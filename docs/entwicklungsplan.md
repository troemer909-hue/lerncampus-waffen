# Entwicklungsplan Waffensachkunde-Lernapp

Nov 22, 2026 · @Thomas

## 1. Projektuebersicht

Dieser Plan beschreibt die Entwicklung der Waffensachkunde-Lernapp von der Vorbereitung bis zum produktiven Betrieb. Er basiert auf dem ueberarbeiteten Konzept (V1-Scope).

|  |  |
| --- | --- |
| Produkt | Progressive Web App zur Vorbereitung auf die Sachkundepruefung nach Paragraph 7 WaffG |
| V1-Scope | Lernmodul, Uebungsmodus, Spaced Repetition, Pruefungssimulation, Lizenzcode-System |
| Gesamtdauer V1 | ca. 20 Wochen (Vorbereitung + Entwicklung + Pilotbetrieb) |
| Kritischer Pfad | Rechtsklaerung BVA-Fragenkatalog vor Entwicklungsstart |
| V2 | Lehrkraeftebereich, Zahlungsintegration, Offline-Nutzung |

## 2. Phasen und Meilensteine

| Phase | Wochen | Ziel | Gate (Freigabe fuer naechste Phase) |
| --- | --- | --- | --- |
| 0 Vorbereitung | 1 bis 3 | Rechtsklaerung, Inhalte geprueft, Datenmodell final, Tech-Stack beschlossen | Schriftliche BVA-Freigabe liegt vor |
| 1 Grundgeruest | 4 bis 7 | Lauffaehige PWA mit Auth, Datenbank, Lizenzcode-Backend | Login und Lizenzaktivierung funktionieren end-to-end |
| 2 Lernmodul | 8 bis 13 | Lektionen, Fragenmodul (MC und Freiantwort), Spaced Repetition, Fortschritt | Alle Fragen eines Lernbereichs spielbar, Wiederholungsintervalle korrekt |
| 3 Pruefungsmodus | 14 bis 16 | Pruefungssimulation, Kapiteltests, Lernplan, DSGVO-Checks, Barrierefreiheit | Vollstaendiger Pruefungsdurchgang auswertbar; DSGVO-Checkliste abgehakt |
| 4 Pilotbetrieb | 17 bis 20 | Beta mit echter Lerngruppe, Feedback, Bugfixes, Produktionslaunch | Nutzerfeedback ausgewertet, kritische Bugs behoben, Launch-Checkliste gruen |
| V2 Planung | ab Woche 21 | Lehrkraeftebereich, Zahlungsintegration, Offline-Nutzung | Pilotfeedback ausgewertet, V2-Backlog priorisiert |

Alle Wochen sind relativ zum Projektstart. Der kritische Pfad laeuft durch Phase 0: ohne BVA-Freigabe startet Phase 1 nicht.

## 3. Technologiestack

Der Stack muss vor Ende Phase 0 verbindlich festgelegt werden. Folgende Empfehlungen gelten als Ausgangspunkt.

| Bereich | Empfehlung | Begruendung |
| --- | --- | --- |
| Frontend Framework | React mit TypeScript | Grosse Community, starkes PWA-Oekosystem (Vite, Workbox) |
| PWA-Grundlage | Vite PWA Plugin + Workbox | Service Worker und Manifest werden automatisch generiert |
| Styling | Tailwind CSS | Schnelle Entwicklung, gutes Responsive-Verhalten |
| Backend | Node.js mit Express oder Fastify (TypeScript) | Einheitliche Sprache Frontend und Backend |
| Datenbank | MySQL | Relationale Struktur passt zum Datenmodell; weit verbreitet, guter Hosting-Support |
| ORM | Prisma | Typsichere Datenbankzugriffe, einfache Migrationen |
| Authentifizierung | JWT + E-Mail-Verifizierung (eigene Implementierung oder Auth.js) | Volle Kontrolle ueber Nutzerdaten, kein Drittanbieter-Lock-in |
| Hosting Backend | Hetzner Cloud oder Railway (EU-Region) | DSGVO-konformes Hosting in der EU |
| Hosting Frontend | Vercel oder Cloudflare Pages | Schnelle CDN-Auslieferung, automatische HTTPS |
| Datenbank-Hosting | PlanetScale (MySQL serverless), Railway MySQL oder Hetzner Cloud | EU-Region verfuegbar; Prisma unterstuetzt alle drei |
| CI/CD | GitHub Actions | Automatische Tests und Deployments bei jedem Push |
| Monitoring | Sentry (Fehler) + Plausible oder Umami (Analytics, DSGVO-konform) | Kein Google Analytics |

