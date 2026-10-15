# Prozesslog

Entwicklungsprotokoll zum Master-Prompt: fünf Versionen, zehn Läufe in NotebookLM, sechs Läufe in Claude. Alle genannten Dateien liegen in diesem Repository. Notebook-Nummern beziehen sich auf die Linkliste in der README. Bewertung und Einordnung stehen in Kapitel 5 und 6 der Hausarbeit.

## 1. Aufgabe und Ziele

- Artefakt: ein Master-Prompt, mit dem ein großes Sprachmodell aus einem vorgegebenen Datensatz einen theoriebasierten Fragebogen zur KI-Readiness von Mitarbeitern erstellt
- Das Modell schlägt die Theorien selbst vor und leitet die Items daraus ab
- Sieben Ziele (Tabelle 1 der Hausarbeit): Theoriebindung, nachvollziehbare Herkunft, Item-Qualität, Quellenbindung, mindestens 90 Prozent Übereinstimmung der Konstruktauswahl zwischen zwei Läufen, vollständiges Konstrukt-Inventar, nach der Prüfung keine Doppelfragen und versteckten Annahmen
- Die 90-Prozent-Schwelle ist selbst gesetzt. Bei 13 Konstrukten darf höchstens eines abweichen
- Wortgleiche Reproduzierbarkeit war kein Ziel

## 2. Quellen

- Wissensbasis: Datensatz mit fünf validierten Fragebögen und die fünf zugehörigen Paper
- Kursunterlagen zur Prüfung wurden nicht hochgeladen, weil sie das Modell ablenken würden
- Die Unterlagen stammen von der Hochschule und liegen nicht im Repository. Sie sind über die NotebookLM-Links einsehbar

## 3. Vorgehen

- Jede Version lief zweimal. Ab v1 Lauf 2b hatte jeder Lauf ein eigenes Notebook
- Ab v4 bestand ein Lauf aus zwei Nachrichten (Erstellung a, Prüfung b), ab v5 aus drei (zusätzlich Prüfung c in Claude)
- Zum Plattformvergleich liefen Prompt 5A (als v6) und Prompt v1 (als v7) auch in Claude, jeweils in eigenen Chats mit denselben sechs Quellen
- Claude-Version: Fable 5.1, Stand September 2026

| Version | Plattform | Dateien in `outputs/` | Notebook |
|---|---|---|---|
| v1 | NotebookLM | output_v1_lauf1, lauf2 (selber Chat), lauf2b (neues Notebook) | 01, 02 |
| v2 | NotebookLM | output_v2_lauf1, lauf2 | 03, 04 |
| v3 | NotebookLM | output_v3_lauf1, lauf2 | 05, 06 |
| v4 | NotebookLM | output_v4_lauf1_a/b, lauf2_a/b | 07, 08 |
| v5 | NotebookLM + Claude | output_v5_lauf1_a/b/c, lauf2_a/b/c | 09, 10 |
| v6 (5A in Claude) | Claude | output_v6_lauf1_a, lauf2_a | – |
| v7 (v1 in Claude) | Claude | output_v7_lauf1, lauf2 | – |

## 4. Iterationsverlauf

