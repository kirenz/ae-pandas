# Prüfung mit Python 3.14

Stand: 07.11.2026. Die Vorlage verwendet uv und Python 3.14 (`>=3.14,<3.15`). Die Prüfung erfolgte lokal auf macOS mit CPython 3.14.9. Push und Deployment erfolgten nicht.

## Umgebung

`uv lock` und `uv sync --locked` waren erfolgreich. Der Kernel `data-analytics` wurde mit `--sys-prefix` innerhalb von `.venv` eingerichtet. Die Notebook-Metadaten nennen die tatsächlich geprüfte Python-Version und den Kernel „Python 3.14 (Data Analytics)“.

| Paket | Geprüfte Version |
|---|---|
| pandas | 2.3.3 |
| numpy | 2.5.4 |
| matplotlib | 3.11.2 |
| scikit-learn | 1.9.1 |
| altair | 6.3.0 |
| openpyxl | 3.1.5 |
| ipykernel | 7.4.0 |
| nbclient | 0.11.0 |

pandas bleibt in Version 2, weil die Datentypaufgabe Zeichenketten als `object` behandelt. Die Mindestversion 2.3.3 unterstützt Python 3.14. Ein zusätzlicher Importtest zeigte bei Altair 5.5.0 einen `TypedDict`-Fehler unter Python 3.14. Altair wurde daher auf `>=6,<7` angehoben. Mit Altair 6.3.0 wurden Import und Erzeugung einer Diagrammspezifikation erfolgreich geprüft.

## Notebook-Prüfung

Alle sechs Notebooks wurden in temporären Arbeitsverzeichnissen vollständig über einen echten Python-3.14-Kernel ausgeführt. Die 18 Aufgabenstellen erhielten ausschließlich in temporären Kopien Lösungen. Die vorhandenen Prüfzellen liefen unverändert mit. Auch die Excel-Datei aus dem ersten Notebook wurde dort erzeugt und wieder eingelesen.

| Notebook | Temporär ergänzte Aufgabenstellen | Ergebnis |
|---|---:|---|
| `1_import_store.ipynb` | 3 | Vollständiger Lauf erfolgreich |
| `2_columns.ipynb` | 4 | Vollständiger Lauf erfolgreich |
| `3_data_types.ipynb` | 2 | Vollständiger Lauf erfolgreich |
| `4_statistics.ipynb` | 2 | Vollständiger Lauf erfolgreich |
| `5_selection.ipynb` | 5 | Vollständiger Lauf erfolgreich |
| `6_filter.ipynb` | 2 | Vollständiger Lauf erfolgreich |

Der abschließende Lauf verwendet Altair 6.3.0 und prüft dessen Import zusätzlich im Kernel. Sämtliche Quellzellen der Vorlagennotebooks sind gegenüber dem vorherigen Commit unverändert. Die Dateien enthalten weiterhin `NotImplementedError`, keine Lösungsausgaben und keine Ausführungszähler. Das Lösungsskript und die ausgeführten Kopien liegen ausschließlich außerhalb des Repositorys. Alle sechs Quelldateien wurden zusätzlich auf gültiges Notebook-Format geprüft.

## Prüfgrenzen

Die Prüfung bestätigt die technische Ausführbarkeit nach vollständiger Bearbeitung. Sie ersetzt keine didaktische Prüfung mit Teilnehmenden und keinen Windows-Test. Das dritte Notebook bezieht weiterhin seine ursprüngliche CSV-Datei über eine externe URL. Für diesen Lauf war die Quelle erreichbar; spätere Verfügbarkeit und Änderungen an der Quelle sind damit nicht zugesichert.
