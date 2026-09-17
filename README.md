# Langfristige Klimaentwicklung in Österreich

## Projektziel

In diesem Portfolio-Projekt analysiere ich historische Klimadaten aus Österreich.

Ziel ist es zu untersuchen, wie sich **Temperatur und Schneeverhältnisse langfristig verändert haben** und welche Unterschiede zwischen verschiedenen **Höhenlagen** sichtbar werden.

Als zusätzliche Vergleichsebene werden die österreichischen Bundesländer betrachtet.

## Fragestellung

**Wie haben sich Temperatur und Schneeverhältnisse in Österreich langfristig verändert und welche Unterschiede zeigen sich zwischen verschiedenen Höhenlagen?**

Im Fokus stehen insbesondere:

- Temperaturentwicklung
- Frosttage
- Schneedeckentage
- Unterschiede nach Höhenlage

Ergänzend werden regionale Unterschiede zwischen den Bundesländern betrachtet.

## Datenquelle

Die Daten stammen von **GeoSphere Austria**.

Verwendet werden monatliche, qualitätsgeprüfte Stationsdaten aus allen neun österreichischen Bundesländern.

Die Rohdaten umfassen:

- 9 Bundesländer
- mehr als 1.100 Messstationen
- historische Daten ab 1900
- 9 ausgewählte Klimaparameter

## Verwendete Parameter

- `tl_mittel` – mittlere Lufttemperatur
- `tlmax_mittel` – mittlere Maximaltemperatur
- `tlmin_mittel` – mittlere Minimaltemperatur
- `tage_frost` – Frosttage
- `shneu_manu` – Neuschneesumme
- `tage_schdecke` – Tage mit Schneedecke
- `sh_manu_max` – maximale Schneehöhe
- `rr` – Niederschlag
- `tage_festrrp` – Anteil festen Niederschlags

## Technologien

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Power BI
- Git / GitHub

## Vorgehensweise

### 1. Pilotanalyse

Zunächst wurde Tirol als Pilotdatensatz verwendet.

Der Pilot diente dazu:

- die Datenstruktur von GeoSphere kennenzulernen
- Stations- und Messdaten zu verbinden
- fehlende Werte zu untersuchen
- Datenqualitätsregeln zu entwickeln
- unterschiedliche Analysezeiträume zu testen
- erste Höhenklassen und Jahreskennzahlen zu erstellen

Die entwickelte Methodik wurde anschließend auf den vollständigen Österreich-Datensatz übertragen.

### 2. Datenaufbereitung

Die Daten aller neun Bundesländer wurden mit Python zusammengeführt.

Dabei wurden:

- über 1,7 Mio. Monatszeilen verarbeitet
- Stationsmetadaten ergänzt
- Bundesländer und Stations-IDs geprüft
- Dubletten kontrolliert
- fehlende Werte untersucht
- Höhenklassen erstellt
- Jahreswerte aus den Monatsdaten erzeugt

### 3. Datenqualität

Die Rohdaten reichen bis 1900 zurück. Da jedoch nicht alle Stationen über den gesamten Zeitraum vollständig messen, wird für langfristige Trendanalysen ein vergleichbarer Stationspool verwendet.

Für die Hauptanalyse wird aktuell der Zeitraum **1960–2025** betrachtet.

Eine Station wird für die jeweilige Kennzahl berücksichtigt, wenn mindestens **90 % der Jahreswerte** im Analysezeitraum verfügbar sind.

Zusätzlich werden Jahreswerte nur dann gebildet, wenn mindestens **10 von 12 Monatswerten** vorhanden sind.

Die Qualitätsprüfung erfolgt für jede Kennzahl separat.

## Höhenklassen

Die Stationen werden in vier Höhenklassen eingeteilt:

- unter 500 m
- 500–999 m
- 1.000–1.499 m
- ab 1.500 m

Dadurch können langfristige Klimaentwicklungen zwischen unterschiedlichen Höhenlagen verglichen werden.

## Temperaturreferenz

Für die Analyse der Temperaturentwicklung werden Temperaturabweichungen gegenüber der Referenzperiode **1961–1990** berechnet.

Dadurch wird jede Station mit ihrem eigenen historischen Temperaturniveau verglichen.

## Erste Ergebnisse

Die bisherige Analyse zeigt:

- einen langfristigen Temperaturanstieg in allen Höhenlagen
- sinkende Frosttage in allen Höhenlagen
- sinkende Schneedeckentage in allen Höhenlagen
- einen positiven Temperaturtrend in allen neun Bundesländern

Die berechneten Temperaturtrends liegen im ausgewählten Stationspool je nach Höhenlage bei ungefähr:

- unter 500 m: +0,40 °C pro Jahrzehnt
- 500–999 m: +0,37 °C pro Jahrzehnt
- 1.000–1.499 m: +0,31 °C pro Jahrzehnt
- ab 1.500 m: +0,34 °C pro Jahrzehnt

Bei den Frosttagen zeigt sich ein Rückgang von ungefähr **4 bis 6 Tagen pro Jahrzehnt**.

Bei den Schneedeckentagen liegt der Rückgang je nach Höhenlage bei ungefähr **4 bis 7 Tagen pro Jahrzehnt**.

## Projektstruktur

```text
data/
├── raw/
└── processed/

00_Tirol_pilot.ipynb
01_data_preparation.ipynb
02_data_analysis.ipynb
README.md