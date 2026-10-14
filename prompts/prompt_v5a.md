# Prompt Version 5A (Erstellung) – finale Fassung

Plattform: NotebookLM (output_v5_lauf1_a, output_v5_lauf2_a) und Claude (output_v6_lauf1_a, output_v6_lauf2_a)
Neu gegenüber V4A: Zählregel für Konstrukte (nur Überschriften), Höchstgrenze 12 Konstrukte × 3 Items, Aufzählungen gelten als Doppelfrage, Konjunktiv gegen versteckte Annahmen, umgedrehte Items immer "neu", verschärftes Zusagenverbot. Auf ca. 3.400 Zeichen verdichtet (Zeichenlimit NotebookLM).

---

Du bist Experte für empirische Sozialforschung und Fragebogenentwicklung. Arbeite ausschließlich mit den bereitgestellten Quellen.

Kontext: Ein Unternehmen möchte die KI-Readiness seiner Mitarbeitenden messen. Ob dort bereits KI eingesetzt wird, ist unbekannt.

Schritt 1 – Begriffe
Definiere "KI-Readiness" in 2–3 Sätzen und was im Fragebogen unter "KI" verstanden wird. Die KI-Definition ist sachlich, allgemein verständlich und ohne technische Behauptungen, die nicht für alle KI-Anwendungen gelten. Fehlt eine Definition in den Quellen, kennzeichne sie als eigene Arbeitsdefinition.

Schritt 2 – Theorien
Wähle 1–3 Theorien aus den Quellen, die KI-Readiness erklären, und begründe die Wahl. Berücksichtige kognitive, affektive und soziale Aspekte.

Schritt 3 – Konstrukt-Inventar
Liste für jeden der fünf Fragebögen im Datensatz alle als Überschrift genannten Konstrukte auf (Unterkategorien wie einzelne Aufgabentypen zählen nicht) und nenne die Anzahl pro Fragebogen. Entscheide je Konstrukt "aufnehmen" oder "ausschließen" mit einem Satz Begründung. Regeln:
- "Nutzungsabsicht" wird immer als Zielkonstrukt aufgenommen.
- Konstrukte der gewählten Theorien werden aufgenommen oder ausdrücklich begründet ausgeschlossen.
- Empirische Begründungen (z. B. "nicht signifikant") nur mit Quellenangabe.
- Jedes Konstrukt misst genau eine Dimension; höchstens 12 Konstrukte, bei mehr Kandidaten priorisieren.

Schritt 4 – Definitionen und Items
Übernimm die Konstruktdefinitionen aus dem Datensatz, angepasst auf KI am Arbeitsplatz; eigene Definitionen kennzeichnen. Formuliere genau 3 Items pro Konstrukt. Regeln:
- Jedes Item passt zur Definition und überschneidet sich nicht mit anderen Konstrukten.
- Keine Doppelfragen, auch keine Aufzählungen wie "nervös und beunruhigt".
- Keine Suggestivfragen; kurze Sätze, Ich-Form, Bezug zum eigenen Arbeitsplatz.
- Keine versteckten Annahmen über verfügbare oder genutzte KI; Erfahrungen im Konjunktiv ("Ich würde … vertrauen" statt "Ich vertraue …").
- (R) nur, wenn das Item entgegen der Richtung seines eigenen Konstrukts formuliert ist (z. B. "Ich fände KI an meinem Arbeitsplatz unbefriedigend" bei Einstellung). Items zu negativen Konstrukten wie Angst in deren eigener Richtung erhalten kein (R).
- Herkunft: "übernommen" nur bei unverändertem Inhalt (ggf. übersetzt); "angepasst", wenn nur der Gegenstand ersetzt wurde (Originalitem angeben); sonst "neu" (kurz begründen). Umgedrehte Items sind immer "neu". Nenne Fragebogen und Item-Nummer.

Schritt 5 – Fragebogen
Schreibe eine kurze Einleitung, die KI verständlich beschreibt (vergleichbar mit der VR-Beschreibung in Fragebogen 3). Keinerlei Aussagen zu Dauer, Anonymität, Vertraulichkeit oder Datenverwendung, auch nicht abgeschwächt; nur Platzhalter wie [Dauer], [Hinweis zum Datenschutz]. 7-stufige Likert-Skala (1 = stimme überhaupt nicht zu, 7 = stimme voll und ganz zu). Keine zwei Items desselben Konstrukts direkt hintereinander.

Ausgabe:
A) Definitionen
B) Theorien mit Begründung
C) Konstrukt-Inventar: Konstrukt | Fragebogen | aufnehmen/ausschließen | Begründung (plus Anzahl pro Fragebogen)
D) Item-Tabelle: Konstrukt | Definition | Item-ID | Item | (R) | Herkunft | Quelle
E) Fragebogen für die Mitarbeitenden (Einleitung, Items mit Item-ID, ohne Konstruktnamen)

Beende die Antwort ohne Rückfragen oder Angebote.