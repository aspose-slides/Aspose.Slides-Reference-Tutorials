---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python mühelos Prozentbeschriftungen in Diagrammen in PowerPoint-Präsentationen anzeigen. Perfekt zur Verbesserung der Datenvisualisierung."
"title": "So zeigen Sie Prozentbeschriftungen in Diagrammen mit Aspose.Slides für Python an – Ein umfassender Leitfaden"
"url": "/de/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So zeigen Sie Prozentbeschriftungen in Diagrammen mit Aspose.Slides für Python an

## Einführung

Die effektive Visualisierung von Daten ist in Präsentationen und Berichten entscheidend, insbesondere wenn Sie Anteile oder Verteilungen deutlich hervorheben möchten. Was aber, wenn Sie diese Prozentsätze direkt in Ihren Diagrammen anzeigen möchten? Dieser umfassende Leitfaden führt Sie durch die Verwendung **Aspose.Slides für Python** um mühelos Prozentwerte als Beschriftungen in einem Diagramm anzuzeigen.

### Was Sie lernen werden:
- So erstellen und betten Sie mit Aspose.Slides für Python Diagramme in PowerPoint-Präsentationen ein.
- Anzeigen von Datenpunkten als Prozentbeschriftungen in Ihren Diagrammen.
- PowerPoint-Präsentationen effizient speichern und verwalten.

Sind Sie bereit, Ihre Daten mit aufschlussreichen Visualisierungen zu versehen? Schauen wir uns zunächst an, was Sie benötigen, bevor wir uns in den Code vertiefen!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Aspose.Slides für Python**: Diese Bibliothek ist für die programmgesteuerte Erstellung und Bearbeitung von PowerPoint-Präsentationen unerlässlich.
- **Python-Umgebung**: Grundlegende Kenntnisse der Python-Programmierung und der Umgebungseinrichtung.
- **PIP-Paket-Manager**: Wird zum Installieren von Aspose.Slides verwendet.

## Einrichten von Aspose.Slides für Python

Um Aspose.Slides verwenden zu können, müssen Sie es zunächst installieren:

```bash
pip install aspose.slides
```

### Schritte zum Lizenzerwerb:
Sie können mit einer kostenlosen Testversion beginnen oder eine temporäre Lizenz erwerben, um den vollen Funktionsumfang von Aspose.Slides zu nutzen. Für eine erweiterte Nutzung können Sie ein Abonnement erwerben.

#### Grundlegende Initialisierung und Einrichtung

Nach der Installation initialisieren Sie Ihre Präsentationsumgebung wie folgt:

```python
import aspose.slides as slides

# Initialisieren eines Präsentationsobjekts
def create_presentation():
    with slides.Presentation() as presentation:
        # Ihr Code hier
```

## Implementierungshandbuch

Nachdem wir nun alles eingerichtet haben, können wir uns mit der Anzeige von Prozentsätzen in Diagrammen befassen.

### Erstellen des Diagramms und Hinzufügen von Daten

#### Überblick
Wir erstellen ein gestapeltes Säulendiagramm mit Prozentbeschriftungen für jeden Datenpunkt, sodass der Betrachter die genauen Anteile auf einen Blick erkennen kann.

##### Schritt 1: Fügen Sie Ihrer Folie ein Diagramm hinzu

```python
# Greifen Sie auf die erste Folie Ihrer Präsentation zu
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Hinzufügen eines gestapelten Säulendiagramms
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Dieser Codeausschnitt fügt der ersten Folie ein einfaches Diagramm hinzu. Die `add_chart` Die Methode gibt den Diagrammtyp sowie seine Position und Größe an.

##### Schritt 2: Gesamtwerte für Kategorien berechnen

```python
def calculate_totals(chart):
    total_for_category = []
    # Summieren Sie die Werte aller Serien für jede Kategorie
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Diese Schleife berechnet die Summe aller Datenpunkte über die Reihe hinweg, was für Prozentberechnungen entscheidend ist.

#### Festlegen von Prozentbeschriftungen

##### Schritt 3: Konfigurieren Sie Seriendatenpunkte

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Legen Sie Standardbeschriftungsoptionen fest, um nicht wesentliche Informationen auszublenden
        series.labels.default_data_label_format.show_legend_key = False
        
        # Prozentbezeichnungen berechnen und festlegen
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Erstellen Sie einen Textabschnitt mit dem Prozentwert
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Vorhandene Beschriftungen löschen und neue Prozentbeschriftung hinzufügen
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Andere Datenbeschriftungselemente ausblenden
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Dieses Segment verarbeitet jeden Datenpunkt, um seinen Prozentsatz vom Gesamtwert zu berechnen und weist ihn als Bezeichnung zu.

### Speichern Ihrer Präsentation

```python
def save_presentation(presentation, output_directory):
    # Speichern Sie Ihre Präsentation mit Änderungen
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}