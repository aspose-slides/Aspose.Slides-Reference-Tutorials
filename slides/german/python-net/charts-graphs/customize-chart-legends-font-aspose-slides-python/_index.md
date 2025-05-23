---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie die Schrifteigenschaften von Diagrammlegenden mit Aspose.Slides für Python anpassen. Optimieren Sie Ihre Präsentationen mit fetten, kursiven und farbigen Schriftarten für einzelne Legendeneinträge."
"title": "Anpassen der Schriftart von Diagrammlegenden mit Aspose.Slides für Python – Ein umfassender Leitfaden"
"url": "/de/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Anpassen der Schriftart der Diagrammlegenden in Präsentationen mit Aspose.Slides für Python

## Einführung
Visuell ansprechende Präsentationen sind unerlässlich, insbesondere bei der Darstellung von Daten in Diagrammen. Eine häufige Herausforderung besteht darin, Diagrammlegenden an Ihren Präsentationsstil oder Ihre Markenanforderungen anzupassen. Diese Anleitung zeigt, wie Sie Schrifteigenschaften wie Fettdruck, Kursivschrift, Größe und Farbe für einzelne Legendeneinträge in einem Diagramm mit Aspose.Slides für Python anpassen.

**Was Sie lernen werden:**
- Einrichten und Verwenden von Aspose.Slides für Python
- Anpassen der Schrifteigenschaften von Diagrammlegenden
- Anwenden bestimmter Schriftstile wie Fettdruck, Kursivschrift und Farbänderungen
- Praktische Beispiele zur Verbesserung von Diagrammen mit benutzerdefinierten Schriftarten

Lassen Sie uns untersuchen, wie Sie diese Anpassung erreichen können.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Bibliotheken**: Aspose.Slides für Python. Installieren Sie es mit pip.
- **Umfeld**: Auf Ihrem Computer ist eine Python-Umgebung (vorzugsweise Python 3.x) eingerichtet.
- **Wissen**Grundlegende Kenntnisse der Python-Programmierung und Vertrautheit mit der programmgesteuerten Handhabung von Präsentationen.

## Einrichten von Aspose.Slides für Python
### Installation
Installieren Sie zunächst die Aspose.Slides-Bibliothek, indem Sie den folgenden Befehl in Ihrem Terminal ausführen:

```bash
pip install aspose.slides
```

### Lizenzerwerb
Aspose.Slides ist ein kommerzielles Produkt mit verschiedenen Lizenzierungsoptionen:
- **Kostenlose Testversion**: Erwerben Sie eine temporäre Lizenz für die volle Funktionalität.
- **Temporäre Lizenz**: Beantragen Sie eine temporäre Lizenz, um alle Funktionen ohne Einschränkungen zu testen.
- **Kaufen**: Kaufen Sie je nach Bedarf ein Abonnement oder eine unbefristete Lizenz.

### Grundlegende Initialisierung
So können Sie Aspose.Slides in Ihrem Python-Skript initialisieren und einrichten:

```python
import aspose.slides as slides

# Initialisieren Sie eine Präsentationsinstanz mit slides.Presentation() als pres:
    # Ihr Code hier
```

## Implementierungshandbuch
In diesem Abschnitt werden wir die Anpassung der Schrifteigenschaften einzelner Legendeneinträge durchgehen.

### Hinzufügen und Zugreifen auf ein Diagramm
Fügen wir Ihrer Folie zunächst ein gruppiertes Säulendiagramm hinzu:

```python
# Fügen Sie an der Position (50, 50) ein gruppiertes Säulendiagramm mit der Breite 600 und der Höhe 400 hinzu
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Dies ist nur ein Platzhalter für die eigentliche Aspose.Slides-Methode.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# Simulieren von pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Anpassen der Schriftarteigenschaften der Legende
#### Zugriff auf das Textformat des Legendeneintrags
So ändern Sie die Schriftarteigenschaften eines bestimmten Legendeneintrags:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# Simulieren von chart.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Festlegen der Schriftarteigenschaften
Hier passen wir Aspekte wie Fettdruck, Größe, Kursivschrift und Farbe an:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Stellen Sie die Schriftgröße auf 20 Punkte ein
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Stellen Sie die Schriftfarbe mithilfe des Fülltyps „Vollständig“ auf Blau ein
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Speichern der Präsentation
Speichern Sie Ihre Präsentation abschließend mit diesen Anpassungen:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}