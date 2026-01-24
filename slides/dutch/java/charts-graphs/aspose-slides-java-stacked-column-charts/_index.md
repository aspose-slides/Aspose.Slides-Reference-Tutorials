---
date: '2026-01-24'
description: Leer hoe je een grafiek maakt met Aspose.Slides voor Java, inclusief
  het instellen van een procentueel gestapelde kolom, asformattering en aanpassing
  van gegevenslabels.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: 'Hoe maak je een grafiek: gestapelde kolom met Aspose.Slides Java'
url: /nl/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Beheers gestapelde kolomgrafieken in Java met Aspose.Slides: Een uitgebreide gids

## Introduction

Verhoog uw presentaties door inzichtelijke datavisualisaties toe te voegen met de kracht van Aspose.Slides voor Java. In deze tutorial leert u **hoe u een chart maakt**‑gedreven dia's die ruwe cijfers omzetten in duidelijke verhalen—of u nu bedrijfsrapporten, projectdashboards of marketingpresentaties voorbereidt.

We lopen stap voor stap door het instellen van uw omgeving, het toevoegen van een **percentage stacked column**‑grafiek, en het aanpassen van assen, series en gegevenslabels zodat de uiteindelijke presentatie er gepolijst en professioneel uitziet.

Laten we duiken in het maken van presentaties die uw publiek boeien.

## Quick Answers
- **Wat is de primaire bibliotheek?** Aspose.Slides for Java
- **Welk Maven‑artifact voegt de bibliotheek toe?** `com.aspose:aspose-slides` (zie *aspose slides maven* sectie)
- **Hoe voeg ik een percentage stacked column‑grafiek toe?** Use `ChartType.PercentsStackedColumn` when calling `addChart`
- **Kan ik de getallen op de grafiekas formatteren?** Yes – set `verticalAxis.setNumberFormat("0.00%")`
- **Hoe pas ik de tekst van gegevenslabels aan?** Override each point’s `ITextFrame` via `point.getLabel().getTextFrameForOverriding()`

## What is a Stacked Column Chart?
Een gestapelde kolomgrafiek groepeert meerdere gegevensreeksen in één kolom, waardoor u de totale omvang kunt vergelijken terwijl u nog steeds de bijdrage van elk component ziet. De **percentage stacked column**‑variant normaliseert elke kolom tot 100 %, waardoor hij ideaal is om proportionele gegevens over categorieën weer te geven.

## Why Use Aspose.Slides for Java?
- **No Office installation required** – genereer PPTX‑bestanden op elke server.
- **Full‑featured chart API** – ondersteunt alle grafiektype­s, inclusief de percentage stacked column.
- **Cross‑platform compatibility** – werkt op Windows, Linux en macOS.
- **Easy Maven/Gradle integration** – zie de *aspose slides maven* snippet hieronder.

## Prerequisites
- **Java Development Kit (JDK):** 8 of hoger.
- **IDE:** IntelliJ IDEA, Eclipse, of een willekeurige Java‑compatibele editor.
- **Build tool (optioneel):** Maven of Gradle voor afhankelijkheidsbeheer.
- **Basis Java‑kennis** – u moet vertrouwd zijn met klassen, methoden en collecties.

## Setting Up Aspose.Slides for Java
Om te beginnen moet u de Aspose.Slides‑bibliotheek in uw project opnemen.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Download anders de nieuwste JAR van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
U kunt beginnen met een gratis proefversie om de functies van Aspose.Slides te verkennen. Om evaluatiebeperkingen te verwijderen, overweeg een tijdelijke of aangeschafte licentie.

- **Free Trial:** Toegang tot beperkte functies zonder directe kosten.  
- **Temporary License:** Aanvragen via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Purchase:** Bezoek de aankooppagina voor volledige toegang.

### Basic Initialization
Zo initialiseert u Aspose.Slides in uw Java‑applicatie:
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

## How to Create Chart: Step-by-Step Guide

### Creating a Presentation and Adding a Slide
**Overview:** Begin met het maken van een eenvoudige presentatie met een eerste dia. Dit is uw basis voor verdere verbeteringen.

#### Step 1: Initialize Presentation Object
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

#### Step 2: Save the Presentation
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:** Verbeter uw dia door een **percentage stacked column**‑grafiek toe te voegen, waardoor eenvoudige datacomparatie mogelijk is.

#### Step 1: Initialize and Access Slide
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

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview:** Pas het getalformaat van de verticale as van uw grafiek aan voor betere leesbaarheid.

#### Step 1: Add and Access Chart
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

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview:** Vul uw grafiek met **add series data** zodat deze informatief en visueel aantrekkelijk wordt.

#### Step 1: Initialize Presentation and Chart
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

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview:** Verbeter de esthetiek van uw grafiek door de vulkleur van elke serie te formatteren.

#### Step 1: Initialize and Access Chart
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

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview:** Maak uw gegevenslabels beter leesbaar door **format chart data labels** te gebruiken om aangepaste tekst weer te geven.

#### Step 1: Access Chart Series and Data Points
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

#### Step 2: Customize Data Labels
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

## Common Use Cases
- **Quarterly sales dashboards** – visualiseer de bijdragen van productlijnen als een percentage van de totale omzet.  
- **Project resource allocation** – toon hoe teamleden over taken zijn verdeeld in één kolom.  
- **Survey results** – vergelijk antwoordverdelingen over meerdere vragen.

## Frequently Asked Questions

**Q: Heb ik een betaalde licentie nodig om gest**  
A: Een gratis proefvers Kan ik het grafiektibel met Java 11 en nieuwer?**  
A: Absoluut. De bibliotheek werkt met JDK 8 tot en met JDKjdk16`).

**Q: Wat als ik meer dan drie series moet toevoegen?**  
A: Herhaal simpelweg het blok voor het toevoegen van series, en pas de werkbladcel‑referenties aan voor elke nieuwe serie.

## Conclusion de Maven/Gradle‑afhankelijkheid tot het aanpassen van de assen, serieskleuren en gegevenslabels van een percentage stacked column‑grafiek. Experimenteer met verschillende datasets, pas uw eigen merkkleuren toe, en integreer deze dia's in geautomatiseerde rapportage‑pijplijnen.

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}