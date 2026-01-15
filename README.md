ShortUploader

ShortUploader ist ein Desktop-Programm für Windows, mit dem Short-Videos effizient vorbereitet und automatisiert hochgeladen werden können.
Der Fokus liegt auf Batch-Workflows, lokaler KI-Unterstützung und voller Nutzerkontrolle vor dem Upload.

Hauptfunktionen

Warteschlange (Queue) für mehrere Videos

Automatische Verarbeitung und Abarbeitung der Queue

Verschieben erfolgreich verarbeiteter Dateien in einen uploaded/-Ordner

Status- und Fehler-Logging im UI

Retry-Mechanismus bei Fehlern

Lokale KI-Unterstützung (Smart Lite) zur Generierung von:

Videotiteln

Hashtags

Alle automatisch erzeugten Inhalte sind vor dem Upload editierbar

Smart Lite (lokale KI)

ShortUploader nutzt lokale KI über Ollama, um Videoinhalte anhand von Frames zu analysieren und daraus kreative, abwechslungsreiche Titel und Hashtags zu erzeugen.

Eigenschaften von Smart Lite

100 % lokal (keine Cloud-KI, keine API-Kosten)

Analyse basiert ausschließlich auf Bildmaterial (keine Audio-Analyse)

Anti-Duplikat-Logik:

Vermeidet identische oder sehr ähnliche Titel bei mehreren Videos

Erzwingt variierende Titel-Längen und Stilrichtungen

Fallback-Mechanismen:

Funktioniert auch bei unvollständigen oder nicht-strikten Modell-Antworten

Stabil für Batch-Verarbeitung vieler Videos

Voraussetzungen für Smart Lite
Ollama

Für die KI-Funktionen wird Ollama benötigt.

Ollama muss lokal installiert und aktiv sein

Empfohlenes Modell:

gemma3:4b


Dieses Modell bietet:

stabile Vision-Unterstützung

gute Performance auch ohne starke GPU

Unterstützung für mehrere Bilder pro Anfrage

Andere Modelle können funktionieren, werden aber nicht offiziell empfohlen.

FFmpeg (Hinweis)

ShortUploader verwendet FFmpeg intern zur Extraktion einzelner Frames aus Videos.

FFmpeg wird vom Programm genutzt, nicht manuell bedient

Die Bereitstellung von FFmpeg erfolgt projektintern
(kein separater Download für Endnutzer erforderlich)

Nutzerkontrolle & Transparenz

ShortUploader postet niemals automatisch ohne Zustimmung.

Alle KI-Vorschläge sind sichtbar und editierbar

Titel, Hashtags und weitere Metadaten können manuell angepasst werden

Uploads starten erst nach expliziter Nutzeraktion

Keine versteckten Uploads, keine Hintergrundaktionen

Datenschutz & Sicherheit

Alle Daten bleiben lokal auf dem Gerät

Keine Übertragung an Drittanbieter-KI-Dienste

Keine Speicherung oder Weitergabe persönlicher Nutzerdaten

KI-Modelle laufen ausschließlich lokal über Ollama

Zielgruppe

ShortUploader richtet sich an:

Content-Creator

Social-Media-Manager

Nutzer mit vielen Short-Videos

Anwender, die Wert auf lokale Verarbeitung und Kontrolle legen

Projektstatus

Aktive Entwicklung

Fokus auf Stabilität, Batch-Workflows und lokale KI

Erweiterungen und Optimierungen geplant
