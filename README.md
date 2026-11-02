
# Muscle Beast

Muscle Beast ist ein minimalistischer Trainings-Tracker als Progressive Web App (PWA).

## Funktionen

- Eigene Übungen anlegen und bearbeiten
- Trainingseinheiten mit Datum und Namen speichern
- Gewicht und Wiederholungen pro Satz protokollieren
- Trainingshistorie je Übung nachvollziehen
- Persönliche Rekorde anhand des höchsten Einzelgewichts anzeigen
- Gesamtdaten als JSON sichern und wiederherstellen
- Trainingsdaten als CSV exportieren
- Offline-Nutzung über einen Service Worker
- Lokale Speicherung mit IndexedDB
- Für iPhone und Desktop optimierte Oberfläche

## Dateien

- `index.html` – App und Benutzeroberfläche
- `manifest.webmanifest` – PWA-Konfiguration
- `sw.js` – Offline-Cache
- `icon.svg` – App-Symbol
- `.nojekyll` – GitHub-Pages-Hinweis

## Lokal testen

Ein Service Worker funktioniert nicht zuverlässig über `file://`.
Starte deshalb einen lokalen Webserver, zum Beispiel:

```bash
python3 -m http.server 8000
```

Öffne danach:

http://localhost:8000

## Veröffentlichung mit GitHub Pages

1. Erstelle ein neues GitHub-Repository namens `MuscleBeast`.
2. Lade alle Projektdateien in das Hauptverzeichnis hoch.
3. Öffne im Repository **Settings → Pages**.
4. Wähle unter Build and deployment die Option **Deploy from a branch**.
5. Wähle den Branch `main` und den Ordner `/ (root)`.
6. Speichere die Einstellung.
7. Öffne nach der Veröffentlichung die angezeigte GitHub-Pages-Adresse.

## Auf dem iPhone verwenden

1. Öffne die veröffentlichte HTTPS-Adresse in Safari.
2. Tippe auf das Teilen-Symbol.
3. Wähle **Zum Home-Bildschirm**.
4. Bestätige mit **Hinzufügen**.
5. Starte Muscle Beast über das neue Home-Bildschirm-Symbol.

## Datensicherung

Unter **Einstellungen** kannst du:

- JSON exportieren: vollständige Sicherung inklusive Übungen, Workouts und Sätzen.
- CSV exportieren: tabellarische Trainingsdaten.
- JSON importieren: stellt eine zuvor exportierte Sicherung wieder her.

Beim Import werden die bestehenden Daten ersetzt.

## Datenschutz und Speicher

Alle Trainingsdaten werden lokal im Browser in IndexedDB gespeichert.
Es gibt kein Benutzerkonto und keinen Cloud-Dienst.

Wichtig: Website-Daten können durch das Löschen von Browserdaten verloren gehen.
Erstelle deshalb regelmäßig eine JSON-Sicherung.

## ZIP erstellen

### macOS / Linux

Im übergeordneten Ordner ausführen:

```bash
zip -r MuscleBeast.zip MuscleBeast
```

### Windows

Rechtsklick auf den Ordner `MuscleBeast` → **Senden an → ZIP-komprimierter Ordner**.

### iPhone

Lege die Dateien in der Dateien-App in einem Ordner `MuscleBeast` ab.
Halte den Ordner gedrückt und wähle **Komprimieren**.

## Hinweis zum Projektstatus

Dies ist eine eigenständige PWA-Grundversion. Vor einer intensiven Nutzung sollten insbesondere Offline-Verhalten, JSON-Wiederherstellung und iPhone-Darstellung auf dem Zielgerät getestet werden.
