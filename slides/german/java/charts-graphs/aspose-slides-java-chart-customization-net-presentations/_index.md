---
date: '2026-06-08'
description: Erfahren Sie, wie Sie Serien zu einem Diagramm hinzufügen und gestapelte
  Säulendiagramme in .NET-Präsentationen mit Aspose.Slides für Java anpassen.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Serien zu Diagramm hinzufügen mit Aspose.Slides für Java in .NET
url: /de/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meisterung der Diagrammanpassung in .NET-Präsentationen mit Aspose.Slides für Java

## Einleitung
Im Bereich datengetriebener Präsentationen sind Diagramme unverzichtbare Werkzeuge, die rohe Zahlen in überzeugende visuelle Geschichten verwandeln. Wenn Sie programmgesteuert **add series to chart** hinzufügen müssen, insbesondere in .NET‑Präsentationsdateien, kann die Aufgabe überwältigend wirken. Glücklicherweise bietet **Aspose.Slides for Java** eine leistungsstarke, sprachunabhängige API, die die Erstellung und Anpassung von Diagrammen unkompliziert macht – selbst wenn Ihr Zielformat ein .NET PPTX ist. Dieser Leitfaden führt Sie durch das Hinzufügen von Serien, den Aufbau eines gestapelten Säulendiagramms und das Feinabstimmen visueller Aspekte wie der Lückenbreite, sodass Sie dynamische, datenreiche Folien erzeugen können, die professionell und poliert aussehen.

## Schnelle Antworten
Die Klasse `Presentation` repräsentiert eine PPTX‑Datei, und `slide.getShapes().addChart(...)` fügt eine Diagrammform ein. Verwenden Sie `chart.getChartData().getSeries().add(...)`, um eine Serie hinzuzufügen, und `setGapWidth()` passt den Abstand an.

- **Was ist die primäre Klasse zum Starten einer Präsentation?** `Presentation` – sie repräsentiert eine PPTX‑Datei im Speicher.  
- **Welche Methode fügt ein Diagramm zu einer Folie hinzu?** `slide.getShapes().addChart(...)` erstellt das Diagrammobjekt auf der Folie.  
- **Wie fügen Sie eine neue Serie hinzu?** `chart.getChartData().getSeries().add(...)` fügt eine neue Datenserie ein.  
- **Können Sie die Lückenbreite zwischen Balken ändern?** Ja – rufen Sie `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` auf (der Wert ist ein Prozentsatz).  
- **Benötige ich eine Lizenz für die Produktion?** Absolut – eine gültige Aspose.Slides for Java‑Lizenz schaltet alle Funktionen frei und entfernt Evaluationswasserzeichen.

## Was bedeutet “add series to chart”?
Das Hinzufügen einer Serie zu einem Diagramm bedeutet, eine neue Sammlung von Datenpunkten einzufügen, die das Diagramm als ein separates visuelles Element darstellt (z. B. eine separate Säulengruppe). Jede Serie kann eigene Werte, Farben und Formatierungen haben, was einen Nebeneinandervergleich mehrerer Datensätze ermöglicht.

## Warum Aspose.Slides for Java verwenden, um .NET‑Präsentationen zu ändern?
Aspose.Slides for Java ermöglicht das Erzeugen oder Bearbeiten von PPTX‑Dateien, die vollständig mit .NET‑PowerPoint‑Betrachtern kompatibel sind, ohne dass eine Microsoft‑Office‑Installation erforderlich ist. Verwenden Sie Aspose.Slides for Java, wenn Sie eine serverseitige, plattformübergreifende Lösung benötigen, die .NET PPTX‑Dateien erstellt oder aktualisiert, über 50 Diagrammtypen unterstützt und Dateien bis zu 500 MB verarbeitet, ohne das gesamte Dokument in den Speicher zu laden. Seine API funktioniert in Java, Kotlin, Scala oder jeder JVM‑Sprache und liefert das gleiche Ergebnis, das .NET‑Entwickler erwarten.

## Voraussetzungen
- **Aspose.Slides for Java** Bibliothek (Version 25.4 oder höher).  
- Maven, Gradle oder ein manueller JAR‑Download.  
- Grundkenntnisse in Java und Vertrautheit mit der PPTX‑Dateistruktur.

## Einrichtung von Aspose.Slides für Java
### Maven-Installation
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle-Installation
Fügen Sie diese Zeile in Ihre `build.gradle`‑Datei ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie das neueste JAR von der offiziellen Release‑Seite herunterladen: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Lizenzbeschaffung**  
Beginnen Sie mit einer kostenlosen Testversion, indem Sie eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) herunterladen. Für den Produktionseinsatz erwerben Sie eine Voll‑Lizenz, um alle Funktionen freizuschalten und Evaluationswasserzeichen zu entfernen.

## Schritt‑für‑Schritt‑Implementierungsanleitung
Unter jedem Schritt finden Sie einen knappen Code‑Snippet (unverändert aus dem Original‑Tutorial) gefolgt von einer Erklärung, was er tut.

### Schritt 1: Leere Präsentation erstellen
`Presentation` ist die Einstiegsklasse, die eine PowerPoint‑Datei im Speicher repräsentiert.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Wir beginnen mit einer leeren PPTX‑Datei, die uns eine Leinwand zum Hinzufügen von Diagrammen bietet.*