| Version | Wichtigste Änderung | Beobachtung im Test |
|---|---|---|
| v1 | Ausgangsbasis: Theorien vorschlagen, Konstrukte ableiten, 3 bis 5 Items je Konstrukt, 7-stufige Skala, Tabellenausgabe | Theorien plausibel. Items passten nicht zur Theorie, Doppelfragen, Herkunft unklar, KI und KI-Readiness nicht definiert |
| v2 | Definitionen, Konsistenzregel Theorie–Konstrukt, Item-Regeln nach Hinkin, Herkunftskennzeichnung, Einleitungstext | 5 von 6 Konstrukten gleich. Nutzungsabsicht fehlte in einem Lauf, Konstrukte überschnitten sich, Herkunft teils falsch |
| v3 | Konstrukt-Inventar über alle fünf Fragebögen, Nutzungsabsicht als Pflichtkonstrukt, Qualitätsprüfung in Rollen im selben Durchgang | 6 gemeinsame Konstrukte. Prüfung inszeniert: das Modell erfand Entwürfe, um Korrekturen vorzuführen |
| v4 | Prüfung als eigener Prompt 4B in zweiter Nachricht, Inventar mit Zählung, Definitionen aus dem Datensatz, Regeln für (R) und Herkunft, Platzhalter statt Zusagen | 9 gemeinsame Konstrukte. Prüfung erstmals echt, aber instabil: Prüfer B fand in Lauf 1 Mängel an 13 Items, in Lauf 2 an 2 Items |
| v5 | Zählregel für Konstrukte, Höchstgrenze 12 Konstrukte mit je 3 Items, Aufzählungen gelten als Doppelfrage, Konjunktiv gegen versteckte Annahmen, umgepolte Items immer "neu", zweiter Prüfprompt 5C für ein anderes Modell | 10 von 13 Konstrukten gemeinsam (77 %). Formale Regeln greifen, inhaltliche Fragen bleiben |

- v1: Lauf 1 und 2 im selben Chat fielen fast identisch aus. Der Wiederholungslauf 2b im neuen Notebook zeigte die tatsächliche Abweichung
- v3: Erstellung und Prüfung im selben Prompt. Geprüft wurde eine Vorführung, nicht der Fragebogen. Ab v4 getrennt
- v5: Prompt 5A ließ sich in NotebookLM nicht absenden (Zeichengrenze). Ohne inhaltliche Änderung auf rund 3.400 Zeichen verdichtet
- v5, Lauf 1: Doppelfrage "Antworten und Ergebnissen" (Item VERT1) trotz wörtlichem Verbot im Prompt

## 5. Das finale Artefakt

| Prompt | Aufgabe | Ausführung |
|---|---|---|
| 5A | Erstellung: Begriffe, Theorien, Konstrukt-Inventar, Items, fertiger Fragebogen | NotebookLM, erste Nachricht |
| 5B | Prüfung nach acht Item- und drei Strukturkriterien (Prüfer B) | NotebookLM, zweite Nachricht im selben Notebook |
| 5C | dieselbe Prüfung durch ein zweites Modell ohne Kenntnis des Erstellungsprozesses (Prüfer C) | Claude, eigener Chat mit denselben Quellen |

- 5B ist im Wortlaut gleich 4B. 5C ergänzt eine Rollenbeschreibung und einen Platzhalter für den zu prüfenden Fragebogen
- Umgesetzte Techniken: Retrieval-Augmented Generation (Bindung an die Quellen), Few-Shot-Prompting (die fünf Fragebögen als Beispiele), Rollentrennung agentischer Workflows als getrennte Prompts, weil NotebookLM keine Agentenarchitektur unterstützt

## 6. Konstrukt-Stabilität (Ziel 5)

Anteil der Konstrukte, die in beiden Läufen desselben Prompts vorkommen:

| Prompt | NotebookLM | Claude |
|---|---|---|
| v1 | instabil: 7 bzw. 8 Konstrukte, Auswahl sehr verschieden | 12 von 13 (92 %), als v7 |
| v3 | 6 gemeinsame Konstrukte | – |
| v4 | 9 gemeinsame Konstrukte | – |
| v5A | 10 von 13 (77 %) | 9 von 10 (90 %), als v6 |

- Claude mit v1: 48 bzw. 53 Items statt 27 bis 30, bestehende KI-Nutzung vorausgesetzt, keine Herkunft (output_v7). Mit 5A traten diese Fehler nicht mehr auf (output_v6)
- Nicht jede Abweichung ist ein Fehler: In v6 schloss ein Lauf die Benutzerfreundlichkeit aus (Hypothese 6a in Paper 2 nicht signifikant), der andere nahm sie auf (Hypothese 6b signifikant). Beide Begründungen sind korrekt

## 7. Fehlerlisten und Prüfbefunde (Ziele 2, 3, 6, 7)

