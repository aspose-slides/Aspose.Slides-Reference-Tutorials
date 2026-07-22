---
date: '2026-07-22'
description: Erfahren Sie, wie Sie mit der Aspose Slides Maven Dependency ein stacked
  column chart in Java erstellen, data labels hinzufügen, das vertical axis number
  format ändern und das Ergebnis als PPTX-Datei exportieren.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency ermöglicht es Ihnen, ein stacked column
  chart in Java zu erstellen, data labels anzupassen, das vertical axis format zu
  ändern und als PPTX zu speichern – alles mit prägnantem, produktionsreifem Code.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
url: /de/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven-Abhängigkeit: Gestapelte Säulendiagramm in Java

## Einführung

Verbessern Sie Ihre Präsentationen, indem Sie aussagekräftige Datenvisualisierungen mit der Leistungsfähigkeit von **Aspose.Slides for Java** einbinden. In diesem Leitfaden erstellen Sie ein **gestapeltes Säulendiagramm**, das professionell wirkt – egal, ob Sie Geschäftsberichte vorbereiten oder Projektdaten präsentieren. Am Ende dieses Tutorials können Sie:

- Ihre Umgebung mit der **Aspose Slides Maven-Abhängigkeit** einrichten
- Eine Präsentation von Grund auf erstellen
- **Ein prozentual gestapeltes Diagramm** hinzufügen und dessen Aussehen anpassen
- **Diagrammdatenbeschriftungen formatieren** und **das Zahlenformat der vertikalen Achse ändern**
- **Die Präsentation als PPTX** mit einer einzigen Codezeile speichern

