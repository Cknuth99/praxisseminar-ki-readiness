# Leitlinien für die automatisierte, theoriebasierte Fragebogenerstellung mit großen Sprachmodellen

Design-Science-Ansatz am Beispiel der KI-Readiness von Mitarbeitern

Charlotte Knuth · Praxisseminar, Master Digital Commerce, Marketing & Psychology · WINGS / Hochschule Wismar · Wintersemester 2026/27

## Worum es geht

Dieses Repository enthält das Artefakt der Hausarbeit: einen Master-Prompt, mit dem ein großes Sprachmodell aus einem vorgegebenen Datensatz (fünf validierte Fragebögen und die fünf zugehörigen Paper) einen theoriebasierten Fragebogen zur KI-Readiness von Mitarbeitern erstellt. Der Master-Prompt besteht aus drei Teilen, die nacheinander angewendet werden:

| Prompt | Aufgabe | Ausführung |
|---|---|---|
| [5A](prompts/v5A_erstellung.md) | Erstellung: Begriffe, Theorien, Konstrukt-Inventar, Items, fertiger Fragebogen | NotebookLM, erste Nachricht |
| [5B](prompts/v5B_pruefung.md) | Prüfung nach acht Item- und drei Strukturkriterien | NotebookLM, zweite Nachricht im selben Notebook |
| [5C](prompts/v5C_pruefung_claude.md) | dieselbe Prüfung durch ein zweites Modell ohne Kenntnis des Erstellungsprozesses | Claude, eigener Chat mit denselben sechs Quellen |

Der Master-Prompt wurde in fünf Versionen entwickelt. Jede Version löst ein Problem, das im Test der Vorversion beobachtet wurde. Der Verlauf ist in [PROZESSLOG.md](PROZESSLOG.md) dokumentiert.

## Aufbau des Repositorys

```
README.md                 diese Seite
PROZESSLOG.md             Entwicklungsprotokoll: Iterationen, Hindernisse, Ergebnisse, Limitationen
prompts/                  alle Prompt-Versionen im Wortlaut (v1 bis v5A/5B/5C)
outputs/                  alle Modellausgaben, eine Datei je Lauf und Prompt-Teil
fragebogen/               der finale Fragebogen (Version 5, Lauf 2, nach Prüfung durch 5C)
screenshots/              Abbildungen aus NotebookLM
```

Dateinamen in `outputs/`: `output_v5_lauf2_a.txt` steht für Version 5, Lauf 2, Teil a. Teil `a` ist die Ausgabe des Erstellungsprompts, `b` die Prüfung im selben Notebook, `c` die Prüfung durch Claude. Die Versionen 6 und 7 sind keine neuen Prompts: v6 ist Prompt 5A in Claude, v7 ist Prompt v1 in Claude (Gegentest).

## NotebookLM-Notebooks

Für jeden Lauf wurde ein eigenes Notebook angelegt, damit sich die Läufe nicht beeinflussen. Alle Notebooks enthalten dieselben sechs Quellen (Datensatz mit fünf Fragebögen, fünf Paper). Die Links sind als Betrachter freigegeben.

| Nr. | Version, Lauf | Link |
|---|---|---|
| 01 | v1, Lauf 1 und 2 (im selben Chat) | https://notebook.google.com/notebook/689c905f-0be1-411a-9f44-796fb8f9808c |
| 02 | v1, Lauf 2b (neues Notebook) | https://notebook.google.com/notebook/8f7b6eaf-b4b0-46d5-b182-8fef9ac9f51a |
| 03 | v2, Lauf 1 | https://notebook.google.com/notebook/0499c102-d214-472a-aa86-79ca9c72af8b |
| 04 | v2, Lauf 2 | https://notebook.google.com/notebook/4dd867c0-7ff0-45fd-a0fe-d34aab57644a |
| 05 | v3, Lauf 1 | https://notebook.google.com/notebook/a7af8189-656d-4d1f-abd3-e58e9c3303f1 |
| 06 | v3, Lauf 2 | https://notebook.google.com/notebook/344578d3-9c0c-4279-8427-50afd9c48ad7 |
| 07 | v4, Lauf 1 | https://notebook.google.com/notebook/352ee574-83bb-40cf-a630-e593422aade1 |
| 08 | v4, Lauf 2 | https://notebook.google.com/notebook/ea7e0791-8443-4d30-b3a4-d38088b96acd |
| 09 | v5, Lauf 1 | https://notebook.google.com/notebook/e1fbacfe-d816-4bcd-99bf-0fee389a2f58 |
| 10 | v5, Lauf 2 (Demonstrationsfall in Kapitel 4) | https://notebook.google.com/notebook/32d68783-9eea-4316-84a2-250f0d6e3b69 |

NotebookLM teilt den Chatverlauf nicht mit. Die vollständigen Ausgaben jedes Laufs liegen deshalb als Textdateien in `outputs/`.

## Was nicht im Repository liegt

Der Datensatz und die fünf Paper wurden von der Hochschule bereitgestellt und dürfen laut Study Guide nicht weitergegeben werden. Sie sind über die NotebookLM-Links einsehbar, aber nicht hier abgelegt. Ebenfalls nicht enthalten ist die Hausarbeit selbst; sie wird getrennt eingereicht.

## Verwendete Werkzeuge

NotebookLM (Google) als vorgegebene Plattform für die Entwicklung und für die Prüfung 5B. Claude (Anthropic) als zweite Plattform für die Prüfung 5C, für die Vergleichsläufe v6 und v7 sowie als Werkzeug bei der Entwicklung der Prompts, der Erstellung der Fehlerlisten und der sprachlichen Überarbeitung. Alle Inhalte wurden von der Verfasserin geprüft und verantwortet.