Vor jeder Prüfung wurde der erzeugte Fragebogen mit Claude analysiert. Die festgestellten Mängel bilden die Fehlerliste. Danach wurde gezählt, welche Punkte Prüfer B und C fanden. Mängel, die erst ein Prüfer aufdeckte und die sich am Datensatz bestätigen ließen, wurden nachträglich aufgenommen.

### v4

- Lauf 1 (output_v4_lauf1_b): Prüfer B fand 13 Items mit Mängeln. Zwei Doppelfragen (FEA_2, FEA_3), sieben versteckte Annahmen einer bestehenden KI-Nutzung (ATT_4, PBC_3, UNC_1 bis UNC_3, ING_1, ING_2), fünf falsche Herkunftsangaben (ABI_1 bis ABI_3, ING_1, ING_2), ein Grammatikfehler (ATT_2). ING_1 und ING_2 zählen in beiden Gruppen
- Lauf 2 (output_v4_lauf2_b): Prüfer B fand nur zwei Doppelfragen (TRU_1, TRU_3) und erklärte die übrigen 28 der 30 Items für fehlerfrei
- Folge: Prüfung zwischen den Läufen nicht stabil, deshalb zweiter Prüfer in v5

### v5, Lauf 1

| Nr. | Mangel | Prüfer B (output_v5_lauf1_b) | Prüfer C (output_v5_lauf1_c_Claude) |
|---|---|---|---|
| 1 | Doppelfrage VERT1 "Antworten und Ergebnissen" (Ziel 3, 7) | gefunden | nicht gefunden |
| 2 | Sieben falsche Herkunftsetiketten: LEIST1 bis LEIST3 als "übernommen" statt "angepasst", EINST3, VERT3, BEDI3, INTEG3 als "neu" statt "angepasst, umgepolt" (Ziel 2) | teilweise: LEIST1 bis LEIST3 | alle sieben |
| 3 | NUTZ1: Originalitem 10(4) doppelt vergeben, Überschneidung mit LEIST1 (Ziel 2) | gefunden | gefunden |
| 4 | Versteckte Annahme vorhandener KI in VKONT3 und FAEH3 (Ziel 3, 7) | nicht gefunden | gefunden |
| 5 | Doppelverneinung in INTEG1, Fachbegriff "Interaktionsdaten" in INTEG2 (Ziel 3) | nicht gefunden | gefunden |

- Inventar 40 von 40, von beiden Prüfern bestätigt (Ziel 6)
- Prüfer B markierte zusätzlich WOHL1 bis WOHL3 als falsch gepolt. Umstritten, weil die Skala Unheimlichkeit misst
- Prüfer C bestätigte die zitierten Kennwerte gegen die Paper (Abschnitt 8)

### v5, Lauf 2

| Nr. | Mangel | Prüfer B (output_v5_lauf2_b) | Prüfer C (output_v5_lauf2_c_Claude) |
|---|---|---|---|
| 1 | Inventar unvollständig: Abilities (HIS) aus Fragebogen 1 fehlt, 39 von 40 (Ziel 6) | gefunden, ergänzt, danach als vollständig erklärt | gefunden |
| 2 | ATT_3 als "neu" statt "angepasst, invertiert" (Ziel 2) | nicht gefunden | gefunden |
| 3 | ING_3 als "neu" statt "angepasst" (Ziel 2) | nicht gefunden | gefunden |
| 4 | PEOU_3 und PU_3 beginnen mit "Zusammenfassend", stehen aber weit von ihren Konstrukt-Items entfernt (Ziel 3) | nicht gefunden | gefunden |
| 5 | ABI_1 setzt vorhandene KI voraus, Konjunktiv "wüsste" bei einer Wissensaussage (Ziel 3, 7) | nicht gefunden | gefunden |
| 6 | TTF_1 bis TTF_3 ohne Vorfrage, ob solche Aufgaben vorkommen (Ziel 3) | nicht gefunden | gefunden, Zusatzoption vorgeschlagen |
| 7 | Verschachtelte Verneinung in ING_1, Fachbegriff "Interaktionsdaten" in ING_2 (Ziel 3) | nicht gefunden | gefunden |

