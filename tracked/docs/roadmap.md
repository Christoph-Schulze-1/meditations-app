# Meditations-App Roadmap

**Stack**: eine Web-App (HTML + JavaScript, ohne fremde Pakete), Ordner `docs/`, GitHub Pages
**Stand**: 26.11.2026, erste Fassung live unter https://christoph-schulze-1.github.io/meditations-app/, Test auf dem iPhone offen
**Archiv**: `roadmap-ARCHIV.md` (volle Historie, nur per grep)
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
- [ ] Knöpfe im Browser einmal durchklicken (26.11. nicht geprüft, Test-Browser war belegt).
- [ ] Timer-Schrift-Helligkeit (26.11. heller gemacht) auf dem iPhone bestätigen.

## Hinweis
Der Ordner wurde aus der alten Vorlage `ai-os-main` angelegt (englische CLAUDE.md, Skill-Kopien in `local-only/`), nicht aus `ai-os-christoph`.

## Regeln
- Repo ist ÖFFENTLICH (GitHub Free erlaubt Pages nur so, 26.11.2026). Nichts Privates in Repo-Dateien schreiben.
- Bei jeder Änderung an `docs/` die `VERSION` in `docs/sw.js` erhöhen, sonst zeigt das iPhone die alte Fassung. Die neue Fassung erscheint erst beim zweiten Öffnen.

## Letzte Session
- 26.11.2026 (Session 1): Grilling, Web-App gebaut, Töne gemessen, Repo + GitHub Pages live, Timer-Schrift heller (v2). Details: Archiv, Session 1.

## Letzte Übergabe
```
Übergabe aus der Session vom 26.11.2026 (Meditations App):
Woran wir waren: Meditations-Web-App gebaut und live: https://christoph-schulze-1.github.io/meditations-app/
(Ordner docs/, eine Datei index.html mit Audio-Erzeugung, sw.js für offline). Timer-Schrift heller (sw VERSION v2).
Zuerst lesen: tracked/docs/roadmap.md
Als Nächstes / offen:
- iPhone-Test: „Ohne Atmen“, iPhone sperren, kommt die leise Erinnerung um Minute 5 (±1)? Sonst Plan B Wake Lock.
- Helligkeit der Timer-Schrift auf dem iPhone bestätigen.
- Klang/Lautstärke nach erstem Durchgang anpassen.
- Knöpfe im Browser einmal durchklicken.
Prüfer: Tonzeitpunkte und Pegel mit ffmpeg/Python gemessen (stimmen); Seite und alle Dateien HTTP 200. Knöpfe und Sperrbildschirm: ungeprüft.
Hinweis: Repo öffentlich (GitHub Free), nichts Privates hineinschreiben.
```
