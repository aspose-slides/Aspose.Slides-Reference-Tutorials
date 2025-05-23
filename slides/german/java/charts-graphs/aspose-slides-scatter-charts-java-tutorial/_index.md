---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java dynamische Streudiagramme erstellen. Optimieren Sie Ihre Präsentationen mit anpassbaren Diagrammfunktionen."
"title": "Erstellen und Anpassen von Streudiagrammen in Java mit Aspose.Slides"
"url": "/de/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen und Anpassen von Streudiagrammen in Java mit Aspose.Slides

Optimieren Sie Ihre Präsentationen mit dynamischen Streudiagrammen in Java und Aspose.Slides. Dieses umfassende Tutorial führt Sie durch das Einrichten von Verzeichnissen, das Initialisieren von Präsentationen, das Erstellen von Streudiagrammen, das Verwalten von Diagrammdaten, das Anpassen von Serientypen und Markierungen sowie das Speichern Ihrer Arbeit – ganz einfach.

**Was Sie lernen werden:**
- Einrichten eines Verzeichnisses zum Speichern von Präsentationsdateien
- Initialisieren und Bearbeiten von Präsentationen mit Aspose.Slides
- Erstellen von Streudiagrammen auf Folien
- Verwalten und Hinzufügen von Daten zu Diagrammreihen
- Anpassen von Diagrammreihentypen und Markierungen
- Speichern Ihrer Präsentation mit Änderungen

Stellen wir zunächst sicher, dass Sie über die erforderlichen Voraussetzungen verfügen.

## Voraussetzungen

Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Aspose.Slides für Java**: Version 25.4 oder höher ist erforderlich.
- **Java Development Kit (JDK)**: JDK 8 oder höher wird benötigt.
- Grundkenntnisse der Java-Programmierung und Vertrautheit mit den Build-Tools Maven oder Gradle.

## Einrichten von Aspose.Slides für Java

Bevor wir mit der Codierung beginnen, integrieren Sie Aspose.Slides mit einer der folgenden Methoden in Ihr Projekt:

### Maven
Fügen Sie diese Abhängigkeit in Ihre `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie diese Zeile zu Ihrem `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativ können Sie die neueste Version von Aspose.Slides für Java herunterladen von [Aspose-Veröffentlichungen](https://releases.aspose.com/slides/java/).

#### Lizenzerwerb
- **Kostenlose Testversion**: Beginnen Sie mit einer 30-tägigen kostenlosen Testversion, um die Funktionen zu erkunden.
- **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz für erweiterte Tests.
- **Kaufen**: Kaufen Sie eine Lizenz für vollständigen Zugriff und Support.

Initialisieren Sie nun Aspose.Slides in Ihrer Java-Anwendung, indem Sie die erforderlichen Importe wie unten gezeigt hinzufügen.

## Implementierungshandbuch

### Verzeichnis-Setup
Stellen Sie zunächst sicher, dass das Verzeichnis zum Speichern der Präsentationsdateien vorhanden ist. Dadurch werden Fehler beim Speichern der Dateien vermieden.

#### Erstellen Sie das Verzeichnis, falls es nicht vorhanden ist
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Erstellen Sie das Verzeichnis
    new File(dataDir).mkdirs();
}
```
Dieses Snippet sucht nach einem angegebenen Verzeichnis und erstellt es, falls es nicht existiert. Es verwendet `File.exists()` zur Überprüfung der Anwesenheit und `File.mkdirs()` um Verzeichnisse zu erstellen.

### Präsentationsinitialisierung

Initialisieren Sie als Nächstes Ihr Präsentationsobjekt, in dem Sie das Streudiagramm hinzufügen.

#### Initialisieren Sie Ihre Präsentation
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Hier, `new Presentation()` erstellt eine leere Präsentation. Wir greifen direkt auf die erste Folie zu, um damit zu arbeiten.

### Diagrammerstellung
Als Nächstes erstellen wir auf unserer initialisierten Folie ein Streudiagramm.

#### Streudiagramm zur Folie hinzufügen
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Dieser Codeausschnitt fügt der ersten Folie ein Streudiagramm mit glatten Linien hinzu. Die Parameter definieren die Position und Größe des Diagramms.

### Diagrammdatenverwaltung
Verwalten wir nun unsere Diagrammdaten, indem wir alle vorhandenen Reihen löschen und neue hinzufügen.

#### Diagrammserien verwalten
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Hinzufügen neuer Reihen zum Diagramm
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Dieser Abschnitt löscht vorhandene Daten und fügt unserem Streudiagramm zwei neue Reihen hinzu.

### Datenpunktaddition für Streureihen
Um unsere Daten zu visualisieren, fügen wir jeder Reihe im Streudiagramm Punkte hinzu.

#### Datenpunkte hinzufügen
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Wir verwenden `addDataPointForScatterSeries()` um Datenpunkte an unsere erste Reihe anzuhängen. Parameter definieren X- und Y-Werte.

### Serientyp und Markierungsänderung
Passen Sie das Erscheinungsbild Ihres Diagramms an, indem Sie den Typ und Stil der Markierungen in jeder Reihe ändern.

#### Serie anpassen
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Ändern der zweiten Serie
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Diese Änderungen passen den Serientyp an, sodass gerade Linien und Markierungen verwendet werden. Außerdem legen wir die Markierungsgröße und das Symbol zur visuellen Unterscheidung fest.

### Präsentation speichern
Speichern Sie abschließend Ihre Präsentation mit allen vorgenommenen Änderungen.

#### Speichern Sie Ihre Präsentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Verwenden `SaveFormat.Pptx` um das PowerPoint-Format zum Speichern Ihrer Datei anzugeben. Dieser Schritt ist entscheidend, damit alle Änderungen erhalten bleiben.

## Praktische Anwendungen
Hier sind einige Anwendungsfälle aus der Praxis:
1. **Finanzanalyse**: Verwenden Sie Streudiagramme, um Aktientrends im Zeitverlauf anzuzeigen.
2. **Wissenschaftliche Forschung**: Stellen Sie experimentelle Datenpunkte für die Analyse dar.
3. **Projektmanagement**: Visualisieren Sie die Ressourcenzuweisung und Fortschrittsmetriken.

Durch die Integration von Aspose.Slides in Ihr System können Sie die Berichterstellung automatisieren und so die Produktivität und Genauigkeit steigern.

## Überlegungen zur Leistung
Für optimale Leistung:
- Verwalten Sie die Speichernutzung, indem Sie Präsentationen nach dem Speichern verwerfen.
- Verwenden Sie effiziente Datenstrukturen für große Datensätze.
- Minimieren Sie ressourcenintensive Vorgänge innerhalb von Schleifen.

Best Practices gewährleisten eine reibungslose Ausführung auch bei komplexen Chartmanipulationen.

## Abschluss
In diesem Tutorial haben Sie gelernt, Verzeichnisse einzurichten, Aspose.Slides-Präsentationen zu initialisieren, Streudiagramme zu erstellen und anzupassen, Seriendaten zu verwalten, Markierungen zu ändern und Ihre Arbeit zu speichern. Um die Funktionen von Aspose.Slides noch weiter zu erkunden, sollten Sie sich mit erweiterten Funktionen wie Animationen und Folienübergängen befassen.

**Nächste Schritte**: Experimentieren Sie mit verschiedenen Diagrammtypen oder integrieren Sie diese Techniken in ein größeres Java-Projekt.

## Häufig gestellte Fragen

### Wie ändere ich die Farbe der Markierungen?
Um die Markierungsfarbe zu ändern, verwenden Sie `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Wo `ColorObject` ist Ihre Wunschfarbe.

### Kann ich einem Streudiagramm mehr als zwei Reihen hinzufügen?
Ja, Sie können beliebig viele Reihen hinzufügen, indem Sie den Vorgang des Hinzufügens neuer Reihen und Datenpunkte wiederholen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}