- Prüfer B bewertete alle 33 Items als fehlerfrei
- Prüfer C markierte zehn Items mit Korrekturvorschlag. Der korrigierte Fragebogen (Abschnitt H in output_v5_lauf2_c_Claude) ist die finale Fassung in `fragebogen/`
- Ein Korrekturvorschlag von Prüfer C führte selbst eine neue Aufzählung ein: ING_1 "vertraulich bleiben und nicht an Dritte gelangen" (Item 10 der finalen Fassung)

## 8. Prüfung der zitierten Kennwerte (Ziel 4)

Alle Stellen, an denen das Modell in v5 Lauf 1 oder 2 Kennwerte aus den Papern zitiert, im PDF nachgeschlagen:

| Behauptung im Output | Lauf | Paper | Befund |
|---|---|---|---|
| Hedonische Motivation → Nutzungsabsicht nicht signifikant (Lauf 1 mit β = .011) | 1, 2 | Paper 2, S. 967 | stimmt (H4, β = .011) |
| Angst vor Umweltgefahren → Verhaltenskontrolle nicht signifikant | 1, 2 | Paper 2, S. 967 | stimmt (H9, β = −.045) |
| Umweltbesorgnis → Verhaltenskontrolle nicht signifikant | 2 | Paper 2, S. 967 | stimmt (H8, β = −.037) |
| Gewohnheit → Verhaltenskontrolle nicht signifikant | 2 | Paper 2, S. 967 | stimmt (H5b, β = .101) |
| Verhaltenskontrolle → Nutzungsabsicht negativ | 2 | Paper 2, S. 967 | stimmt (H10, β = −.218) |
| Soziale Kommunikation → Arbeitsengagement nicht signifikant (0.097) | 1, 2 | Paper 5, S. 179 | stimmt (H2) |
| Wohlwollen trägt in keinem Unternehmensbereich zum Vertrauen bei | 2 | Paper 4, S. 11 | stimmt |
| Kosten/Barrieren in allen KI-Medizinszenarien ohne direkten Effekt | 2 | Paper 1 | nicht prüfbar: Koeffizienten stehen in "Multimedia Appendix 1", nicht im PDF |

- Sieben von acht stimmen, eine nicht prüfbar, keine falsch
- Für v1 bis v4 wurden die Kennwerte nicht vollständig geprüft

## 9. Hindernisse

| Hindernis | Auswirkung | Lösung |
|---|---|---|
| Lauf 1 und 2 von v1 im selben Chat | Läufe beeinflussten sich | Ab Lauf 2b ein Notebook pro Lauf |
| Chatverlauf soll offengelegt werden, unabhängige Läufe brauchen getrennte Chats | Konflikt zwischen Nachvollziehbarkeit und Unabhängigkeit | Ein Notebook pro Lauf, alle als Betrachter freigegeben. Mehrere Chats laut Dozenten zugelassen |
| NotebookLM teilt den Chatverlauf nicht mit | Links zeigen Quellen, nicht die Ausgaben | Alle Ausgaben als Textdateien in `outputs/` |
| Prüfung in v3 im selben Durchgang wie die Erstellung | Modell erfand Fehler, Prüfung wertlos | Ab v4 eigener Prüfprompt in zweiter Nachricht |
| Prüfer B fand in v4 je nach Lauf 13 oder 2 Mängel | Ein Prüfer nicht verlässlich | Zweiter Prüfprompt 5C in anderem Modell |
| Prompt 5A ließ sich in NotebookLM nicht absenden | Zeichengrenze begrenzt die Zahl der Regeln | Auf rund 3.400 Zeichen verdichtet |
| 5C zunächst nur mit dem Datensatz geplant | Prüfer C hätte weniger Information als B gehabt | Alle sechs Quellen auch für 5C |
| Geschlechtergerechte Schreibweise im Prompt uneinheitlich | Promptdateien und gesendeter Wortlaut wichen ab | Dateien am gesendeten Wortlaut ausgerichtet, Rest als Limitation in der Hausarbeit |
