---
date: '2026-01-17'
description: Erfahren Sie, wie Sie einer Diagrammserie Daten hinzufügen und gestapelte
  Säulendiagramme in .NET‑Präsentationen mit Aspose.Slides für Java anpassen.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Serie zum Diagramm hinzufügen mit Aspose.Slides für Java in .NET
url: /de/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meistern der Diagrammanpassung in .NET‑Präsentationen mit Aspose.Slides für Java

## Einleitung
Im Bereich datengetriebener Präsentationen sind Diagramme unverzichtbare Werkzeuge, die Rohdaten in überzeugende visuelle Geschichten verwandeln. Wenn Sie programmatisch **add series to chart** hinzufügen müssen, insbesondere in .NET‑Präsentationsdateien, kann die Aufgabe überwältigend wirken. Glücklicherweise bietet **Aspose.Slides for Java** eine leistungsstarke, sprachunabhängige API, die die Erstellung und Anpassung von Diagrammen einfach macht – selbst wenn Ihr Zielformat ein .NET PPTX ist.

In diesem Tutorial erfahren Sie, wie Sie **add series to chart** hinzufügen, wie Sie **how to add chart** vom Typ gestapelte Säule hinzufügen und wie Sie visuelle Aspekte wie die Lückenbreite feinabstimmen. Am Ende können Sie dynamische, datenreiche Folien erzeugen, die professionell und poliert aussehen.

**Was Sie lernen werden**
- Wie man eine leere Präsentation mit Aspose.Slides erstellt  
- Wie man ein **add stacked column chart** zu einer Folie hinzufügt  
- Wie man **add series to chart** hinzufügt und Kategorien definiert  
- Wie man Datenpunkte befüllt und visuelle Einstellungen anpasst  

Lassen Sie uns Ihre Entwicklungsumgebung vorbereiten.

## Schnelle Antworten
- **Was ist die primäre Klasse, um eine Präsentation zu starten?** `Presentation`  
- **Welche Methode fügt ein Diagramm zu einer Folie hinzu?** `slide.getShapes().addChart(...)`  
- **Wie fügt man eine neue Serie hinzu?** `chart.getChartData().getSeries().add(...)`  
- **Kann man die Lückenbreite zwischen Balken ändern?** Ja, mittels `setGapWidth()` in der Seriengruppe  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine gültige Aspose.Slides for Java Lizenz ist erforderlich  

## Was bedeutet “add series to chart”?
Das Hinzufügen einer Serie zu einem Diagramm bedeutet das Einfügen einer neuen Datensammlung, die das Diagramm als ein separates visuelles Element (z. B. einen neuen Balken, eine Linie oder ein Segment) darstellt. Jede Serie kann ihre eigenen Werte, Farben und Formatierungen besitzen, sodass Sie mehrere Datensätze nebeneinander vergleichen können.

## Warum Aspose.Slides für Java verwenden, um .NET‑Präsentationen zu ändern?
- **Cross‑platform**: Schreiben Sie Java‑Code einmal und zielen Sie auf PPTX‑Dateien, die von .NET‑Anwendungen verwendet werden.  
- **Keine COM‑ oder Office‑Abhängigkeiten**: Funktioniert auf Servern, CI‑Pipelines und Containern.  
- **Umfangreiche Diagramm‑API**: Unterstützt über 50 Diagrammtypen, einschließlich gestapelter Säulendiagramme.  

## Voraussetzungen
1. **Aspose.Slides for Java** Bibliothek (Version 25.4 oder neuer).  
2. Maven‑ oder Gradle‑Build‑Tool, oder ein manueller JAR‑Download.  
3. Grundlegende Java‑Kenntnisse und Vertrautheit mit der PPTX‑Struktur.  

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
Laden Sie das neueste JAR von der offiziellen Release‑Seite herunter: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Lizenzbeschaffung**  
Starten Sie mit einer kostenlosen Testversion, indem Sie eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) herunterladen. Für den Produktionseinsatz erwerben Sie eine Voll‑Lizenz, um alle Funktionen freizuschalten.

