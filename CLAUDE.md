# Bäckerei 2000 — Projektnotizen

Statische Website (6 HTML-Seiten, kein Build-Schritt), deployt über GitHub Actions
nach GitHub Pages: https://cs67pzk79g-sys.github.io/1.0/

Alle Inhalte sind erfunden. Konsistent gehaltene Eckdaten:

- 2000 von Marga Brandt eröffnet, seit 2014 führt Sohn Jonas Brandt (Bäckermeister)
- Sauerteig „Berta", angesetzt 2014 · Steinofen „Alfred", Baujahr 1998
- Mehl der Rosdorfer Mühle · Kaffee von Elbgold · 18 Std kalte Teigführung
- Team: Jonas Brandt, Marlene Kittel, Aylin Yücel, Piet Ostermann
- Bahnhofsplatz 1, 37073 Göttingen · 0551 12 34 567

**Keine erfundenen Kundenbewertungen und keine Stockfotos als „unser Team".**

## Arbeitsweise

- Entwicklung auf `claude/live-preview-webdesign-i0lkjm`, dann PR nach `main`
- Deploy läuft automatisch beim Merge (`.github/workflows/pages.yml`)
- Vor jedem Commit: Chromium-Screenshots bei 1280px und 390px, auf horizontalen
  Überlauf prüfen
- **Das Layout der Datum-/Uhrzeit-Felder in `reservierung.html` nicht anfassen** —
  feste 9.5rem je Feld, zentriert, 1.75rem Abstand, Umbruch bei 600px. Hat mehrere
  Anläufe gekostet. Kein zweispaltiges Seitenraster, das die Formularbreite verringert.

## Offene Vorhaben (vom Nutzer)

- [ ] Impressum-Bereich verbessern (`impressum.html`, noch im alten schlichten Zustand)
- [ ] AGB-Pop-up — AGB-Text existiert noch gar nicht
- [ ] Logo ausbessern (Inline-SVG im Header aller Seiten + `favicon.svg`, gleicher Pfad)
- [ ] Datenschutz überarbeiten (`datenschutz.html`, 7 Abschnitte vorhanden, unbearbeitet)

## Launch-Checkliste (Stand: 28.08.2026)

Bei künftigen Änderungen im Blick behalten und den Nutzer an Offenes erinnern.

Erledigt: klarer CTA · interne Links · Antwortzeitversprechen · eigene Seitentitel ·
Karte + Anfahrt · Datenschutzseite vorhanden

| Offen | Punkt | Notiz |
|---|---|---|
| [ ] | Meta-Beschreibungen | fehlen auf allen 6 Seiten — größter SEO-Hebel |
| [ ] | Local Schema (JSON-LD) | `Bakery`/`LocalBusiness` mit `openingHours`; zweitgrößter Hebel |
| [ ] | `lang="de"` | es gibt gar kein `<html>`-Tag auf den Seiten |
| [ ] | robots.txt | fehlt (sitemap.xml ebenfalls) |
| [ ] | Eigene 404-Seite | fehlt |
| [ ] | Open-Graph-Vorschaubild | keine `og:`-Tags |
| [ ] | Breadcrumbs | bisher nur „← Zurück zur Startseite" |
| [ ] | 5 FAQs | Info-Karten vorhanden, aber kein FAQ-Format |
| [ ] | Danke-Seite | Reservierung öffnet nur das Mailprogramm |
| [ ] | Fester Kontakt-Button | Tel/Mail auf 5 Seiten, Öffnungszeiten-Seite hat keinen |
| [ ] | Team-Fotos | derzeit Monogramm-Kreise statt Fotos |

Bewusst nicht umgesetzt:

- **Echte Bewertungen** — bei einer erfundenen Bäckerei nicht ehrlich möglich
- **Google Analytics** — kollidiert mit `datenschutz.html` Abschnitt 3 („Keine Cookies,
  keine Analyse-Tools"); bräuchte Cookie-Banner und angepassten Datenschutztext
- **Kundenprojekte/Referenzen** — Agentur-Punkt, für eine Bäckerei ist das die Speisekarte
- **Alt-Texte** — es gibt keine Bilddateien; alle Grafiken sind Inline-SVG mit `aria-hidden`