Falls ein Entwickler bereits einen bevorzugten Stack mitbringt, ist dieser Vorrang zu geben, sofern die DSGVO-Anforderungen (EU-Hosting) und PWA-Faehigkeit erhalten bleiben.

## 4. Phase 0: Vorbereitung (Wochen 1-3)

### Rechtliches

- [ ] Anfrage an das Bundesverwaltungsamt (BVA): schriftliche Zustimmung zur Nutzung und Bearbeitung des Fragenkatalogs einholen
- [ ] Nutzungsrechte an der Praesentation klaeren
- [ ] Datenschutzerklaerung erstellen
- [ ] Hosting-Anbieter auswaehlen und Auftragsverarbeitungsvertrag schliessen

### Inhalte

- [ ] Alle Folien und Katalogfragen den vier Pruefungsgebieten zuordnen
- [ ] Veraltete, oertliche oder rechtlich unklare Inhalte kennzeichnen oder entfernen
- [ ] Metadaten je Lektion und Frage erfassen (Quelle, Fundstelle, Pruefstatus)
- [ ] Fachlich verantwortliche Person fuer Inhaltsfreigabe benennen

### Technik und Planung

- [ ] Technologiestack verbindlich festlegen
- [ ] Datenmodell vollstaendig ausarbeiten und mit Entwicklungsteam abstimmen
- [ ] Git-Repository und CI/CD-Pipeline einrichten
- [ ] Entwicklungsumgebung dokumentieren (README, .env-Vorlage)
- [ ] Hosting-Infrastruktur aufsetzen (Staging- und Produktionsumgebung)

**Gate:** BVA-Freigabe schriftlich vorliegend; Datenmodell abgenommen; Hosting aufgesetzt.

## 5. Phase 1: Grundgeruest (Wochen 4-7)

### PWA und Frontend-Grundstruktur

- [ ] PWA-Projektstruktur aufsetzen (Vite, TypeScript, Tailwind)
- [ ] Service Worker und Web App Manifest konfigurieren
- [ ] Routing-Struktur anlegen (Startseite, Auth, Lernbereich, Einstellungen)
- [ ] Responsives Basis-Layout (Mobile first)
- [ ] Barrierefreiheits-Grundlagen: Farbsystem, Schriftskala, Fokus-Management

### Authentifizierung

- [ ] Registrierungsformular mit E-Mail-Verifizierung
- [ ] Login und Logout
- [ ] Passwort-Reset per E-Mail
- [ ] Session-Management (JWT, sichere Speicherung)
- [ ] Rate-Limiting und Brute-Force-Schutz fuer Login-Endpunkte

### Lizenzcode-System (Backend)

- [ ] Code-Generator (zufaellige, schwer erratbare Codes)
- [ ] Einloese-Endpunkt mit serverseitiger Pruefung
- [ ] Lizenz-Status-Pruefung bei geschuetzten API-Endpunkten
- [ ] Admin-Minimal-Interface: Code erzeugen, Status einsehen, Code sperren

### Datenbank

- [ ] Schema deployen (User, License, ActivationCode)
- [ ] Migrationsworkflow einrichten
- [ ] Backup-Strategie konfigurieren

**Gate:** Registrierung, Login und Lizenzaktivierung funktionieren end-to-end in Staging.

## 6. Phase 2: Lernmodul (Wochen 8-13)

### Lektionen

- [ ] Lektion-Datenstruktur und CMS-Minimal-Interface (Inhalt einpflegen, bearbeiten, versionieren)
- [ ] Lektion-Anzeige im Frontend (Text, optionale Illustration, Quellenangabe)
- [ ] Navigation nach Pruefungsgebieten (I-IV)
- [ ] Lektionsfortschritt pro Nutzer speichern

### Fragenmodul

- [ ] Fragen-Datenstruktur (MC, Multiple-Choice, Freiantwort)
- [ ] Fragenmodul: Single-Choice mit sofortiger Rueckmeldung und Erklaerung
- [ ] Multiple-Choice: Mehrfachauswahl und korrekte Auswertung (mindestens eine Antwort richtig)
- [ ] Freiantwort: Musterlosung anzeigen, Selbstbewertung per Schaltflaeche
- [ ] Verknuepfung jeder Frage mit passender Lektion und Quellenangabe

