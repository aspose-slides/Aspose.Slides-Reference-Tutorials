---
date: '2026-09-12'
description: Erfahren Sie, wie Sie Maven Aspose Slides verwenden, um dynamic stock
  charts in PowerPoint mit Java hinzuzufügen und anzupassen. Enthält Einrichtung,
  Hinzufügen von data series, formatting lines und saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides Tutorial zeigt, wie man dynamic stock charts in
  PowerPoint mit Java erstellt und anpasst, einschließlich data series, line formatting
  und saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides Anleitung: Erstellen Sie dynamic stock charts in PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: Erstellen Sie dynamic stock charts in PowerPoint mit
  Java'
url: /de/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: dynamische Aktiencharts in PowerPoint mit Java erstellen

## Einführung

**Maven Aspose Slides** ermöglicht es Ihnen, programmgesteuert anspruchsvolle PowerPoint-Präsentationen aus Java zu erstellen. In diesem Tutorial lernen Sie, wie man dynamische Aktiencharts erstellt, Datenreihen hinzufügt und formatiert, Diagrammlinien anpasst und schließlich die Datei speichert. Egal, ob Sie ein Finanzanalyst sind, der Quartalsberichte vorbereitet, oder ein Entwickler, der automatisierte Foliendecks erstellt, die nachfolgenden Schritte bieten Ihnen eine vollständige, produktionsreife Lösung.

**Was Sie lernen werden**
- Wie man Maven mit Aspose.Slides für Java einrichtet  
- Wie man ein Aktienchart hinzufügt und Standarddaten löscht  
- Wie man **Datenreihen‑Diagramm hinzufügt** und **Diagrammlinien formatiert**  
- Wie man **chart‑java‑spezifische** visuelle Elemente anpasst  
- Wie man die aktualisierte Präsentation speichert

Bereit, Rohdaten in auffällige Aktienvisualisierungen zu verwandeln? Lassen Sie uns beginnen!

## Schnelle Antworten
- **Welches Maven‑Artefakt benötige ich?** `aspose-slides` Version 25.4 (oder neuer).  
- **Kann ich das auf jedem Betriebssystem ausführen?** Ja – die Bibliothek ist reines Java und funktioniert unter Windows, macOS und Linux.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Diagrammtypen werden unterstützt?** Über 70 integrierte Diagrammtypen, darunter Aktien-, Linien‑ und Balkendiagramme.  
- **Wie groß darf eine Präsentation sein, die ich verarbeiten kann?** Aspose.Slides kann Dateien mit über 500 Folien verarbeiten, ohne die gesamte Datei in den Speicher zu laden.

## Was ist Maven Aspose Slides?

`Aspose.Slides for Java` ist eine Java‑API, die das Erstellen, Manipulieren und Konvertieren von PowerPoint‑Dateien ohne Microsoft Office ermöglicht. Die Maven‑Integration vereinfacht das Abhängigkeitsmanagement, sodass Sie die Bibliothek direkt aus Maven Central beziehen können.

## Warum Maven Aspose Slides für Aktiencharts verwenden?

Aspose.Slides unterstützt **über 70 Diagrammtypen** und kann mehrseitige Präsentationen auf typischer Serverhardware in weniger als einer Sekunde rendern. Seine **High‑Low‑Linie**‑ und **Auf‑/Ab‑Balken**‑Funktionen bieten Ihnen präzise Kontrolle über finanzielle Visualisierungen, weit über das hinaus, was die PowerPoint‑Benutzeroberfläche bietet.

## Voraussetzungen

- **Java Development Kit (JDK)** – Version 11 oder höher.  
- **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Editor Ihrer Wahl.  
- **Aspose.Slides for Java** – Version 25.4 (die zum Zeitpunkt des Schreibens aktuelle Version).  

### Einrichtung von Aspose.Slides für Java

#### Maven
Um Aspose.Slides in Ihr Projekt mit Maven zu integrieren, fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Für Gradle‑Benutzer fügen Sie dies in Ihre `build.gradle` ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direkter Download
Alternativ können Sie das neueste JAR von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

