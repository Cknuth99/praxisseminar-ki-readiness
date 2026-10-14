# Prompt Version 5C (Prüfung durch ein zweites Modell) – finale Fassung

Plattform: Claude · Läufe: output_v5_lauf1_c_Claude, output_v5_lauf2_c_Claude
Wird in einem neuen Chat ohne Kenntnis des Erstellungsprozesses gesendet. Anhang: Datensatz (fünf Fragebögen, fünf Paper) und der von 5A erzeugte Fragebogen. Prüfkriterien identisch mit 5B.

---

Im Anhang findest du einen Datensatz mit fünf wissenschaftlichen Fragebögen sowie die fünf zugehörigen Paper. Darunter steht ein Fragebogen zur KI-Readiness von Mitarbeitenden, den eine andere KI auf Basis dieser Quellen erstellt hat. Es ist nicht bekannt, ob im Unternehmen bereits KI eingesetzt wird.

Prüfe den Fragebogen kritisch als unabhängiger Gutachter. Erfinde keine Probleme: Wenn ein Item fehlerfrei ist, markiere es als "ok".

Prüfe jedes Item aus Tabelle D anhand dieser Kriterien:
1. Doppelfrage
2. Suggestivfrage
3. Versteckte Annahme (setzt vorhandene oder genutzte KI voraus)
4. Passung zur Konstruktdefinition
5. Überschneidung mit einem anderen Konstrukt
6. Korrekte Herkunftsangabe (vergleiche mit dem Originalitem im Datensatz)
7. Korrekte (R)-Kennzeichnung
8. Verständlichkeit für eine Person ohne KI-Erfahrung

Prüfe außerdem die Gesamtstruktur:
- Ist das Konstrukt-Inventar vollständig (alle Konstrukte aller fünf Fragebögen)?
- Sind alle Konstrukte der gewählten Theorien aufgenommen oder begründet ausgeschlossen?
- Enthält die Einleitung Zusagen ohne Platzhalter?

Ausgabe:
F) Prüftabelle: Item-ID | Befund (ok oder Problem mit Kriterium-Nummer) | Begründung | Änderung
G) Prüfung der Gesamtstruktur
H) Finaler Fragebogen mit allen Änderungen (oder "keine Änderungen erforderlich")

Beende die Antwort ohne Rückfragen oder Angebote.

Fragebogen: [Ausgabe von Prompt 5A einfügen bzw. als Datei anhängen]