### Spaced Repetition

- [ ] UserProgress-Tabelle: Intervallschritt und naechstes Faelligkeitsdatum speichern
- [ ] Wiederholungsstapel-Logik: Faellige Fragen anzeigen, Intervall nach Ergebnis anpassen
- [ ] Intervallschema umsetzen: 1 / 3 / 7 / 14 Tage / dauerhaft sicher
- [ ] Sicherheitsrelevante Fragen bei Wiederholungsvorschlag bevorzugen
- [ ] Fragen als unsicher markieren (manuell)

### Fortschrittsanzeige

- [ ] Fortschrittsbalken je Pruefungsgebiet auf Startseite
- [ ] Anzahl faelliger Wiederholungsfragen
- [ ] Letztes Testergebnis anzeigen
- [ ] Optionale Anzeige: verbleibende Tage bis Pruefungstermin

**Gate:** Alle Fragen eines Lernbereichs spielbar; Wiederholungsintervalle korrekt; Fortschritt wird persistiert.

## 7. Phase 3: Pruefungsmodus und Polishing (Wochen 14-16)

### Pruefungssimulation und Tests

- [ ] Pruefungssimulation: gemischte Fragen aus allen Lernbereichen, keine Loesungen waehrend des Durchgangs
- [ ] Auswertung nach Pruefungssimulation: Gesamtergebnis, Auswertung je Lernbereich, Schwachstellenhinweise
- [ ] Kapiteltest: Kurztest fuer einzelne Themengebiete
- [ ] Lernplan: Pruefungsdatum eingeben, Wochenplan generieren

### DSGVO und Rechtliches

- [ ] Kontoloeschung mit vollstaendiger Datentilgung implementieren
- [ ] Datenschutzerklaerung einbinden (Impressum, Links aus App)
- [ ] E-Mail-Benachrichtigungen DSGVO-konform (kein Tracking-Pixel)
- [ ] Nutzungsbedingungen und Einwilligungsabfrage bei Registrierung

### Barrierefreiheit

- [ ] Farbkontraste pruefen (WCAG 2.1 AA)
- [ ] Tastaturnavigation vollstaendig testen
- [ ] Screenreader-Labels und Alt-Texte fuer alle interaktiven Elemente
- [ ] Schriftgroessen: kein festes px fuer Lauftext

### Qualitaet und Stabilitaet

- [ ] Alle API-Endpunkte mit Integrationstests abdecken
- [ ] Ladezeiten und Core Web Vitals messen (Ziel: LCP unter 2,5 Sekunden)
- [ ] Fehlermonitoring einrichten (Sentry)
- [ ] PWA-Installation auf iOS und Android testen

**Gate:** Vollstaendiger Pruefungsdurchgang auswertbar; DSGVO-Checkliste abgehakt; Barrierefreiheitspruefung bestanden.

## 8. Phase 4: Pilotbetrieb (Wochen 17-20)

### Beta-Start

- [ ] Kleine Lerngruppe (5 bis 15 Personen) mit Lehrkraft auswaehlen
- [ ] Testzugang bereitstellen (Aktivierungscodes ausgeben)
- [ ] Feedback-Kanal einrichten (Formular oder direkter Kontakt)
- [ ] Kritische Nutzerpfade begleiten: Registrierung, Lizenzaktivierung, erste Lerneinheit

### Feedback auswerten

- [ ] Nutzungsdaten auswerten (welche Bereiche werden genutzt, wo gibt es Abbrueche)
- [ ] Strukturiertes Feedback-Gespraech mit Lehrkraft und 2 bis 3 Schuelern
- [ ] Kritische Bugs identifizieren und priorisieren
- [ ] Inhalte auf fachliche Richtigkeit pruefen (Praxiserfahrung der Lerngruppe)

### Launch-Vorbereitung

- [ ] Kritische Bugs behoben
- [ ] Launch-Checkliste abarbeiten (siehe Abschnitt 10)
- [ ] Produktions-Deployment final einrichten
- [ ] Support-Prozess definieren (Erreichbarkeit, Reaktionszeit bei Problemen)
- [ ] Erste Aktivierungscodes fuer Verkauf bereitstellen

**Gate:** Nutzerfeedback ausgewertet; kritische Bugs behoben; Launch-Checkliste vollstaendig gruen.

## 9. Testplan