**Lizenzbeschaffung** – beginnen Sie mit einer kostenlosen Testversion oder beantragen Sie eine temporäre Lizenz. Für die kommerzielle Nutzung erwerben Sie eine Voll‑Lizenz.

Für detaillierte API‑Referenz siehe die [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Wie man ein dynamisches Aktienchart Schritt für Schritt erstellt

Laden Sie Ihre Präsentation, fügen Sie ein Aktienchart hinzu, löschen Sie die Standarddaten und fügen Sie dann Ihre eigenen Serien und Kategorien ein. Die direkte Antwort auf die Kernfrage lautet:

> Laden Sie ein vorhandenes PPTX mit `new Presentation("template.pptx")`, fügen Sie ein `Chart` vom Typ `ChartType.Stock` hinzu, löschen Sie dessen Standardserien und -kategorien und füllen Sie es anschließend mit Ihren eigenen Datenpunkten und Formatierungsoptionen. Rufen Sie schließlich `presentation.save("output.pptx", SaveFormat.Pptx)` auf.

### Präsentation initialisieren
#### Überblick
Beginnen Sie damit, eine vorhandene PowerPoint‑Datei zu laden, damit Sie sie direkt bearbeiten können.

#### Schritt für Schritt
1. **Importieren Sie die Bibliothek** – die Klasse `Presentation` ist der Einstiegspunkt für alle Folien‑Operationen.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Laden Sie die Präsentationsdatei** – geben Sie den Pfad zu Ihrer Vorlage‑PPTX an.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aktienchart zur Folie hinzufügen
#### Überblick
Fügen Sie ein Aktienchart auf die erste Folie der Präsentation ein.  
Die Klasse `Chart` repräsentiert ein Diagramm‑Shape, das zu einer Folie hinzugefügt werden kann.

#### Direkte Antwort
Sie fügen ein Aktienchart hinzu, indem Sie `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` aufrufen. Dies erzeugt ein Diagramm‑Objekt, das Sie sofort manipulieren können.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Vorhandene Datenserien und Kategorien im Diagramm löschen
#### Überblick
Entfernen Sie alle vorab gefüllten Serien oder Kategorien, damit Sie mit einem sauberen Datensatz beginnen können.  
Das Objekt `ChartData` enthält die Serien und Kategorien für ein Diagramm.

#### Direkte Antwort
Rufen Sie `chart.getChartData().getSeries().clear()` und `chart.getChartData().getCategories().clear()` auf, um den Standardinhalt zu löschen, bevor Sie Ihre eigenen hinzufügen.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Kategorien zu Diagrammdaten hinzufügen
#### Überblick
Definieren Sie die X‑Achsen‑Kategorien (z. B. Daten), die Ihre Aktienwerte gruppieren.  
Ein `ChartCategory` stellt ein X‑Achsen‑Label für ein Diagramm dar.

#### Direkte Antwort
Erstellen Sie für jedes Label ein neues `ChartCategory` mit `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` und wiederholen Sie dies für jeden Monat oder Zeitraum.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Datenreihen zum Diagramm hinzufügen
#### Überblick
Fügen Sie die vier wesentlichen Serien hinzu: Open, High, Low und Close.  
Ein `ChartSeries` enthält eine Sammlung von Datenpunkten für eine bestimmte Serie im Diagramm.

#### Direkte Antwort
Für jede Serie rufen Sie `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` auf. Damit wird die Serie im Daten‑Workbook des Diagramms registriert.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Datenpunkte zu Serien hinzufügen
#### Überblick
Füllen Sie jede Serie mit numerischen Werten, die Aktienkurse darstellen.  
Ein `DataPoint` stellt einen einzelnen Wert in einer Serie dar.

#### Direkte Antwort
Durchlaufen Sie Ihre Datensammlung und verwenden Sie `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (oder die passende Methode für den Seriotyp), um jeden Punkt einzufügen.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### High‑Low‑Linien und Auf‑/Ab‑Balken formatieren
#### Überblick
Passen Sie den visuellen Stil der High‑Low‑Verbindungen und der Auf‑/Ab‑Balken‑Füllungen an.  
Ein `Marker` definiert das visuelle Symbol für einen Datenpunkt.

#### Direkte Antwort
Setzen Sie `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` und konfigurieren Sie `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)`, um die Linienstärke und -farbe zu steuern.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Auf‑/Ab‑Balken anzeigen
Verwenden Sie die Methode `setShowUpDownBars(true)` des Diagramms, um die Auf‑/Ab‑Balken sichtbar zu machen.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Datenbeschriftungen auf High‑Low‑Linien anpassen
#### Überblick
Zeigen Sie numerische Werte direkt auf den High‑Low‑Linien für eine schnelle Referenz an.  
Ein `DataLabel` steuert das Aussehen von Beschriftungen, die an Datenpunkten befestigt sind.

#### Direkte Antwort
Aktivieren Sie Datenbeschriftungen mit `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` und formatieren Sie sie nach Bedarf.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Auf‑/Ab‑Balken‑Füllfarbe festlegen
#### Überblick
Geben Sie den Auf‑Balken eine grüne Füllung und den Ab‑Balken eine rote Füllung, um Marktbewegungen intuitiv darzustellen.  
Das Objekt `UpDownBars` bietet Zugriff auf die Formatierung der Auf‑ und Ab‑Balken.

#### Direkte Antwort
Wenden Sie `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` an und setzen Sie die Vollfarbe auf `Color.GREEN`; wiederholen Sie dies für den Ab‑Balken mit `Color.RED`.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### PowerPoint‑Datei speichern
#### Überblick
Speichern Sie Ihre Änderungen in einer neuen PPTX‑Datei.  
Die Methode `save` schreibt die Präsentation in das angegebene Format auf die Festplatte.

#### Direkte Antwort
Rufen Sie `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` auf – dies schreibt die modifizierte Präsentation im Standard‑PowerPoint‑Format auf die Festplatte.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Häufige Probleme und Fehlersuche

- **Diagramm wird nicht angezeigt** – stellen Sie sicher, dass die X/Y‑Koordinaten und Abmessungen des Diagramms innerhalb der Folienränder liegen.  
- **Datenpunkte fehlen** – prüfen Sie, ob die Zellindizes des Daten‑Workbooks mit der Serie/Zeile übereinstimmen, die Sie befüllen möchten.  
- **Lizenzausnahme** – eine temporäre Testlizenz läuft nach 30 Tagen ab; ersetzen Sie sie für Produktions‑Builds durch eine permanente Lizenz.  
- **Leistungsabfall bei großen Dateien** – verwenden Sie `Presentation.setCacheSize(0)`, um das Caching zu deaktivieren, wenn Sie Tausende von Folien in einem Batch verarbeiten.

## Häufig gestellte Fragen

**F: Kann ich diesen Code in einer Webanwendung verwenden?**  
A: Ja. Die Bibliothek ist reines Java, sodass Sie sie in jedem Servlet‑Container oder Spring‑Boot‑Service ausführen können.

**F: Unterstützt Aspose.Slides andere Diagrammtypen neben Aktien?**  
A: Absolut. Es unterstützt über 70 Diagrammtypen, darunter Linien-, Balken-, Kreis- und Radar‑Diagramme.

**F: Wie füge ich einem Diagramm programmgesteuert einen Titel hinzu?**  
A: Verwenden Sie `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` und formatieren Sie den Titel nach Bedarf.

**F: Gibt es ein Limit für die Anzahl der Datenpunkte pro Serie?**  
A: Praktisch können Sie zehntausende Punkte hinzufügen; der Speicherverbrauch skaliert linear, und die Bibliothek streamt Daten, um den Speicherbedarf gering zu halten.

**F: Welche Maven‑Koordinaten sollte ich für die neueste Version verwenden?**  
A: Die neueste Version ist stets unter `com.aspose:aspose-slides:25.4` (oder neuer) im Maven Central verfügbar.

**Zuletzt aktualisiert:** 2026-09-12  
**Getestet mit:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Verwandte Tutorials

- [aspose slides maven dependency: Diagramme in Präsentationen mit Aspose.Slides für Java hinzufügen und konfigurieren](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint‑Diagramm in Java erstellen – Präsentationen mit Diagrammen mit Aspose.Slides speichern](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint‑Diagramme erstellen und formatieren mit Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}