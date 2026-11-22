# Waffensachkunde-Lernapp – Überarbeitetes Konzept

Nov 22, 2026 · @Thomas

## 1. Ziel und Leitidee

Die App bereitet Schueler auf die Sachkundepruefung nach Paragraph 7 WaffG vor. Sie verbindet kurze Lerneinheiten mit dem amtlichen Fragenkatalog, gezielter Wiederholung und Pruefungssimulation.

Das Ziel ist sicheres Verstaendnis, nicht blosses Auswendiglernen. Die App zeigt Lernenden ihre Wissensluecken, priorisiert sicherheitsrelevante Inhalte und begleitet sie bis zur Pruefung. Lehrkraefte und Lehrgangsanbieter erhalten Werkzeuge zur Kursverwaltung und Lernstandsauswertung (ab V2).

Grundlage sind die Praesentation Waffensachkunde Paragraph 7 WaffG und der Fragenkatalog des Bundesverwaltungsamtes (Stand 22.03.2022). Vor Veroeffentlichung muessen Nutzungsrechte und Aktualitaet geklaert sein.

## 2. Zielgruppen

| Zielgruppe | Nutzung |
| --- | --- |
| Einzelne Schueler | Selbststaendige Pruefungsvorbereitung mit eigenem Konto und Lizenz |
| Lehrgangsteilnehmer | Begleitendes Lernen zum Kurs, Zugangscode vom Anbieter |
| Lehrkraefte und Ausbilder | Kursverwaltung, Fortschrittsauswertung, eigene Zusatzfragen (V2) |
| Vereine und Verbande | Lizenzkontingente fuer Gruppen, verbandsbezogene Zusatzinhalte (V2) |

## 3. Lernstruktur

Die Navigation folgt den vier Pruefungsgebieten des amtlichen Fragenkatalogs.

| Lernbereich | Unterthemen |
| --- | --- |
| I. Waffenrecht und Vorschriften | Begriffe, Rechte und Pflichten, Kennzeichnung, Aufbewahrung, Notwehr und Notstand, waffenrechtliche Erlaubnisse, Beschussrecht |
| II. Waffentechnik | Waffenarten, wesentliche Teile, Munition, Geschosse und Ballistik |
| III. Sicherer Umgang | Sicherheitsregeln, Verhalten auf der Schiessstatte, Aufsicht und Handhabung |
| IV. Not- und Seenotsignalmittel | Arten, Einsatzbereiche, Vorschriften, sichere Aufbewahrung |

Inhalte aus der Praesentation (z. B. Schiesserlaube, Schiessstatte) werden den passenden Pruefungsgebieten zugeordnet. Inhalt, der nicht Bestandteil des bundesweiten Pruefungsstoffs ist, wird klar gekennzeichnet.

## 4. Lernformen und Interaktionen

### Lerneinheiten

Jede Lektion behandelt ein Thema und enthaelt eine knappe Erklaerung, eine optionale Illustration und eine Wissensfrage mit Quellenangabe. Umfang: 5 bis 10 Minuten.

### Fragen ueben (Uebungsmodus)

Fragen erscheinen im Format des Katalogs. Die App unterstuetzt Single- und Multiple-Choice sowie ausformulierte Antworten. Nach der Antwort gibt es sofortige Rueckmeldung mit Erklaerung und Verweis auf die passende Lektion.

Wichtig: Bei Multiple-Choice koennen mehrere Antworten richtig sein; mindestens eine ist immer richtig. Die Auswertungslogik muss Mehrfachauswahl ausdruecklich unterstuetzen.

### Freie Antworten (vereinfacht fuer V1)

Nach eigener Formulierung zeigt die App die Musterlosung. Der Schueler bewertet sich selbst per Schaltflaeche (Hatte ich vollstaendig / teilweise / nicht). Die Selbsteinschaetzung steuert den Wiederholungsplan. Eine automatische NLP-Bewertung ist nicht vorgesehen; das spart erheblichen Entwicklungsaufwand und ist fuer V1 genuegend.

### Wiederholung (Spaced Repetition)

Falsch beantwortete oder als unsicher markierte Fragen kommen in den Wiederholungsstapel. Die App legt sie nach einem festen Intervallschema erneut vor:

- Neu oder falsch: nach 1 Tag
- Beim naechsten Mal richtig: nach 3 Tagen
- Erneut richtig: nach 7 Tagen
- Wieder richtig: nach 14 Tagen
- Dauerhaft sicher: aus dem aktiven Stapel entfernt

Bei erneuter Fehlerbeantwortung beginnt das Schema von vorn. Sicherheitsrelevante Themen (z. B. Aufbewahrung, Handhabung) werden beim Wiederholungsvorschlag bevorzugt.

### Pruefungssimulation

