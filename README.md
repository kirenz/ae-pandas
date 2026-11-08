# Pandas-Übungen

Data Analytics · WS 2026/27

Die sechs Notebooks führen vom Einlesen zu gezielten Abfragen. Die Übungen bauen in dieser Reihenfolge aufeinander auf:

| Notebook | Aufgabe |
|---|---|
| `1_import_store.ipynb` | Tabelle erstellen, CSV einlesen und Excel-Datei speichern |
| `2_columns.ipynb` | Spaltennamen prüfen und vereinheitlichen |
| `3_data_types.ipynb` | Datentypen prüfen und umwandeln |
| `4_statistics.ipynb` | Kennzahlen berechnen und Verteilungen untersuchen |
| `5_selection.ipynb` | Zeilen und Spalten gezielt auswählen |
| `6_filter.ipynb` | Bedingungen formulieren und Gruppen bilden |

Die CSV-Dateien liegen in `data/`. Ihre Herkunft steht in `data/QUELLEN.md`. Das erste Notebook erzeugt `height.xlsx` als lokale Übungsdatei.

## Eigene Arbeitskopie

1. Auf GitHub „Use this template“ und „Create a new repository“ wählen.
2. Einen eigenen Repository-Namen vergeben und die Sichtbarkeit „Private“ wählen.
3. Das eigene Repository mit GitHub Desktop oder dem vorhandenen Git-Werkzeug klonen.
4. Ein Terminal im geklonten Projektordner öffnen.

## Python-Umgebung

Die Projektumgebung verwendet Python 3.14. uv installiert die passende Python-Version bei Bedarf automatisch.

Voraussetzung: [uv ist installiert](https://github.com/kirenz/uv-setup#installing-uv). Das Terminal befindet sich im Projektordner.

1. Die festgelegte Umgebung einrichten:

```bash
uv sync --locked
```

2. Den Kernel in dieser lokalen Umgebung einrichten:

```bash
uv run --locked python -m ipykernel install --sys-prefix --name data-analytics --display-name "Python 3.14 (Data Analytics)"
```

3. Jupyter Lab starten:

```bash
uv run --locked jupyter lab
```

4. Im Notebook den Kernel „Python 3.14 (Data Analytics)“ auswählen.

Die lokale Umgebung wird in `.venv` angelegt. `pyproject.toml` und `uv.lock` gehören zum Repository; `.venv` bleibt lokal.

## Bearbeitung

1. Das erste Notebook öffnen.
2. In `NAME` das eigene Kürzel eintragen.
3. Erklärungen lesen und Zellen mit `# YOUR CODE HERE` bearbeiten.
4. `raise NotImplementedError()` jeweils durch den eigenen Code ersetzen.
5. Die vorhandenen Prüfzellen ausführen.
6. Nach Abschluss den Kernel neu starten und alle Zellen erneut ausführen.
7. Den bearbeiteten Stand mit einer verständlichen Commit-Nachricht sichern.

Prüfkriterium: Alle Zellen laufen nach vollständiger Bearbeitung ohne Fehler. Die Prüfzellen bleiben unverändert. Vor der Bearbeitung brechen Aufgabenstellen absichtlich mit `NotImplementedError` ab.

Die Aufgaben werden selbst gelöst. Ein Coding-Agent im Projektordner erklärt Fehlermeldungen und Begriffe, gibt Hinweise und kommentiert eine fertige eigene Lösung. Die Regeln dafür stehen in `AGENTS.md`. Vorgaben zur Abgabe und zum KI-Einsatz stehen im aktuellen Moodle-Kurs.

Grundlage: die gleichnamige Kursvorlage aus data-analytics-ws2425. Die bisherigen Beispiele und Aufgaben bleiben erhalten.
