# Meditations-App Archiv

Volle Historie, wird nur ergänzt, nie gekürzt.

## Session 1, 26.11.2026
- Grilling (6 Fragen): Web-App statt echter App (dauerhaft ohne Entwicklerkonto), Signal als leiser Ton, iPhone darf sich sperren (ganze Sitzung als eine WAV-Datei), Atmen ohne Führung nur mit Start-/Endton, Erinnerungen um Minute 5/10/15 je ±60 s zufällig, sehr kurze Klangschale (selbst erzeugt, f0 520 Hz, 4 unharmonische Teiltöne), Ort GitHub Pages.
- Nachbau mit eigenem Code. Auslesen einer fremden App wurde abgelehnt (Kopierschutz, § 95a UrhG).
- Gebaut: `docs/index.html` (Oberfläche + Audio-Erzeugung, WAV 16 kHz mono, 39-49 MB je Sitzung), `docs/sw.js` (offline), Manifest, Symbole (Ring, mit ffmpeg erzeugt).
- Gemessen: Tonzeitpunkte in allen 3 Varianten mit ffmpeg silencedetect, stimmen (Beispiel ohne Atmen: Erinnerungen bei 6,03 / 10,17 / 14,24 min). Pegel: Start -8 dB, Erinnerung -19,5 dB, Ende -9 dB.
- GitHub Pages im privaten Repo abgelehnt (HTTP 422, Tarif Free). Repo auf öffentlich gestellt, gitleaks 0 Funde. Seite live, alle Dateien HTTP 200.
- Danach Timer-Schrift heller (#a7b0b8, Phase #7d868e), sw VERSION v2.
- Nicht geprüft: Knöpfe im Browser (Test-Browser belegt), Ton bei gesperrtem iPhone.
- Ordner stammt aus der alten Vorlage `ai-os-main`, nicht `ai-os-christoph`.

## Session 2, 26.11.2026
- Anlass: Christoph hatte nach dem Probelauf den Eindruck, das iPhone werde warm und verliere viel Akku.
- Code geprüft und in Chrome am Mac gemessen: Audio erzeugen 80 ms (46,3 MB, Fall 5 Min Atmen), ein Timer-Schritt 0,003 ms (läuft 2-mal je Sekunde), Last des Browsers beim Abspielen rund 6 % und damit wie im Ruhezustand. Kein Stromfresser im Code gefunden. Am iPhone (Safari) nicht gemessen, Ursache dort offen.
- Erinnerungstöne auf Christophs Wunsch leiser und tiefer: `VOL_REMINDER` 0,12 → 0,09 (gemessen -22 dB statt -19,5 dB), eigener Grundton `F0_REMINDER` 347 Hz (vorher 520 Hz). Start- und Schlusston unverändert (520 Hz, -8 / -9 dB). sw VERSION v3.
- Knöpfe in Chrome durchgeklickt: alle 3 Starts, Stopp und die Markierung „zuletzt gewählt“ laufen.
- Fortsetzung 27.11.2026, Christophs Wunsch: Erinnerungstöne „deutlich tiefer“ (`F0_REMINDER` 347 → 260 Hz, Pegel -22,2 dB). Neu: 3 Minuten Entspannen nach der Meditation (`REST_MIN`). Meditation endet mit 2 Tönen (`MED_END_STRIKES`), das Entspannen mit 3 Tönen (`REST_END_STRIKES`). Anzeige: Phase „Entspannen“ mit Restzeit. Im Browser gemessen (alle 3 Varianten): Töne bei Minute 20,00 / 20,07 und 23,00 / 23,07 / 23,13 ab Meditationsstart, Datei 42,6 / 46,3 / 51,8 MB, Dauer ohne Atmen 23,28 min. sw VERSION v4.