## Schritt‑für‑Schritt‑Implementierungs‑Leitfaden
Nach jedem Schritt finden Sie ein prägnantes Code‑Snippet (unverändert aus dem Original‑Tutorial) sowie eine Erklärung seiner Funktion.

### Schritt 1: Erstelle eine leere Präsentation
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

### Schritt 2: Füge ein gestapeltes Säulendiagramm zur Folie hinzu
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Die Methode `addChart` erstellt ein **add stacked column chart** und platziert es in der oberen linken Ecke der Folie.*

### Schritt 3: Serie zum Diagramm hinzufügen (Hauptziel)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Hier **add series to chart** – jeder Aufruf erstellt eine neue Datenserie, die als separate Spaltengruppe erscheint.*

### Schritt 4: Kategorien zum Diagramm hinzufügen
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Kategorien fungieren als X‑Achsen‑Beschriftungen und verleihen jeder Spalte Bedeutung.*

### Schritt 5: Serien‑Daten befüllen
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
*Datenpunkte geben jeder Serie ihre numerischen Werte, die das Diagramm als Balkenhöhen darstellt.*

### Schritt 6: Lückenbreite für die Diagramm‑Seriengruppe festlegen
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Das Anpassen der Lückenbreite verbessert die Lesbarkeit, besonders wenn viele Kategorien vorhanden sind.*

## Häufige Anwendungsfälle
- **Finanzberichterstattung** – Vergleich des Quartalsumsatzes über Geschäftsbereiche hinweg.  
- **Projekt‑Dashboards** – Anzeige der Aufgaben‑Abschluss‑Prozentsätze pro Team.  
- **Marketing‑Analytik** – Visualisierung der Kampagnenleistung nebeneinander.  

## Leistungstipps
- **Wiederverwenden Sie das `Presentation`‑Objekt** beim Erstellen mehrerer Diagramme, um den Speicherverbrauch zu reduzieren.  
- **Begrenzen Sie die Anzahl der Datenpunkte** auf das für die visuelle Geschichte erforderliche Minimum.  
- **Entsorgen Sie Objekte** (`presentation.dispose()`) nach dem Speichern, um Ressourcen freizugeben.  

## Häufig gestellte Fragen
**F: Kann ich andere Diagrammtypen außer gestapelter Säule hinzufügen?**  
A: Ja, Aspose.Slides unterstützt Linien-, Kreis-, Flächen‑ und viele weitere Diagrammtypen.

**F: Benötige ich eine separate Lizenz für .NET‑Ausgabe?**  
A: Nein, dieselbe Java‑Lizenz funktioniert für alle Ausgabeformate, einschließlich .NET‑PPTX‑Dateien.

**F: Wie ändere ich die Farbpalette des Diagramms?**  
A: Verwenden Sie `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` und setzen Sie die gewünschte `Color`.

**F: Ist es möglich, Datenbeschriftungen programmatisch hinzuzufügen?**  
A: Absolut. Rufen Sie `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` auf, um Werte anzuzeigen.

**F: Was, wenn ich eine bestehende Präsentation aktualisieren muss?**  
A: Laden Sie die Datei mit `new Presentation("existing.pptx")`, ändern Sie das Diagramm und speichern Sie sie erneut.

## Fazit
Sie haben nun eine vollständige End‑zu‑End‑Anleitung, wie Sie **add series to chart** durchführen, ein **stacked column chart** erstellen und dessen Erscheinungsbild in .NET‑Präsentationen mit Aspose.Slides für Java feinabstimmen. Experimentieren Sie mit verschiedenen Diagrammtypen, Farben und Datenquellen, um überzeugende visuelle Berichte zu erstellen, die Stakeholder beeindrucken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose