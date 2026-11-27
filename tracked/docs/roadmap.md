# Meditations-App Roadmap

**Stack**: eine Web-App (HTML + JavaScript, ohne fremde Pakete), Ordner `docs/`, GitHub Pages
**Stand**: 27.11.2026, Fassung v4 live unter https://christoph-schulze-1.github.io/meditations-app/ (per curl geprüft 27.11.2026). Christoph hat am iPhone einen Probelauf gemacht (Eindruck: warm, viel Akku). Ob der Ton bei gesperrtem iPhone weiterläuft, hat er nicht gemeldet.
**Archiv**: `roadmap-ARCHIV.md` (volle Historie, nur per grep)
**Nur für Christoph privat.** Eigener Code, nichts aus der TM-App übernommen.

## Ziel
- Optional 2 oder 5 Minuten Atmen (nur Ton am Anfang und Ende), dann 20 Minuten Meditation.
- Um Minute 5, 10 und 15 ein sehr leiser, kurzer Klangschalen-Ton (je bis 1 Minute zufällig versetzt), damit Christoph zurückkommt, wenn er in Gedanken ist.
- Ende der Meditation: 2 kurze Klangschalen-Töne. Danach 3 Minuten Entspannen, am Ende 3 Töne (Christoph 27.11.2026, seit v4).

## Entscheidungen (Grilling 26.11.2026)
- Web-App statt echter iPhone-App: läuft dauerhaft ohne Entwicklerkonto und ohne Neu-Aufspielen.
- Signal nur als leiser Ton (Augen sind zu, Web-Apps können auf dem iPhone nicht vibrieren).
- iPhone darf sich sperren: Die ganze Sitzung wird beim Tippen als EINE Audiodatei (WAV, 16 kHz, 43-52 MB im Speicher, gemessen 27.11.2026) erzeugt und abgespielt.
- Atemübung ohne Führung, nur Start- und Endton.
- Erinnerung leicht versetzt, nicht genau alle 5 Minuten.
- Klang: sehr kurze Klangschale, am Computer erzeugt (keine fremden Klänge).
- Ort: GitHub Pages.

## Geprüft
- 26.11.2026 (Fassung v1): Zeitpunkte der Töne in allen 3 Varianten gemessen (Stillephasen mit ffmpeg): stimmen.
- Pegel: Start -8 dB, Erinnerung -22 dB (bis v2: -19,5 dB), Ende -9 dB.
- Erinnerung seit v3 tiefer: Grundton 347 Hz statt 520 Hz (Christoph 26.11.2026: „etwas leiser, tiefere Klangschale“). Seit v4 noch tiefer: 260 Hz, eine Oktave unter dem Startton (Christoph 27.11.2026: „deutlich tiefer“). Start- und Schlusston bleiben bei 520 Hz. Im Browser gemessen.
- v4 (27.11.2026) in allen 3 Varianten im Browser gemessen: 2 Töne bei Minute 20,00 und 20,07, 3 Töne bei Minute 23,00 / 23,07 / 23,13. Anzeige zeigt „Entspannen“ mit Restzeit. Datei jetzt 43-52 MB.
- Knöpfe (alle 3 Starts, Stopp, „zuletzt gewählt“) in Chrome durchgeklickt: laufen.
- Akku/Wärme (Christophs Eindruck nach dem Probelauf): Im Code kein Stromfresser gefunden. Gemessen in Chrome am Mac: Audio erzeugen 80 ms, ein Timer-Schritt 0,003 ms, Browser-Last beim Abspielen wie im Ruhezustand (rund 6 %). Am iPhone selbst nicht gemessen.

## Offen
- [ ] Test auf dem iPhone: läuft der Ton bei gesperrtem Bildschirm aus der Startbildschirm-App weiter? Plan B: Bildschirm bleibt schwarz an (Wake Lock).
- [ ] Akku/Wärme: am iPhone unter Einstellungen > Batterie nachsehen, wie viel Prozent die App (oder Safari) nach einem Durchgang zeigt und ob „Bildschirm an“ oder „Hintergrund“ dabeisteht. Erst danach etwas umbauen.
- [ ] Neue Erinnerungstöne (v4, 260 Hz, -22 dB) auf dem iPhone anhören: noch hörbar über den Lautsprecher?
- [ ] Timer-Schrift-Helligkeit (26.11. heller gemacht) auf dem iPhone bestätigen.

## Hinweis
Der Ordner wurde aus der alten Vorlage `ai-os-main` angelegt (englische CLAUDE.md, Skill-Kopien in `local-only/`), nicht aus `ai-os-christoph`.

## Regeln
- Repo ist ÖFFENTLICH (GitHub Free erlaubt Pages nur so, 26.11.2026). Nichts Privates in Repo-Dateien schreiben.
- Bei jeder Änderung an `docs/` die `VERSION` in `docs/sw.js` erhöhen, sonst zeigt das iPhone die alte Fassung. Die neue Fassung erscheint erst beim zweiten Öffnen.
- Ein Push auf `main` ist der Livegang (GitHub Pages aus `docs/`). Danach per curl prüfen, ob `sw.js` die neue VERSION zeigt (dauert bis etwa 1 Minute).
- Töne nach jeder Klang-Änderung messen (eingeführt 27.11.2026, Anlass: Töne zweimal geändert): `docs/index.html` per `file://` in Chrome öffnen, `buildSession(n)` auswerten (Pegel und Grundton je Ton). Genauer Weg: Archiv, Session 2.
- Akku/Wärme: erst die Zahl vom iPhone, dann umbauen (27.11.2026, Anlass: im Code war kein Stromfresser zu finden).

## Letzte Session
- 26./27.11.2026 (Session 2): Akku-Frage geprüft (kein Stromfresser im Code, am iPhone offen). Erinnerungstöne leiser (-22 dB) und deutlich tiefer (260 Hz). Neu: nach 20 Minuten 2 Töne, dann 3 Minuten Entspannen, am Ende 3 Töne (v4). Knöpfe durchgeklickt. Projekt aus dem Router genommen (privat). Details: Archiv, Session 2.

## Letzte Übergabe
```
Übergabe aus der Session vom 27.11.2026 (Meditations App):
Woran wir waren: Meditations-Web-App, Fassung v4 live: https://christoph-schulze-1.github.io/meditations-app/
Neu in dieser Session: Erinnerungstöne leiser (-22 dB) und deutlich tiefer (260 Hz). Nach 20 Min Meditation 2 Töne,
dann 3 Min Entspannen, am Ende 3 Töne. Akku/Wärme geprüft: im Code kein Stromfresser gefunden, nichts umgebaut.
Zuerst lesen: tracked/docs/roadmap.md
Als Nächstes / offen:
- Akku/Wärme: Zahl vom iPhone fehlt (Einstellungen > Batterie > „Meditation“ oder Safari, Prozent und „Bildschirm an“/„Hintergrund“). Erst danach umbauen.
- iPhone-Test: „Ohne Atmen“, iPhone sperren, läuft der Ton weiter? Sonst Plan B Wake Lock.
- Erinnerungstöne (260 Hz, -22 dB) am iPhone anhören: über den Lautsprecher noch hörbar?
- Helligkeit der Timer-Schrift auf dem iPhone bestätigen.
Prüfer: Töne in allen 3 Varianten im Browser gemessen (Minute 20,00/20,07 und 23,00/23,07/23,13, Erinnerung 260 Hz bei -22 dB);
Knöpfe in Chrome durchgeklickt; live per curl geprüft (sw.js v4). Am iPhone: alles ungeprüft. Akku-Ursache: ungeprüft.
Hinweis: Repo öffentlich (GitHub Free), nichts Privates hineinschreiben. Die App zweimal öffnen, dann erst kommt die neue Fassung.
```
