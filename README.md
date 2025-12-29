# ShortUploader (YouTube Shorts + TikTok) – Desktop Uploader mit Queue & Scheduling

ShortUploader ist ein Windows-Desktopprogramm, das Short-Videos aus einem Ordner in eine Upload-Queue lädt und nacheinander zu:
- **YouTube Shorts** (YouTube Data API v3)
- **TikTok** (TikTok Developer: Login Kit + Content Posting API)

hochlädt. Nach erfolgreichem Upload werden Videos automatisch in einen `uploaded/`-Ordner verschoben (bei Fehlern optional in `failed/`). Das Programm zeigt Status-Logs im UI und besitzt einen Retry-Mechanismus.

> Ziel: Upload automatisieren, Scheduling sauber abbilden, Dateien nach Upload wegorganisieren, ohne dass das Programm dauerhaft offen sein muss (je nach Modus).

---

## Features

- Ordner auswählen → Videos werden in eine **Queue** geladen
- Upload nacheinander (konfigurierbar)
- **Retry** (z. B. 3 Versuche mit Backoff)
- **Logging** (UI + Datei-Logs)
- Nach Upload: Verschieben nach `uploaded/` (und optional `failed/`)
- **YouTube Scheduling (plattformseitig)** via `publishAt` (Upload jetzt, Veröffentlichung später)
- **Interne Planung** (Slots/Zeitplan durch das Tool)

---

## Voraussetzungen

### System
- Windows 10/11 (x64 empfohlen)
- Internetverbindung

### Für Entwickler / Selbst-Build
- .NET SDK **8+** (zum Bauen der EXE)

Wenn du nur die fertige EXE nutzt, ist kein .NET Runtime-Zwang nötig (Self-contained Build).

---

## Schnellstart (Endnutzer)

1. **Programm starten**
2. **Video-Ordner auswählen**
3. Plattform(en) konfigurieren:
   - YouTube verbinden (OAuth)
   - TikTok verbinden (Developer OAuth)
4. Optional: Scheduling aktivieren (intern oder plattformseitig)
5. **Start Upload** drücken

Nach erfolgreichem Upload werden Videos nach `uploaded/` verschoben.

---

## TikTok Setup (Developer) – Pflicht

TikTok Upload benötigt eine TikTok Developer App.

### 1) TikTok Developer App anlegen/konfigurieren
Im TikTok Developer Portal:
- **Platform:** Desktop
- **Products aktivieren:**
  - Login Kit
  - Content Posting API (Direct Post)
- **Redirect URI (Desktop Loopback):**
  - `http://127.0.0.1:*/callback/`
- **Scopes:**
  - `user.info.basic`
  - `video.publish`

### 2) Review / Production
Für Posting-Funktionen kann TikTok eine **Review** verlangen. Stelle sicher:
- App **nicht** im Status `Draft`
- Terms of Service & Privacy Policy öffentlich erreichbar und von einer Homepage verlinkt

Wenn TikTok beim Login „client_key“ meldet, ist die App häufig noch `Draft` oder nicht für Production freigegeben.

### 3) In der App eintragen
Im Programm trägst du ein:
- Client Key
- Client Secret
- Scopes (z. B. `user.info.basic,video.publish`)
Dann klickst du auf **TikTok Login**.

> Tokens werden lokal gespeichert (verschlüsselt) und automatisch refreshed.

---

## YouTube Setup – Pflicht

YouTube Upload nutzt die **YouTube Data API v3** (Google Cloud).

### 1) Google Cloud Projekt
- YouTube Data API v3 aktivieren
- OAuth Consent Screen konfigurieren
- OAuth Client erstellen (Desktop)

### 2) In der App verbinden
- In ShortUploader **YouTube Login** starten
- Zugriff erlauben
- Danach kann die App uploaden und (optional) YouTube-Scheduling setzen

---

## Scheduling – zwei Arten (wichtig)

### 1) Interne Programm-Planung
Das Programm entscheidet:
- wie viele Videos pro Tag
- zu welchen Uhrzeiten


