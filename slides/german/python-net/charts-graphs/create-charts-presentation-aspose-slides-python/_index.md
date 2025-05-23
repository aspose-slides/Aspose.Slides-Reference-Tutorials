---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen mit dynamischen Diagrammen mithilfe von Aspose.Slides für Python optimieren. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um gruppierte Säulendiagramme effektiv zu erstellen, zu verwalten und zu formatieren."
"title": "Erstellen und formatieren Sie Diagramme in PowerPoint-Präsentationen mit Aspose.Slides für Python"
"url": "/de/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen und formatieren Sie Diagramme in PowerPoint-Präsentationen mit Aspose.Slides für Python

## Einführung

In der heutigen datengetriebenen Welt ist die Einbindung visuell ansprechender Diagramme in Präsentationen entscheidend für eine effektive Kommunikation. Ob Datenanalyst, Projektmanager oder Wirtschaftsexperte – dynamische Diagramme können Ihre Botschaft deutlich verbessern. Dieses Tutorial führt Sie durch die Erstellung und Formatierung gruppierter Säulendiagramme mit Aspose.Slides für Python und ermöglicht Ihnen so, Ihre PowerPoint-Folien mühelos aufzuwerten.

**Was Sie lernen werden:**
- So installieren und richten Sie Aspose.Slides für Python ein
- Erstellen Sie eine neue Präsentation und fügen Sie ein gruppiertes Säulendiagramm hinzu
- Verwalten von Datenreihen und Kategorien innerhalb des Diagramms
- Füllen und formatieren Sie Seriendaten für eine bessere Visualisierung

Bereit, Ihre Präsentationen zu verbessern? Lassen Sie uns untersuchen, wie Sie mit Aspose.Slides ansprechende Diagramme erstellen können.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Installiertes Python:** Es wird Version 3.6 oder höher empfohlen.
- **Aspose.Slides für Python-Paket:** Installieren Sie dieses Paket mit pip.
- **Grundkenntnisse der Python-Programmierung:** Kenntnisse der Python-Syntax und der Dateiverwaltung sind von Vorteil.

## Einrichten von Aspose.Slides für Python

Um zu beginnen, müssen Sie die Bibliothek Aspose.Slides installieren. Dieses leistungsstarke Tool vereinfacht das Erstellen und Bearbeiten von PowerPoint-Präsentationen in Python.

### Installation

Führen Sie den folgenden Befehl aus, um das Paket zu installieren:

```bash
pip install aspose.slides
```

### Lizenzerwerb

Aspose bietet eine kostenlose Testlizenz an, mit der Sie alle Funktionen ohne Einschränkungen nutzen können. Befolgen Sie diese Schritte, um die Lizenz zu erhalten:

1. Besuchen [Kostenlose Aspose-Testversion](https://releases.aspose.com/slides/python-net/) um das Testpaket herunterzuladen.
2. Alternativ können Sie eine temporäre Lizenz anfordern über [Seite „Temporäre Lizenz“](https://purchase.aspose.com/temporary-license/).

Sobald Sie Ihre Lizenzdatei haben, initialisieren Sie sie in Ihrem Python-Skript:

```python
from aspose.slides import License

# Einrichten der Aspose.Slides-Lizenz
license = License()
license.set_license("path/to/your/license/file.lic")
```

## Implementierungshandbuch

Wir unterteilen den Prozess in drei Hauptfunktionen: Erstellen von Diagrammen, Verwalten von Datenreihen und Kategorien sowie Auffüllen und Formatieren von Reihendaten.

### Funktion 1: Erstellen und Hinzufügen eines Diagramms zu einer Präsentation

#### Überblick

Bei dieser Funktion geht es darum, Ihrer Präsentation mithilfe von Aspose.Slides für Python ein gruppiertes Säulendiagramm hinzuzufügen.

#### Schrittweise Implementierung

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # Fügen Sie an der Position (100, 100) ein gruppiertes Säulendiagramm mit der Breite 400 und der Höhe 300 hinzu.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # Speichern Sie die Präsentation in einer Datei in Ihrem Ausgabeverzeichnis.
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**Erläuterung:**
- **Diagrammposition und -größe:** Der `add_chart` Die Methode wird mit Parametern verwendet, die Diagrammtyp, Position (x,y), Breite und Höhe angeben.
- **Speichern der Präsentation:** Die Präsentation wird in einem angegebenen Verzeichnis gespeichert.

### Funktion 2: Verwalten von Diagrammdatenreihen und -kategorien

#### Überblick

In diesem Abschnitt wird gezeigt, wie Sie Datenreihen und Kategorien in Ihrem Diagramm effektiv verwalten.

#### Schrittweise Implementierung

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # Fügen Sie an der Position (100, 100) ein gruppiertes Säulendiagramm mit der Breite 400 und der Höhe 300 hinzu.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Löschen Sie vorhandene Serien und Kategorien, bevor Sie neue hinzufügen.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Hinzufügen einer neuen Serie mit dem Namen „Serie 1“ zum Diagramm.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Hinzufügen von drei Kategorien zu den Diagrammdaten.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Speichern Sie die Präsentation in einer Datei in Ihrem Ausgabeverzeichnis.
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**Erläuterung:**
- **Vorhandene Daten löschen:** Vor dem Hinzufügen neuer Serien und Kategorien werden vorhandene gelöscht, um Datenduplikate zu vermeiden.
- **Hinzufügen von Serien und Kategorien:** Neue Serien und Kategorien werden über das `chart_data_workbook` Objekt.

### Funktion 3: Auffüllen von Seriendaten und Formatieren des Diagramms

#### Überblick

Mit dieser Funktion füllen wir Ihr Diagramm mit Datenpunkten und wenden Formatierungen an, um seine visuelle Attraktivität zu verbessern.

#### Schrittweise Implementierung

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # Fügen Sie an der Position (100, 100) ein gruppiertes Säulendiagramm mit der Breite 400 und der Höhe 300 hinzu.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Löschen Sie vorhandene Serien und Kategorien, bevor Sie neue hinzufügen.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Hinzufügen einer neuen Serie mit dem Namen „Serie 1“ zum Diagramm.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Hinzufügen von drei Kategorien zu den Diagrammdaten.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Nehmen Sie die erste Diagrammreihe und füllen Sie sie mit Datenpunkten.
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # Legen Sie die Farbe für negative Werte in der Reihe fest.
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # Speichern Sie die Präsentation in einer Datei in Ihrem Ausgabeverzeichnis.
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**Erläuterung:**
- **Hinzufügen von Datenpunkten:** Datenpunkte werden hinzugefügt mit `add_data_point_for_bar_series`.
- **Formatieren negativer Werte:** Diagrammformatierungsoptionen wie die Farbumkehrung für negative Werte verbessern die Lesbarkeit der Daten.

## Praktische Anwendungen

Die Verwendung von Aspose.Slides zum Hinzufügen und Formatieren von Diagrammen in Präsentationen hat zahlreiche Anwendungsmöglichkeiten:

1. **Geschäftsberichte:** Verbessern Sie Quartalsberichte mit dynamischen Visualisierungen, die wichtige Kennzahlen klar vermitteln.
2. **Lehrmaterial:** Erstellen Sie ansprechende Bildungsinhalte, indem Sie komplexe Informationen visuell darstellen.
3. **Projektpräsentationen:** Verwenden Sie Diagramme, um den Projektfortschritt und die Ergebnisse effektiv zu veranschaulichen.

Wenn Sie dieser Anleitung folgen, können Sie Aspose.Slides für Python nutzen, um wirkungsvolle Präsentationen zu erstellen, die sich von der Masse abheben.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}