Mischt Fragen aus allen Lernbereichen; waehrend des Durchgangs keine Loesungen. Auswertung danach: Gesamtergebnis, Auswertung nach Lernbereich, Hinweise auf Schwachstellen, Vorschlaege fuer naechste Lerneinheiten.

Zusaetzlich: kurze Kapiteltests fuer einzelne Themengebiete.

### Lernplan

Schueler koennen ein Pruefungsdatum angeben. Die App erstellt daraus einen anpassbaren Wochenplan mit Lektionen, Fragen und Wiederholungen.

## 5. Startseite und Fortschritt

Die Startseite zeigt auf einen Blick:

- Lernfortschritt je Pruefungsgebiet (Balken oder Prozent)
- empfohlene naechste Lektion oder Frage
- faellige Wiederholungsfragen (Anzahl und Dringlichkeit)
- Ergebnis des letzten Tests
- optional: verbleibende Tage bis zum Pruefungstermin

Ranglisten und Wettbewerbe sind nicht vorgesehen. Der Fokus liegt auf persoenlichem Fortschritt und sicherheitsrelevantem Verstaendnis.

## 6. Funktionen fuer Lehrkraefte (V2)

Der Lehrkraeftebereich ist nicht Teil des MVP. Er enthaelt erheblichen Eigenaufwand (Gruppen-, Kurs- und Fortschrittsverwaltung) und sollte nach dem Pilotbetrieb mit V2 eingefuehrt werden.

Geplanter Funktionsumfang fuer V2:

- Lerngruppen und Kurse anlegen
- Lektionen und Tests zuweisen
- Lernfortschritt der Teilnehmer nach Pruefungsgebiet einsehen
- haeufige Wissensluecken einer Gruppe erkennen
- einfachen Lernstandsbericht exportieren
- kurs- oder verbandsbezogene Zusatzfragen bereitstellen (klar getrennt vom amtlichen Pruefungsstoff)

Sammelcodes und Lizenzkontingente fuer Lehrgangsanbieter koennen bereits in V1 technisch vorbereitet werden, benoetigen aber kein eigenes Verwaltungs-Frontend.

## 7. PWA, Konto und Lizenzmodell

### PWA und Konto

Die App wird als installierbare Progressive Web App umgesetzt. Installation ueber den Browser auf Smartphone, Tablet und Computer. Responsives Layout fuer Mobilgeraete und groessere Bildschirme.

Jeder Schueler erhaelt ein eigenes Konto mit verifizierter E-Mail-Adresse. Die Lizenz ist an das Konto gebunden, nicht an ein einzelnes Geraet. Mehrere eigene Geraete sind erlaubt.

Fuer V1 ist eine Internetverbindung Voraussetzung. Offline-Nutzung kann spaeter als begrenzte Offline-Frist ergaenzt werden (zuvor online bestaetigt, danach kurze Gueltigkeitsdauer).

### Aktivierung per Einmalcode

1. Schueler registriert sich und bestaetigt E-Mail-Adresse.
2. Er gibt den gekauften Aktivierungscode ein.
3. Server prueft den Code und ordnet die Lizenz dem Konto zu.
4. Der Code wird verbraucht und kann nicht ein zweites Mal eingeloest werden.
5. App zeigt Lizenztyp und Laufzeit an.

Der Code ist kein Login-Passwort; er schaltet ein Nutzungsrecht frei. Codes koennen einzeln verkauft oder von Lehrgangsanbietern an Teilnehmer ausgegeben werden.

### Lizenzarten

| Lizenzart | Beschreibung |
| --- | --- |
| Einzellizenz | Ein Schueler, ein Zeitraum |
| Zeitlich befristete Lizenz | Fuer einen Kurszeitraum |
| Dauerlizenz | Optional, kein Ablaufdatum |
| Kontingentcode | Sammelcode fuer Lehrgangsanbieter (V2) |

Jede Lizenz erhaelt einen Status: nicht eingeloest, aktiv, abgelaufen oder gesperrt. Bei Verlust oder fehlerhafter Ausgabe kann ein Code gesperrt und neu ausgestellt werden.

### Serverseitige Lizenzpruefung

Die Pruefung erfolgt ausschliesslich auf dem Server; eine reine Frontend-Sperre laesst sich umgehen. Die App prueft die Lizenz bei der Anmeldung und beim Laden geschuetzter Lerninhalte. Abgelaufene Konten koennen sich weiterhin anmelden, um einen neuen Code einzuloesen.

Codes werden zufaellig generiert, serverseitig gespeichert und mit Eingabelimit gegen Brute-Force geschuetzt.

### Verkauf und Ausgabe

V1: manuelle oder automatisierte Ausgabe nach Kauf. Spaeter: Anbindung an Zahlungsdienstleister, z. B. Bizzify (bezahlter Auftrag erzeugt automatisch Code).

