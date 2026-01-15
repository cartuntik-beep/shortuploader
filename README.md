# ShortUploader

ShortUploader ist ein **Desktop-Programm für Windows**, mit dem Short-Videos effizient vorbereitet und automatisiert hochgeladen werden können.  
Der Fokus liegt auf **Batch-Workflows**, **lokaler KI-Unterstützung** und **voller Nutzerkontrolle** vor dem Upload.

---

## ✨ Hauptfunktionen

- Warteschlange (Queue) für mehrere Videos
- Automatische Verarbeitung und Abarbeitung der Queue
- Verschieben erfolgreich verarbeiteter Dateien in einen `uploaded/`-Ordner
- Status- und Fehler-Logging im UI
- Retry-Mechanismus bei Fehlern
- **Lokale KI-Unterstützung (Smart Lite)** zur Generierung von:
  - Videotiteln
  - Hashtags
- Alle automatisch erzeugten Inhalte sind **vor dem Upload editierbar**

---

## 🤖 Smart Lite (lokale KI)

ShortUploader nutzt **lokale KI über Ollama**, um Videoinhalte anhand von Frames zu analysieren und daraus **kreative, abwechslungsreiche Titel und Hashtags** zu erzeugen.

### Eigenschaften von Smart Lite

- 100 % lokal (keine Cloud-KI, keine API-Kosten)
- Analyse basiert ausschließlich auf Bildmaterial (keine Audio-Analyse)
- Anti-Duplikat-Logik:
  - Vermeidet identische oder sehr ähnliche Titel bei mehreren Videos
  - Erzwingt variierende Titel-Längen und Stilrichtungen
- Fallback-Mechanismen:
  - Funktioniert auch bei unvollständigen oder nicht-strikten Modell-Antworten
- Stabil für Batch-Verarbeitung vieler Videos

---

## ⚙️ Voraussetzungen für Smart Lite

### Ollama

Für die KI-Funktionen wird **Ollama** benötigt.

- Ollama muss lokal installiert und aktiv sein
- **Empfohlenes Modell:**

```text
gemma3:4b