### Schritt 2: Gestapeltes Säulendiagramm zur Folie hinzufügen
`Chart` repräsentiert eine Diagrammform innerhalb einer Folie. `ChartType.StackedColumn` gibt ein **stacked column chart** an.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Die `addChart`‑Methode erstellt ein **stacked column chart** und platziert es in der oberen linken Ecke der Folie.*

### Schritt 3: Serien zum Diagramm hinzufügen (Hauptziel)
`Series` kapselt eine einzelne Datenserie in einem Diagramm.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Hier **add series to chart** – jeder Aufruf erstellt eine neue Datenserie, die als separate Säulengruppe erscheint.*

### Schritt 4: Kategorien zum Diagramm hinzufügen
`Category` definiert ein X‑Achsen‑Label für Diagrammdaten.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategorien fungieren als X‑Achsen‑Beschriftungen und geben jeder Säule Bedeutung.*

### Schritt 5: Serien‑Daten befüllen
`DataPoint` hält einen numerischen Wert für eine Serie bei einer bestimmten Kategorie.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Datenpunkte geben jeder Serie ihre numerischen Werte, die das Diagramm als Balkenhöhen rendert.*

### Schritt 6: Lückenbreite für Diagramm‑Seriengruppe festlegen
`SeriesGroup` steuert Layout‑Eigenschaften für eine Gruppe von Serien, wie die Lückenbreite.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Die Anpassung der Lückenbreite verbessert die Lesbarkeit, insbesondere wenn viele Kategorien vorhanden sind.*

## Häufige Anwendungsfälle
- **Finanzberichterstattung** – Vergleich des Quartalsumsatzes über Geschäftsbereiche hinweg.  
- **Projekt‑Dashboards** – Anzeige der Aufgaben‑Abschluss‑Prozentsätze pro Team.  
- **Marketing‑Analyse** – Visualisierung der Kampagnenleistung nebeneinander.  
Diese Szenarien profitieren vom **stacked column chart example**, da sie die Beiträge einzelner Kategorien zum Gesamtergebnis hervorheben.

## Leistungstipps
- **Wiederverwenden Sie das `Presentation`‑Objekt**, wenn Sie mehrere Diagramme erstellen, um den Speicheraufwand zu reduzieren.  
- **Begrenzen Sie die Anzahl der Datenpunkte** auf das für die visuelle Geschichte erforderliche Minimum; Aspose.Slides kann 10.000 Punkte verarbeiten, aber die Rendergeschwindigkeit sinkt nach etwa 5.000.  
- **Entsorgen Sie Objekte** (`presentation.dispose()`) nach dem Speichern, um Ressourcen freizugeben und Speicherlecks zu vermeiden.

## Häufig gestellte Fragen
**Q: Kann ich neben gestapelten Säulen weitere Diagrammtypen hinzufügen?**  
**A:** Ja, Aspose.Slides unterstützt Linien-, Kreis-, Flächen-, Radar-, Blasen‑ und über 50 weitere Diagrammtypen, die alle über dieselbe `addChart`‑Methode zugänglich sind.

**Q: Benötige ich eine separate Lizenz für .NET‑Ausgabe?**  
**A:** Nein, dieselbe Java‑Lizenz funktioniert für alle Ausgabeformate, einschließlich .NET PPTX‑Dateien.

**Q: Wie ändere ich die Farbpalette des Diagramms?**  
**A:** Verwenden Sie `series.getFormat().getFill().setFillType(FillType.Solid)` und setzen Sie anschließend das gewünschte `Color`‑Objekt für jede Serie.

**Q: Ist es möglich, Datenbeschriftungen programmgesteuert hinzuzufügen?**  
**A:** Absolut. Rufen Sie `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` auf, um den numerischen Wert auf jeder Säule anzuzeigen.

**Q: Was ist, wenn ich eine bestehende Präsentation aktualisieren muss?**  
**A:** Laden Sie die Datei mit `new Presentation("existing.pptx")`, ändern Sie das Diagramm mit denselben API‑Aufrufen und speichern Sie sie wieder auf die Festplatte.

## Fazit
Sie haben nun einen vollständigen End‑zu‑Ende‑Leitfaden, wie Sie **add series to chart** durchführen, ein **stacked column chart** erstellen und dessen Erscheinungsbild in .NET‑Präsentationen mit Aspose.Slides für Java feinabstimmen. Experimentieren Sie mit verschiedenen Diagrammtypen, Farben und Datenquellen, um überzeugende visuelle Berichte zu erstellen, die Stakeholder beeindrucken und datenbasierte Entscheidungen vorantreiben.

---

**Zuletzt aktualisiert:** 2026-06-08  
**Getestet mit:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man prozentbasierte gestapelte Säulendiagramme in .NET mit Aspose.Slides erstellt](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Meisterhafte Erstellung und Manipulation von Diagrammserien mit Aspose.Slides .NET für effektive Datenvisualisierung](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Spezifische Diagrammserien‑Datenpunkte mit Aspose.Slides .NET löschen](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}