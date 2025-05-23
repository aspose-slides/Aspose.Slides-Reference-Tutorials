---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python Diagramme in PowerPoint erstellen und anpassen. Optimieren Sie Ihre Präsentationen mühelos mit professionellen Grafiken."
"title": "Meistern Sie PowerPoint-Diagramme mit Aspose.Slides für Python – einfach erstellen und anpassen"
"url": "/de/python-net/charts-graphs/create-customize-powerpoint-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagrammerstellung und -anpassung in PowerPoint mit Aspose.Slides für Python meistern

## Einführung
Visuell ansprechende Präsentationen sind entscheidend für eine effektive Kommunikation, egal ob Sie vor einem Vorstand präsentieren oder Dateneinblicke mit Kunden teilen. Die Herausforderung besteht oft darin, überzeugende Diagramme, die Ihre Daten präzise darstellen, in PowerPoint-Folien zu integrieren. Mit **Aspose.Slides für Python**, wird diese Aufgabe nahtlos und effizient.

In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Slides Python mühelos PowerPoint-Diagramme erstellen und anpassen. Diese leistungsstarke Bibliothek bietet robuste Funktionen, um Ihre Präsentationen mit professionellen Grafiken zu verbessern.

**Was Sie lernen werden:**
- So richten Sie Aspose.Slides für Python ein
- Erstellen eines Liniendiagramms innerhalb einer Folie
- Ändern vorhandener Diagrammdaten
- Festlegen benutzerdefinierter Markierungen mithilfe von Bildern
- Reale Anwendungen dieser Techniken

Bereit, Ihre PowerPoint-Diagramme zu verbessern? Sehen wir uns die Voraussetzungen an und legen wir los!

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über die erforderlichen Werkzeuge und Kenntnisse verfügen, um mit den folgenden Schritten fortzufahren:

1. **Python-Installation**: Stellen Sie sicher, dass Python auf Ihrem System installiert ist (Version 3.6 oder höher empfohlen).
2. **Aspose.Slides für Python**: Über Pip installieren:
   ```bash
   pip install aspose.slides
   ```
3. **Entwicklungsumgebung**: Verwenden Sie eine IDE wie VSCode oder PyCharm für eine bessere Codeverwaltung.
4. **Grundlegende Python-Kenntnisse**Vertrautheit mit der Python-Syntax und den Programmierkonzepten ist unerlässlich.

## Einrichten von Aspose.Slides für Python
Um zu beginnen, müssen Sie Aspose.Slides für Python in Ihrer Entwicklungsumgebung einrichten:

### Installation
Installieren Sie die Bibliothek mit pip:
```bash
pip install aspose.slides
```

### Lizenzerwerb
Aspose.Slides bietet verschiedene Lizenzierungsoptionen:
- **Kostenlose Testversion**: Testen Sie Funktionen mit eingeschränkter Funktionalität.
- **Temporäre Lizenz**: Erhalten Sie während des Tests eine kostenlose temporäre Lizenz für den Zugriff auf alle Funktionen.
- **Kaufen**: Für die fortlaufende Nutzung sollten Sie den Kauf eines Abonnements in Erwägung ziehen.

**Grundlegende Initialisierung und Einrichtung:**
```python
import aspose.slides as slides

# Präsentationsobjekt initialisieren
with slides.Presentation() as presentation:
    # Fügen Sie hier Ihren Code ein, um die Präsentation zu bearbeiten
    pass
```

## Implementierungshandbuch
Lassen Sie uns die Implementierung in drei Hauptfunktionen unterteilen:

### Diagramm erstellen und hinzufügen
#### Überblick
Diese Funktion demonstriert das Hinzufügen eines Liniendiagramms mit Markierungen zu einer PowerPoint-Folie.

**Schritte:**
1. **Offene Präsentation**Beginnen Sie, indem Sie eine neue oder vorhandene Präsentation öffnen.
2. **Folie auswählen**: Wählen Sie die Folie aus, der Sie das Diagramm hinzufügen möchten.
3. **Liniendiagramm hinzufügen**: Verwenden `add_chart` Methode zum Einfügen des Diagramms.
4. **Präsentation speichern**: Speichern Sie Ihre Änderungen mit der aktualisierten Folie.