| Testart | Was wird getestet | Wann | Verantwortung |
| --- | --- | --- | --- |
| Unit Tests | Spaced-Repetition-Logik, Lizenzcode-Validierung, Auswertungslogik | Ab Phase 1, laufend | Entwickler |
| Integrationstests | API-Endpunkte (Auth, Lizenz, Fragen, Fortschritt) | Ab Phase 2, laufend | Entwickler |
| E2E-Tests | Registrierung bis erste Lerneinheit; Pruefungssimulation | Phase 3 | Entwickler |
| Barrierefreiheitspruefung | WCAG 2.1 AA: Kontraste, Tastatur, Screenreader | Phase 3 | Entwickler + manuell |
| Geraete- und Browser-Tests | iOS Safari, Android Chrome, Desktop Chrome/Firefox | Phase 3 und 4 | Entwickler + Testnutzer |
| PWA-Installationstest | Installation und Offline-Verhalten auf iOS und Android | Phase 3 | Entwickler |
| Nutzertests | Usability, Lernpfad, Fragen verstaendlich | Phase 4 (Pilot) | Lerngruppe + Lehrkraft |
| Sicherheitstest | Brute-Force-Schutz, Session-Sicherheit, Datenbankzugriffe | Phase 3 | Entwickler |

**Akzeptanzkriterien fuer Launch:**

- Keine kritischen Bugs offen
- Spaced-Repetition-Intervalle zu 100 Prozent korrekt
- Lizenzaktivierung end-to-end stabil
- Alle WCAG-2.1-AA-Kontraste erfuellt
- LCP unter 2,5 Sekunden auf mobilem Geraet

## 10. Launch-Checkliste

### Rechtliches und Datenschutz

- [ ] BVA-Freigabe vorliegend und dokumentiert
- [ ] Datenschutzerklaerung aktuell und erreichbar
- [ ] Impressum vorhanden
- [ ] AVV mit Hosting-Anbieter unterzeichnet
- [ ] Kontoloeschfunktion getestet

### Technik und Sicherheit

- [ ] HTTPS fuer alle Endpunkte erzwungen
- [ ] Rate-Limiting auf Auth- und Code-Einloese-Endpunkten aktiv
- [ ] Datenbank-Backups automatisiert und wiederhergestellt getestet
- [ ] Fehlermonitoring (Sentry) aktiv
- [ ] Produktionsumgebung von Staging getrennt
- [ ] Zugangsdaten und Secrets in Umgebungsvariablen, nicht im Code

### Inhalte

- [ ] Alle Lektionen fachlich geprueft und freigegeben
- [ ] Alle Fragen auf Aktualitaet geprueft
- [ ] Quellenangaben vollstaendig
- [ ] Amtlicher Pruefungsstoff klar von Zusatzmaterial getrennt

### Produkt

- [ ] PWA-Installation auf iOS und Android getestet
- [ ] Lizenzaktivierung end-to-end getestet
- [ ] Pruefungssimulation vollstaendig auswertbar
- [ ] Support-Kontaktmoeglichkeit sichtbar eingebunden
- [ ] Erste Aktivierungscodes bereit fuer Verkauf oder Ausgabe

## 11. V2 Roadmap (ab Woche 21)

V2 startet nach Auswertung des Pilotbetriebs. Die Reihenfolge kann sich je nach Nutzerfeedback verschieben.

| Feature | Beschreibung | Abhaengigkeit |
| --- | --- | --- |
| Lehrkraeftebereich | Kurse, Gruppen, Fortschrittsauswertung, Lernstandsberichte | V1 stabil, Nutzerfeedback |
| Sammelcodes-Frontend | Verwaltungsoberflaeche fuer Lizenzkontingente | Lehrkraeftebereich oder separat |
| Zahlungsintegration | Automatische Code-Ausgabe nach Kauf, z. B. Bizzify-Anbindung | Sammelcodes |
| Offline-Nutzung | Begrenzte Offline-Frist (vorab bestaetigt, dann 7 Tage offline moeglich) | Service Worker in V1 vorbereiten |
| 2FA | Optionale Zwei-Faktor-Authentifizierung | V1 Auth-System |
| Erweiterte Auswertungen | Gruppenstatistiken, Exportberichte, haeufige Fehler | Lehrkraeftebereich |

Fuer Offline-Nutzung empfiehlt es sich, in V1 den Service Worker bereits so aufzusetzen, dass eine spaetere Erweiterung um Offline-Caching keine Architektur-Aenderung erfordert.