## Schnellantworten
- **Welche Bibliothek benötige ich?** Fügen Sie die `aspose-slides` Maven/Gradle‑Abhängigkeit hinzu (siehe unten „Aspose Slides Maven‑Abhängigkeit“).  
- **Welcher Diagrammtyp erzeugt eine gestapelte Ansicht?** Verwenden Sie `ChartType.PercentsStackedColumn` für ein prozentual gestapeltes Säulendiagramm.  
- **Wie ändere ich das Zahlenformat der Achse?** Rufen Sie `IAxis.setNumberFormat()` auf und setzen Sie `setNumberFormatLinkedToSource(false)`.  
- **Kann ich Datenbeschriftungen anpassen?** Ja – iterieren Sie über jedes `IChartDataPoint` und weisen Sie ein benutzerdefiniertes `ITextFrame` zu.  
- **Wie speichere ich die Datei?** Verwenden Sie `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Was ist ein gestapeltes Säulendiagramm?
Ein gestapeltes Säulendiagramm visualisiert mehrere Datenreihen, die in jeder Kategorien‑Säule vertikal übereinander liegen, wobei die **prozentual gestapelte** Variante jede Säule auf 100 % normiert, um den Vergleich von Anteilen zu erleichtern. Dieses Format ermöglicht es Betrachtern, schnell zu erkennen, wie jeder Bestandteil zum Ganzen in den verschiedenen Kategorien beiträgt, wodurch Trends und relative Größen sofort ersichtlich werden.

## Warum Aspose.Slides für Java verwenden?
Aspose.Slides für Java ermöglicht das Erzeugen, Bearbeiten und Konvertieren von PowerPoint‑Dateien **ohne Microsoft Office** und unterstützt **mehr als 50 Ausgabeformate** unter Windows, Linux und macOS. Die Bibliothek läuft vollständig auf einer JRE, was serverseitige Automatisierung und Hochdurchsatz‑Reporting erlaubt. Zudem bietet sie feinkörnige Kontrolle über Diagrammobjekte, Folienlayouts und Dokumenteigenschaften – ideal für die Präsentationserstellung auf Unternehmens‑Level.

## Voraussetzungen
- **Java Development Kit (JDK):** 8 oder höher  
- **IDE:** IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor  
- **Build‑Tool:** Maven oder Gradle (optional, aber empfohlen)  
- **Grundkenntnisse in Java** – Sie sollten mit Klassen und Methoden vertraut sein  

## Aspose.Slides für Java einrichten
Um zu beginnen, fügen Sie die Aspose.Slides‑Bibliothek zu Ihrem Projekt hinzu.

### Aspose Slides Maven‑Abhängigkeit
Fügen Sie das Folgende zu Ihrer `pom.xml` hinzu (dies ist die **aspose slides maven dependency**, die Sie benötigen):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑Alternative
Falls Sie Gradle bevorzugen, ergänzen Sie diese Zeile in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie das neueste JAR von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung
Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides zu erkunden. Um Evaluationsbeschränkungen zu entfernen, sollten Sie eine temporäre oder gekaufte Lizenz erwerben.

- **Kostenlose Testversion:** Zugriff auf eingeschränkte Funktionen ohne sofortige Kosten.  
- **Temporäre Lizenz:** Anforderung über die [Aspose‑Website](https://purchase.aspose.com/temporary-license/).  
- **Kauf:** Besuchen Sie die Kaufseite für vollen Zugriff.

### Grundlegende Initialisierung
`Presentation` ist die Kernklasse von Aspose.Slides, die eine PowerPoint‑Datei im Speicher repräsentiert. Das folgende Minimal‑Snippet zeigt, wie ein `Presentation`‑Objekt erstellt wird:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementierungs‑Leitfaden

### Eine Präsentation erstellen und eine Folie hinzufügen
**Übersicht:**  
Zunächst erstellen wir eine leere Präsentation und prüfen, dass eine Folie vorhanden ist.

#### Schritt 1: Präsentationsobjekt initialisieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Schritt 2: Präsentation speichern
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Prozentual gestapeltes Säulendiagramm zu einer Folie hinzufügen
**Übersicht:**  
Jetzt platzieren wir ein **prozentual gestapeltes Diagramm** auf der ersten Folie.

`ChartType.PercentsStackedColumn` gibt den Diagrammtyp für ein prozentual gestapeltes Säulendiagramm an.

#### Schritt 1: Folie initialisieren und zugreifen
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Schritt 2: Diagramm zur Folie hinzufügen
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Zahlenformat der Diagrammachse anpassen
**Übersicht:**  
Zur besseren Lesbarkeit ändern wir **das Zahlenformat der vertikalen Achse** auf Prozentsätze.

`IAxis` ist das Interface, das eine Diagrammachse repräsentiert und Format‑ sowie Skalierungsanpassungen ermöglicht.

#### Schritt 1: Diagramm hinzufügen und zugreifen
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Schritt 2: Benutzerdefiniertes Zahlenformat setzen
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Reihen und Datenpunkte zum Diagramm hinzufügen
**Übersicht:**  
Wir füllen das Diagramm mit Beispieldatenreihen.

#### Schritt 1: Präsentation und Diagramm initialisieren
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Schritt 2: Datenreihen hinzufügen
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Füllfarbe der Reihen formatieren
**Übersicht:**  
Geben Sie jeder Reihe eine eindeutige Farbe, um das Diagramm leichter lesbar zu machen.

#### Schritt 1: Diagramm initialisieren und zugreifen
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Schritt 2: Füllfarben setzen
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Datenbeschriftungen formatieren
**Übersicht:**  
Jetzt **formatieren wir die Diagrammdatenbeschriftungen**, sodass sie benutzerdefinierten Text anzeigen.

`IChartDataPoint` repräsentiert einen einzelnen Datenpunkt innerhalb einer Diagrammreihe, und `ITextFrame` enthält den Beschriftungstext.

#### Schritt 1: Diagrammreihen und Datenpunkte zugreifen
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Schritt 2: Datenbeschriftungen anpassen
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Häufige Probleme und Lösungen
- **Diagramm erscheint leer:** Stellen Sie sicher, dass Sie mindestens eine Datenreihe und einen Datenpunkt hinzugefügt haben, bevor Sie speichern.  
- **Achsenzahlen zeigen keine Prozentsätze:** Denken Sie daran, `verticalAxis.setNumberFormatLinkedToSource(false)` zu setzen; sonst wird das benutzerdefinierte Format ignoriert.  
- **Lizenz‑Evaluierungsnachricht:** Laden Sie eine gültige Lizenzdatei, bevor Sie das `Presentation`‑Objekt erstellen, um das Evaluationsbanner zu unterdrücken.

## Häufig gestellte Fragen

**F: Kann ich diesen Code mit Java 11 oder neuer verwenden?**  
A: Ja. Die Bibliothek unterstützt JDK 8+; verwenden Sie einfach den passenden Klassifizierer (z. B. `jdk16` für JDK 16 oder höher).

**F: Wie exportiere ich das Diagramm als Bild statt als PPTX?**  
A: Verwenden Sie `chart.getImage().save("chart.png", ImageFormat.Png);` nachdem das Diagramm zur Folie hinzugefügt wurde.

**F: Ist es möglich, eine Legende zum gestapelten Säulendiagramm hinzuzufügen?**  
A: Absolut. Rufen Sie `chart.getChartTitle().addTextFrameForOverriding("My Chart");` auf und konfigurieren Sie `chart.getLegend()` nach Bedarf.

**F: Was, wenn ich Daten nach der Generierung der Präsentation aktualisieren muss?**  
A: Sie können die Zellen des `ChartDataWorkbook` ändern und anschließend `chart.refresh();` aufrufen, um die Änderungen zu übernehmen.

**F: Funktioniert Aspose.Slides auf Linux‑Servern?**  
A: Ja. Die Bibliothek ist reines Java und läuft auf jedem Betriebssystem mit einer kompatiblen JRE.

## Fazit
Durch die Befolgung dieses Leitfadens haben Sie gelernt, wie man in Java mit der **Aspose Slides Maven‑Abhängigkeit** ein **gestapeltes Säulendiagramm** erstellt – von der Umgebungseinrichtung bis zur feinen visuellen Gestaltung. Experimentieren Sie mit verschiedenen Datensätzen, Farben und Beschriftungsformaten, um Ihre Berichte wirklich hervorzuheben.

---

**Zuletzt aktualisiert:** 2026-07-22  
**Getestet mit:** Aspose.Slides 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [How to create clustered column chart in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [How to Set Number Formats in Chart Data Points Using Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}