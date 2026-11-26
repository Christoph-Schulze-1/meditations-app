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