## 8. Datenschutz und Barrierefreiheit

### DSGVO

Die App speichert personenbezogene Daten (E-Mail, Lernfortschritt, Lizenzdaten) serverseitig. Folgende Anforderungen muessen vor dem Launch erfuellt sein:

- Datenschutzerklaerung (Datenkategorien, Zweck, Speicherdauer, Empfaenger)
- Auftragsverarbeitungsvertrag mit dem Hosting-Anbieter
- Auskunfts-, Berichtigungs- und Loeschrecht fuer Nutzer (Konto-Loeschung mit vollstaendiger Datentilgung)
- Hosting in der EU oder mit angemessenem Datenschutzniveau
- Keine Weitergabe von Lernfortschrittsdaten an Dritte ohne ausdrueckliche Einwilligung

Daten minderjaehriger Nutzer erfordern zusaetzliche Pruefung (Zustimmung der Erziehungsberechtigten).

### Authentifizierung und Kontosicherheit

Fuer V1: E-Mail-Verifizierung plus sichere Session-Token. Bei einem Lizenzwert von 20 bis 50 EUR je Code ist eine einfache Passwortstrategie ausreichend, wenn Brute-Force-Schutz und Rate-Limiting konsequent umgesetzt sind. 2FA kann als optionales Feature fuer V2 eingeplant werden.

### Barrierefreiheit

Die App soll grundlegende WCAG-2.1-Anforderungen auf Stufe AA erfuellen:

- Ausreichende Farbkontraste
- Tastaturnavigation
- Screenreader-kompatible Labels und Alt-Texte
- Schriftgroessen skalierbar (kein festes px fuer Lauftext)

Barrierefreiheit gilt insbesondere fuer Verbandsnutzung; eine spezifizierte Anforderung erleichtert spaetere Pruefung.

## 9. Datenmodell (Kernobjekte)

Fuer die Implementierung muessen mindestens folgende Objekte modelliert werden:

| Objekt | Wichtige Felder |
| --- | --- |
| User | id, email, email\_verified, created\_at |
| License | id, user\_id, type, status, valid\_from, valid\_until, code\_id |
| ActivationCode | id, code\_hash, product, status, redeemed\_by, redeemed\_at |
| Lesson | id, area (I-IV), title, content, source\_ref, version, reviewed\_at, valid\_until |
| Question | id, area, type (mc/free), text, source\_ref, is\_official\_exam\_question |
| Answer | id, question\_id, text, is\_correct |
| UserProgress | user\_id, lesson\_id or question\_id, status, last\_seen, next\_due, interval\_step |
| TestRun | id, user\_id, type (practice/simulation/chapter), started\_at, finished\_at |
| TestRunItem | testrun\_id, question\_id, user\_answer, is\_correct |

Die Tabelle interval\_step in UserProgress bildet die Wiederholungsintervalle ab (0 = neu, 1 = 1 Tag, 2 = 3 Tage, 3 = 7 Tage, 4 = 14 Tage, 5 = dauerhaft sicher).

Das Datenmodell muss vor Entwicklungsbeginn vollstaendig ausgearbeitet und mit dem Entwicklungsteam abgestimmt werden.

## 10. Inhaltsqualitaet, Aktualitaet und Rechte

Der amtliche Fragenkatalog traegt den Stand 22.03.2022. Die Praesentation enthaelt zeitgebundene und oertliche Hinweise (z. B. Merkblatt Neu-Ulm, damals geplante Gesetzesaenderung). Diese Inhalte muessen vor Veroeffentlichung fachlich und rechtlich geprueft werden.

### Klaerungs- und Freigabebedarf (kritischer Pfad)

- Nutzungsrechte am BVA-Fragenkatalog: schriftliche Zustimmung des Bundesverwaltungsamtes vor Uebernahme, Bearbeitung und Veroeffentlichung.
- Fachliche Pruefung aller Inhalte auf rechtliche Aktualitaet.
- Kennzeichnung: bundesweiter Pruefungsstoff klar getrennt von Zusatzmaterial und oertlichen Hinweisen.

### Metadaten je Lektion und Frage

- Quelle und Fundstelle (Folien- oder Katalogseite)
- Fachlich verantwortliche Person
- Pruef- und Freigabedatum
- Gueltigkeits- oder Ueberpruefdatum
- Kennzeichnung als amtlicher Pruefungsstoff, Zusatzstoff oder oertlicher Hinweis

Aenderungen an Inhalten werden versioniert gespeichert.

## 11. MVP-Umfang V1

V1 umfasst einen vollstaendig nutzbaren Lernstand, kein halbfertiges Produkt. Alles darueber hinaus kommt in V2.

### Enthalten in V1