**Code-Implementierung:**
```python
import aspose.slides as slides

def add_chart_to_slide():
    # Öffnen Sie eine neue Präsentation
    with slides.Presentation() as presentation:
        # Wählen Sie die erste Folie aus
        slide = presentation.slides[0]
        
        # Fügen Sie der ausgewählten Folie an Position (0, 0) und Größe (400, 400) ein Liniendiagramm mit Markierungen hinzu
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # Speichern Sie die Präsentation mit dem hinzugefügten Diagramm auf der Festplatte
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Diagrammdaten ändern
#### Überblick
Erfahren Sie, wie Sie vorhandene Daten löschen und einem Diagramm neue Punktereihen hinzufügen.

**Schritte:**
1. **Zugriffsdiagramm**: Rufen Sie das Diagramm von Ihrer Folie ab.
2. **Vorhandene Serien löschen**: Entfernen Sie alle bereits vorhandenen Datenreihen.
3. **Neue Datenpunkte hinzufügen**: Neue Daten in die Reihe einfügen.
4. **Änderungen speichern**: Änderungen an der Präsentationsdatei beibehalten.

**Code-Implementierung:**
```python
import aspose.slides as slides

def modify_chart_data():
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        chart = slide.shapes.add_chart(slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400)
        
        # Zugriff auf den Standardarbeitsblattindex für die Diagrammdaten
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # Löschen Sie alle vorhandenen Reihen im Diagramm
        chart.chart_data.series.clear()
        
        # Fügen Sie dem Diagramm eine neue Reihe mit dem angegebenen Namen und Typ hinzu
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # Greifen Sie auf die erste (und einzige) Reihe in den Diagrammdaten zu
        series = chart.chart_data.series[0]
        
        # Fügen Sie der Reihe Datenpunkte hinzu und legen Sie ihre Werte fest
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.value = 4.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.value = 2.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 3, 1, 3.5))
        point.value = 3.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 4, 1, 4.5))
        point.value = 4.5
        
        # Speichern Sie die aktualisierte Präsentation auf der Festplatte
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Diagrammmarkierungen mit Bildern setzen
#### Überblick
Verbessern Sie Ihr Diagramm, indem Sie benutzerdefinierte Bildmarkierungen für Datenpunkte festlegen.

**Schritte:**
1. **Liniendiagramm hinzufügen**: Fügen Sie ein Liniendiagramm in die Folie ein.
2. **Bilder laden**: Fügen Sie Bilder aus Ihrem Dokumentverzeichnis hinzu, die als Markierungen verwendet werden sollen.
3. **Bildmarkierungen setzen**: Wenden Sie diese Bilder auf bestimmte Datenpunkte in der Reihe an.
4. **Markergröße anpassen**: Passen Sie die Größe der Bildmarkierungen für eine bessere Sichtbarkeit an.

**Code-Implementierung:**
```python
import aspose.slides as slides

def set_chart_markers_with_images():
    # Öffnen Sie eine neue Präsentation
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        
        # Fügen Sie der ausgewählten Folie an Position (0, 0) und Größe (400, 400) ein Liniendiagramm mit Markierungen hinzu
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # Zugriff auf den Standardarbeitsblattindex für die Diagrammdaten
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # Löschen Sie alle vorhandenen Reihen im Diagramm und fügen Sie eine neue hinzu
        chart.chart_data.series.clear()
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # Greifen Sie auf die erste (und einzige) Reihe in den Diagrammdaten zu
        series = chart.chart_data.series[0]
        
        # Bilder laden und zur Bildersammlung der Präsentation hinzufügen
        image1 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image1.jpg")
        imgx1 = presentation.images.add_image(image1)
        
        image2 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image2.jpg")
        imgx2 = presentation.images.add_image(image2)
        
        # Fügen Sie Datenpunkte hinzu und legen Sie ihre Markierungsbilder fest
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx1
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx2
        
        # Speichern Sie die Präsentation mit den benutzerdefinierten Markierungen auf der Festplatte
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_with_image_markers_out.pptx", slides.export.SaveFormat.PPTX)
```

## Abschluss
Mit diesem Tutorial verfügen Sie nun über eine solide Grundlage für die Erstellung und Anpassung von Diagrammen in PowerPoint mit Aspose.Slides für Python. Ob Sie neue Datenreihen hinzufügen oder Ihre Visualisierungen mit Bildmarkierungen verbessern – diese Techniken helfen Ihnen, wirkungsvollere Präsentationen zu erstellen.

## Keyword-Empfehlungen
- „Aspose.Slides für Python“
- „PowerPoint-Diagrammanpassung“
- „Diagramme in PowerPoint mit Python erstellen“
- „Python-Präsentationsverbesserung“

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}