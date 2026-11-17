# NEJE 5 Plus mit A40640 (12 W) – Parameter-Referenz: Schneiden & Gravieren

Autor: Paul Simmen mit Vibe (GLM-5-latest-short), 17.11.2026

Diese Übersicht fasst die offiziellen NEJE-Parameter für das Lasermodul **A40640** (12 W optisch, Puls 12 W+ / CW 11 W+, 2 Dioden mit FAC, 450 nm, Fokus-Punkt 0,04 × 0,06 mm) auf der **NEJE 5 Plus** zusammen, ergänzt um Community-Startwerte für Gravur und Praxis-Tipps.

> **Einheiten-Falle:** NEJE-Tabellen sind in mm/min, LightBurn arbeitet in mm/s (60 mm/min = 1 mm/s). S1000 = 100 % Leistung. Alle Schneidwerte gelten **mit Air Assist 0,6–1,5 MPa**.

---

## 1. Schneiden – offizielle NEJE-Material-Datenbank

Quelle: [neje.wiki m_db](https://neje.wiki/doku.php?id=m_db) (offizielle Datenbank, Sektion «NEJE A40640»). Alle Werte bei 100 % Leistung (S1000) und korrektem Air Assist.

| Material | Stärke | Vorschub | Durchgänge |
|---|---|---|---|
| Sperrholz (plywood) | 2 mm | 480 mm/min | 1 |
| Sperrholz | 3 mm | 420 mm/min | 1 |
| Sperrholz | 4 mm | 360 mm/min | 1 |
| Sperrholz | 5 mm | 240 mm/min | 1 |
| Sperrholz | 8 mm | 120 mm/min | 1 |
| Sperrholz | 18 mm | 120 mm/min | 3 |
| Birken-Sperrholz | 3 mm | 480 mm/min | 1 |
| MDF | 3 mm | 120 mm/min | 1 |
| MDF | 5 mm | 120 mm/min | 2 |
| MDF | 8 mm | 120 mm/min | 3 |
| Schwarzes Acryl | 3 mm | 120 mm/min | 1 |
| Schwarzes Acryl | 5 mm | 120 mm/min | 2 |

### Rahmenbedingungen

- **Fokus beim Schneiden:** auf die **obere Hälfte** der Materialstärke fokussieren, nicht auf die Oberfläche ([neje.wiki m_fo](https://neje.wiki/doku.php?id=m_fo)).
- **MDF** braucht 0,6–1,5 MPa Air Assist, damit der Luftstrom das karbonisierte Material aus dem Schnittkanal bläst.
- Die Schnittstärken bis 20 mm gelten laut NEJE-5-Plus-Handbuch für basswood (Limettenholz); feuchtes oder stärker verleimtes Sperrholz schneidet deutlich langsamer ([NEJE 5 PLUS Manual](https://manuals.plus/ae/1005012308060881)).
- Hersteller-Empfehlung für lange Schneideläufe: max. **80 % Leistung** (≈9 W) verwenden, um die Dioden zu schonen ([NEJE A40640/E40 Manual](https://manuals.plus/ae/1005002782434871)).
- **Nicht schneiden:** PVC/Vinyl und andere chlorhaltige Kunststoffe (ätzende, giftige Gase); transparentes Acryl ist für Blaulicht-Dioden praktisch nicht schneidbar.

## 2. Fokus-Einstellungen (Zoom-Fokus)

Das A40640 hat einen **Zoom-Fokus** (empfohlener Bereich 30–55 mm), Einstellung mit flachem Schlitzschraubendreher am Lensring ([neje.wiki m_fo](https://neje.wiki/doku.php?id=m_fo)):

| Fokus (vom Lichtaustritt) | Fokus-Punkt | Einsatzbereich |
|---|---|---|
| ~33 mm | 0,13 × 0,13 mm | Gravur + schnelles Schneiden bis ~10 mm |
| ~55 mm | 0,18 × 0,18 mm | Dickes Schneiden bis 18–20 mm |

Faustregel: **Gravieren auf der Materialoberfläche fokussieren, Schneiden auf die obere Materialhälfte.**

## 3. Gravieren – Startwerte (Brenntiefe/Vorschub)

**Wichtig:** NEJE veröffentlicht **keine offizielle Brenntiefen-Tabelle**. Die Gravurtiefe ergibt sich physikalisch aus der Energie pro Millimeter (Leistung ÷ Vorschub), der Zahl der Durchgänge und dem Fokus. Die Tiefe «steckt» also in den Durchgängen.

Startwerte für 10–12 W optische Diodenlaser (Community-Referenz, [Optics Advisors Settings Chart](https://opticsadvisors.com/guides/laser-engraver-settings-chart/)):

| Anwendung | Leistung | Vorschub | Durchgänge | Linienabstand |
|---|---|---|---|---|
| Raster/Logo auf Birken-Sperrholz | 12–15 % | 4000–4500 mm/min | 1 | 0,08 mm |
| Raster auf MDF | 20 % | 4000 mm/min | 1 | 0,08 mm |
| Karte/Karton, leicht | 10 % | 5000 mm/min | 1 | 0,10 mm |
| Anodisiertes Aluminium (Farbe abtragen) | 100 % | 2000 mm/min | 1–2 | 0,05 mm |
| Schiefer (Coaster) | 80 % | 2500 mm/min | 1 | 0,10 mm |

Tiefe Gravuren in Holz (z. B. Inlay-Formen, 1–3 mm Tiefe):

- 100 % Leistung, 300–600 mm/min, Fokus auf Oberfläche, Air Assist für saubere Wände.
- Pro Durchgang ca. 0,5–1 mm Tiefe; Fokus nicht nachführen (ergibt konisch saubere Kanäle).
- Edelstahl: direkte Graustufen-Gravur möglich (NEJE-Werksangabe), Fokus nah (~33 mm).
- Maximale Gravurgeschwindigkeit laut NEJE-5-Plus-Handbuch: Holz 10 000 mm/min, Edelstahl 2000 mm/min.

## 4. Kalibrier-Methode (empfohlen vor jedem neuen Material)

Statt Tabellen blind zu übernehmen, auf einem Reststück der tatsächlichen Platte ein **Power-Ramp-Testmuster** gravieren (z. B. 5 Felder mit 60/70/80/90/100 % bei fixem Vorschub):

- Holzfeuchte, Leim und Holzart verschieben die Werte oft um 20–30 %.
- **Erst Geschwindigkeit anpassen, dann Leistung** – Geschwindigkeit ist der «verzeihende» Parameter.
- Das Teststück mit den effektiv verwendeten Werten beschriften und als Referenz sammeln.

## 5. Sicherheit (Laserklasse 4)

- Schutzbrille für 450 nm tragen, Maschine nie unbeaufsichtigt laufen lassen.
- Rauchabsaugung/Ventilation sicherstellen.
- **Kein PVC/Vinyl** (Chlorgase!), Löschmittel (Wasserspray) griffbereit.
- MEMS-Erschütterungssensor der NEJE 5 Plus stoppt die Maschine bei Berührung – nicht als Ersatz für Aufsicht verstehen.

## 6. Quellen

| Quelle | Inhalt |
|---|---|
| [neje.wiki – m_db](https://neje.wiki/doku.php?id=m_db) | Offizielle Material-Datenbank (Schnittwerte je Modul) |
| [neje.wiki – m_fo](https://neje.wiki/doku.php?id=m_fo) | Fokus-Anleitung A40640 (33/55 mm), Air-Assist-Hinweise |
| [NEJE 5 PLUS A40640 User Manual](https://manuals.plus/ae/1005012308060881) | Maschinenspezifikationen, max. Schnittdicken |
| [NEJE A40640/E40 Module Manual](https://manuals.plus/ae/1005002782434871) | Modulspezifikationen, 80 %-Empfehlung |
| [Optics Advisors – Laser Engraver Settings Chart](https://opticsadvisors.com/guides/laser-engraver-settings-chart/) | Community-Gravur-Startwerte nach Material/Wattage |
| [lasersettings.fr – NEJE](https://lasersettings.fr/en/brand/neje) | Community-Datenbank mit NEJE-Einstellungen (Material × Stärke) |

> Konfidenz: Schneidtabelle hoch (Herstellerangabe, gilt für korrekten Fokus + Air Assist); Gravur-Startwerte mittel (Community, materialabhängig).