1. Vier Lernbereiche mit kurzen Lektionen
2. Uebungsmodus fuer Katalogfragen (Single- und Multiple-Choice)
3. Freie Antworten mit Musterlosung und Selbstbewertung
4. Spaced Repetition mit 5-Stufen-Schema (1 / 3 / 7 / 14 Tage / dauerhaft sicher)
5. Kapiteltests und Pruefungssimulation
6. Fortschrittsanzeige nach Pruefungsgebiet
7. Quellenangaben und Inhaltsverwaltung mit Versionierung
8. Installierbare PWA
9. Persoenliche Konten mit E-Mail-Verifizierung
10. Aktivierungscode-System mit serverseitiger Lizenzpruefung
11. Einzellizenzen und zeitlich befristete Lizenzen

### Zurueckgestellt auf V2

- Lehrkraeftebereich (Kurse, Gruppen, Fortschrittsauswertung)
- Sammelcodes und Lizenzkontingent-Verwaltungs-Frontend
- Offline-Nutzung
- Automatische Zahlungsabwicklung
- 2FA
- Erweiterte Kursauswertungen

### Geschaetzter Entwicklungsaufwand V1

| Bereich | Aufwand |
| --- | --- |
| PWA, Auth, Lizenzcode | 3 bis 5 Wochen |
| Lernmodul (4 Bereiche und Fragen) | 4 bis 6 Wochen |
| Spaced Repetition und Pruefungssimulation | 2 bis 3 Wochen |
| Inhaltspflege-Backend | 2 bis 3 Wochen |
| Datenschutz, Barrierefreiheit, Tests | 1 bis 2 Wochen |
| Gesamt (kleines Team) | ca. 12 bis 16 Wochen |

## 12. Umsetzungsschritte

1. **Rechtsklaerung (kritischer Pfad):** Nutzungsrechte am BVA-Fragenkatalog schriftlich klaeren. Ohne Freigabe kein Start.
2. **Fachliche Pruefung:** Alle Inhalte auf Aktualitaet pruefen, veraltete oder oertliche Hinweise kennzeichnen oder entfernen.
3. **Datenmodell ausarbeiten:** Kernobjekte vollstaendig spezifizieren und mit Entwicklungsteam abstimmen.
4. **Inhaltszuordnung:** Folien und Katalogfragen den Pruefungsgebieten zuordnen, Metadaten erfassen.
5. **DSGVO-Grundlage legen:** Datenschutzerklaerung, AVV mit Hosting-Anbieter, Kontoloeschfunktion.
6. **Lernapp entwickeln (V1):** PWA, Auth, Lizenzcode, Lektionen, Uebungsmodus, Spaced Repetition, Fortschritt, Pruefungssimulation.
7. **Pilotbetrieb:** Kleine Lerngruppe mit Lehrkraft; Rueckmeldungen sammeln.
8. **V2 ausbauen:** Lehrkraeftebereich, Sammelcodes-Frontend, Offline-Funktion, Zahlungsanbindung.

## 13. Risiken und offene Fragen

| Risiko | Wahrscheinlichkeit | Auswirkung | Massnahme |
| --- | --- | --- | --- |
| BVA verweigert Nutzungsrechte | Mittel | Sehr hoch (kein Start moeglich) | Klaerungs-Schritt als kritischer Pfad; fruehzeitig anfragen |
| Fragenkatalog veraltet (Stand 2022) | Hoch | Hoch (Falschinhalte, Haftung) | Fachliche Pruefung vor Veroeffentlichung; Ueberpruefdatum je Frage |
| Lehrkraeftebereich unterschaetzt | Hoch | Mittel (Verzoegerung V1) | Konsequent aus V1 ausgeschlossen; separat planen |
| Lizenzcodes kompromittiert | Niedrig | Mittel (Einnahmeverlust) | Serverseitige Pruefung, Rate-Limiting, zufaellige Code-Generierung |
| DSGVO-Lucken bei Veroeffentlichung | Mittel | Hoch (Bussgelder, Abmahnungen) | DSGVO-Anforderungen vor Launch vollstaendig umsetzen |
| Offline-Erwartung der Nutzer | Mittel | Niedrig (Nutzerzufriedenheit) | V1 klar als Online-Produkt kommunizieren; Offline als V2-Feature |

### Offene Fragen

- Welche Person uebernimmt fachliche Verantwortung fuer Inhalte und Freigabe?
- Welcher Zeitraum ist fuer die Rechtsklaerung mit dem BVA realistisch?
- Welche Zielpreise gelten fuer Einzel- und Kurslizenz?
- Soll V1 bereits Sammelcodes technisch vorbereiten, auch ohne Verwaltungs-Frontend?
- Ist minderjaehrige Zielgruppe relevant (erfordert gesonderte DSGVO-Massnahmen)?
