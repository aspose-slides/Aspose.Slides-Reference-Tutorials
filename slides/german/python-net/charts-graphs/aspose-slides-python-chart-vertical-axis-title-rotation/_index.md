---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python den Drehwinkel von Diagrammtiteln in Präsentationen anpassen und so die Lesbarkeit und Ästhetik verbessern."
"title": "So legen Sie die Titelrotation der vertikalen Achse eines Diagramms in Aspose.Slides für Python fest"
"url": "/de/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie die Titelrotation der vertikalen Achse eines Diagramms in Aspose.Slides für Python fest

## Einführung

Bei Datenpräsentationen ist die Lesbarkeit von Diagrammen entscheidend. Durch Anpassen des Drehwinkels des vertikalen Achsentitels Ihres Diagramms mit Aspose.Slides für Python können Sie Titel besser einpassen oder auf Ihren Folien hervorheben. Dieses Tutorial führt Sie durch die Einstellung dieses Drehwinkels, um sowohl Funktionalität als auch Optik zu verbessern.

**Was Sie lernen werden:**
- So installieren und konfigurieren Sie Aspose.Slides für Python.
- Schritte zum Hinzufügen und Anpassen von Diagrammen in Ihren Folien.
- Techniken zum Festlegen des Drehwinkels von Diagrammtiteln.
- Reale Anwendungen für diese Funktionen in der Datenvisualisierung.

Lassen Sie uns zunächst die Voraussetzungen klären, bevor wir uns in die Implementierung stürzen.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:
- **Python-Umgebung**: Installieren Sie Python 3.x von [python.org](https://www.python.org/).
- **Aspose.Slides-Bibliothek**: Über Pip installieren, um Präsentationen effektiv zu bearbeiten.
- **Grundkenntnisse der Python-Programmierung**: Wenn Sie mit der Syntax und den Dateioperationen von Python vertraut sind, können Sie den Schritten leichter folgen.

## Einrichten von Aspose.Slides für Python

Um Aspose.Slides zu verwenden, installieren Sie es mit pip. Öffnen Sie Ihr Terminal oder Ihre Eingabeaufforderung und führen Sie Folgendes aus:

```bash
pip install aspose.slides
```

### Schritte zum Lizenzerwerb

Aspose bietet verschiedene Lizenzoptionen:
- **Kostenlose Testversion**: Laden Sie eine Testversion herunter von [Asposes Release-Seite](https://releases.aspose.com/slides/python-net/).
- **Temporäre Lizenz**: Erhalten Sie eine temporäre Lizenz für erweiterte Funktionen über die [Einkaufsportal](https://purchase.aspose.com/temporary-license/).
- **Kaufen**: Erwägen Sie den Kauf, wenn Sie das Werkzeug für unverzichtbar halten. Erhältlich bei [Aspose-Kaufseite](https://purchase.aspose.com/buy).

#### Grundlegende Initialisierung und Einrichtung

So initialisieren Sie Aspose.Slides in Ihrem Python-Skript:

```python
import aspose.slides as slides

# Erstellen eines Präsentationsobjekts
def main():
    with slides.Presentation() as pres:
        # Ihr Code wird hier eingefügt
        pass

if __name__ == "__main__":
    main()
```

## Implementierungshandbuch

### Hinzufügen und Anpassen von Diagrammen

#### Überblick

In diesem Abschnitt fügen wir Ihrer Folie ein gruppiertes Säulendiagramm hinzu und passen es an, indem wir den Drehwinkel des Titels der vertikalen Achse festlegen.

#### Schritte:

##### Schritt 1: Fügen Sie ein gruppiertes Säulendiagramm hinzu

Beginnen Sie, indem Sie an bestimmten Koordinaten ein Diagramm mit definierten Abmessungen hinzufügen:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Fügen Sie Folie 1 ein gruppiertes Säulendiagramm hinzu
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Schritt 2: Konfigurieren Sie den Titel der vertikalen Achse

Aktivieren und legen Sie den Drehwinkel für den Titel der vertikalen Achse fest:

```python
def configure_chart(chart):
    # Aktivieren Sie den Titel der vertikalen Achse
    chart.axes.vertical_axis.has_title = True
    
    # Stellen Sie den Drehwinkel auf 90 Grad ein
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Schritt 3: Speichern Sie Ihre Präsentation

Speichern Sie abschließend Ihre Präsentation mit den Änderungen:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Speichern der Präsentation
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}