# Meditations-App Roadmap

**Stack**: eine Web-App (HTML + JavaScript, ohne fremde Pakete), Ordner `docs/`, GitHub Pages
**Stand**: 26.11.2026, erste Fassung gebaut, Test auf dem iPhone offen
**Nur für Christoph privat.** Eigener Code, nichts aus der TM-App übernommen.

## Ziel
- Optional 2 oder 5 Minuten Atmen (nur Ton am Anfang und Ende), dann 20 Minuten Meditation.
- Um Minute 5, 10 und 15 ein sehr leiser, kurzer Klangschalen-Ton (je bis 1 Minute zufällig versetzt), damit Christoph zurückkommt, wenn er in Gedanken ist.
- Ende: 3 kurze Klangschalen-Töne.

## Entscheidungen (Grilling 26.11.2026)
- Web-App statt echter iPhone-App: läuft dauerhaft ohne Entwicklerkonto und ohne Neu-Aufspielen.
- Signal nur als leiser Ton (Augen sind zu, Web-Apps können auf dem iPhone nicht vibrieren).
- iPhone darf sich sperren: Die ganze Sitzung wird beim Tippen als EINE Audiodatei (WAV, 16 kHz, 39-49 MB im Speicher) erzeugt und abgespielt.
- Atemübung ohne Führung, nur Start- und Endton.
- Erinnerung leicht versetzt, nicht genau alle 5 Minuten.
- Klang: sehr kurze Klangschale, am Computer erzeugt (keine fremden Klänge).
- Ort: GitHub Pages.

## Geprüft (26.11.2026)
- Zeitpunkte der Töne in allen 3 Varianten gemessen (Stillephasen mit ffmpeg): stimmen.
- Pegel: Start -8 dB, Erinnerung -19,5 dB, Ende -9 dB.

## Offen
- [ ] Test auf dem iPhone: läuft der Ton bei gesperrtem Bildschirm aus der Startbildschirm-App weiter? Plan B: Bildschirm bleibt schwarz an (Wake Lock).
- [ ] Klang und Lautstärke nach dem ersten echten Durchgang anpassen.

## Hinweis
Der Ordner wurde aus der alten Vorlage `ai-os-main` angelegt (englische CLAUDE.md, Skill-Kopien in `local-only/`), nicht aus `ai-os-christoph`.
