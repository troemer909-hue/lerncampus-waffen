# Waffensachkunde-Lernapp

Progressive Web App zur Vorbereitung auf die Sachkundeprüfung nach § 7 WaffG.

## Dokumentation

| Dokument | Beschreibung |
| --- | --- |
| [docs/konzept.md](docs/konzept.md) | Überarbeitetes Produktkonzept (Ziele, Lernstruktur, Datenmodell, DSGVO, MVP-Scope) |
| [docs/entwicklungsplan.md](docs/entwicklungsplan.md) | Entwicklungsplan mit Phasen, Tech-Stack, Testplan und Launch-Checkliste |

## Kurzübersicht

**Produkt:** Installierbare PWA für Einzel- und Kursnutzung  
**Lernbereiche:** I. Waffenrecht · II. Waffentechnik · III. Sicherer Umgang · IV. Notsignalmittel  
**Kernfunktionen V1:** Lerneinheiten, Übungsmodus (MC + Freitext), Spaced Repetition (1/3/7/14 Tage), Prüfungssimulation, Lizenzcode-System  
**Tech-Stack:** React + TypeScript, Vite PWA, Tailwind CSS, Node.js, MySQL, Prisma, JWT  
**Hosting:** EU-Region (DSGVO-konform)

## Kritischer Pfad

Vor Entwicklungsstart muss die schriftliche Freigabe des Bundesverwaltungsamts (BVA) zur Nutzung des amtlichen Fragenkatalogs vorliegen.

## Phasen

| Phase | Wochen | Ziel |
| --- | --- | --- |
| 0 Vorbereitung | 1–3 | Rechtsklärung, Datenmodell, Tech-Stack |
| 1 Grundgerüst | 4–7 | PWA, Auth, Lizenzcode-Backend |
| 2 Lernmodul | 8–13 | Lektionen, Fragen, Spaced Repetition |
| 3 Prüfungsmodus | 14–16 | Simulation, DSGVO, Barrierefreiheit |
| 4 Pilotbetrieb | 17–20 | Beta, Feedback, Launch |
| V2 | ab 21 | Lehrbereich, Zahlung, Offline |
