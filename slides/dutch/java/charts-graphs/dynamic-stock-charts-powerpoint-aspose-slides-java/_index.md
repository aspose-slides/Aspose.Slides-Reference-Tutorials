---
date: '2026-09-12'
description: Leer hoe u Maven Aspose Slides kunt gebruiken om dynamic stock charts
  toe te voegen en aan te passen in PowerPoint met Java. Inclusief installatie, het
  toevoegen van gegevensreeksen, het opmaken van lijnen en opslaan.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides tutorial laat zien hoe u dynamic stock charts
  kunt maken en aanpassen in PowerPoint met Java, met aandacht voor gegevensreeksen,
  lijnopmaak en opslaan.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides gids: maak dynamic stock charts in PowerPoint'
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
title: 'Maven Aspose Slides: maak dynamic stock charts in PowerPoint met Java'
url: /nl/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: dynamische aandelenkaarten maken in PowerPoint met Java

## Inleiding

**Maven Aspose Slides** laat je programmatic geavanceerde PowerPoint‑presentaties genereren vanuit Java. In deze tutorial leer je hoe je dynamische aandelenkaarten maakt, gegevensreeksen toevoegt en opmaakt, grafieklijnen aanpast, en uiteindelijk het bestand opslaat. Of je nu een financieel analist bent die kwartaalrapporten voorbereidt of een ontwikkelaar die geautomatiseerde presentaties bouwt, de onderstaande stappen bieden een complete, productieklare oplossing.

**Wat je zult leren**
- Hoe Maven met Aspose.Slides voor Java in te stellen  
- Hoe een aandelenkaart toe te voegen en standaardgegevens te wissen  
- Hoe **add data series chart** en **format chart lines** toe te voegen  
- Hoe **customize chart java**‑specifieke visuele elementen aan te passen  
- Hoe de bijgewerkte presentatie op te slaan

Klaar om ruwe cijfers om te zetten in opvallende aandelenvisualisaties? Laten we beginnen!

## Snelle antwoorden
- **Welk Maven‑artifact heb ik nodig?** `aspose-slides` versie 25.4 (of nieuwer).  
- **Kan ik dit op elk OS uitvoeren?** Ja – de bibliotheek is pure Java en werkt op Windows, macOS en Linux.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis tijdelijke licentie werkt voor testen; een volledige licentie is vereist voor productie.  
- **Welke grafiektype worden ondersteund?** Meer dan 70 ingebouwde grafiektype, inclusief Stock, Line en Bar.  
- **Hoe groot mag een presentatie zijn die ik kan verwerken?** Aspose.Slides kan bestanden met 500+ dia's aan zonder het hele bestand in het geheugen te laden.

## Wat is Maven Aspose Slides?

`Aspose.Slides for Java` is een Java‑API die het maken, manipuleren en converteren van PowerPoint‑bestanden mogelijk maakt zonder Microsoft Office. Maven‑integratie vereenvoudigt het beheer van afhankelijkheden, zodat je de bibliotheek rechtstreeks vanuit Maven Central kunt ophalen.

## Waarom Maven Aspose Slides gebruiken voor aandelenkaarten?

Aspose.Slides ondersteunt **70+ grafiektype** en kan presentaties van honderden pagina's renderen in minder dan een seconde op typische serverhardware. De **high‑low line**‑ en **up/down bar**‑functies geven je nauwkeurige controle over financiële visualisaties, veel meer dan wat de PowerPoint‑UI biedt.

## Vereisten

- **Java Development Kit (JDK)** – versie 11 of hoger.  
- **IDE** – IntelliJ IDEA, Eclipse, of elke editor die je verkiest.  
- **Aspose.Slides for Java** – versie 25.4 (de nieuwste op het moment van schrijven).  

### Instellen van Aspose.Slides voor Java

#### Maven
Om Aspose.Slides in je project te integreren met Maven, voeg je de volgende afhankelijkheid toe aan je `pom.xml`:

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
Voor Gradle‑gebruikers, voeg dit toe aan je `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Directe download
Alternatief kun je de nieuwste JAR downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License acquisition** – begin met een gratis proefversie of vraag een tijdelijke licentie aan. Voor commercieel gebruik, koop een volledige licentie.

Voor een gedetailleerde API‑referentie, zie de [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Hoe maak je stap voor stap een dynamische aandelenkaart

Laad je presentatie, voeg een aandelenkaart toe, wis de standaardgegevens, en voeg vervolgens je eigen series en categorieën toe. Het directe antwoord op de kernvraag is:

> Laad een bestaande PPTX met `new Presentation("template.pptx")`, voeg een `Chart` van het type `ChartType.Stock` toe, wis de standaardseries en -categorieën, en vul vervolgens met je eigen gegevenspunten en opmaakopties. Roep tenslotte `presentation.save("output.pptx", SaveFormat.Pptx)` aan.

### Presentatie initialiseren
#### Overzicht
Begin met het laden van een bestaand PowerPoint‑bestand zodat je het ter plekke kunt aanpassen.

#### Stapsgewijs
1. **Import the library** – de `Presentation`‑klasse is het toegangspunt voor alle slide‑bewerkingen.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – geef het pad naar je template‑PPTX op.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Voeg een aandelenkaart toe aan de slide
#### Overzicht
Voeg een Stock‑kaart toe aan de eerste slide van de presentatie.

De `Chart`‑klasse vertegenwoordigt een grafiekvorm die aan een slide kan worden toegevoegd.

#### Direct antwoord
Je voegt een aandelenkaart toe door `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` aan te roepen. Dit maakt een grafiekobject dat je direct kunt manipuleren.

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

### Verwijder bestaande gegevensseries en -categorieën in de grafiek
#### Overzicht
Verwijder eventuele vooraf ingevulde series of categorieën zodat je met een schone dataset kunt beginnen.

Het `ChartData`‑object bevat de series en categorieën voor een grafiek.

#### Direct antwoord
Roep `chart.getChartData().getSeries().clear()` en `chart.getChartData().getCategories().clear()` aan om de standaardinhoud te wissen voordat je je eigen toevoegt.

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

### Voeg categorieën toe aan grafiekgegevens
#### Overzicht
Definieer de X‑as‑categorieën (bijv. datums) die je aandelenwaarden groeperen.

Een `ChartCategory` vertegenwoordigt een X‑as‑label voor een grafiek.

#### Direct antwoord
Maak een nieuwe `ChartCategory` voor elk label met `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, en herhaal dit voor elke maand of periode.

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

### Voeg gegevensseries toe aan de grafiek
#### Overzicht
Voeg de vier essentiële series toe: Open, High, Low en Close.

Een `ChartSeries` bevat een verzameling gegevenspunten voor een specifieke serie in de grafiek.

#### Direct antwoord
Voor elke serie, roep `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` aan. Dit registreert de serie bij het gegevenswerkboek van de grafiek.

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

### Voeg gegevenspunten toe aan de serie
#### Overzicht
Vul elke serie met numerieke waarden die aandelenprijzen vertegenwoordigen.

Een `DataPoint` vertegenwoordigt een enkele waarde in een serie.

#### Direct antwoord
Loop door je gegevensverzameling en gebruik `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (of de juiste methode voor het serietype) om elk punt in te voegen.

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

### Formatteer high‑low lijnen en up/down bars
#### Overzicht
Pas de visuele stijl van de high‑low connectors en de up/down bar‑vullingen aan.

Een `Marker` definieert het visuele symbool voor een gegevenspunt.

#### Direct antwoord
Stel `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` in en configureer `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` om de lijndikte en kleur te regelen.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Toon up/down bars
Gebruik de `setShowUpDownBars(true)`‑methode van de grafiek om de up/down bars zichtbaar te maken.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Pas gegevenslabels aan op high‑low lijnen
#### Overzicht
Toon numerieke waarden direct op de high‑low lijnen voor snelle referentie.

Een `DataLabel` regelt het uiterlijk van labels die aan gegevenspunten zijn gekoppeld.

#### Direct antwoord
Schakel gegevenslabels in met `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` en style ze naar behoefte.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Stel de vulkleur van up/down bars in
#### Overzicht
Geef de up‑bars een groene vulling en de down‑bars een rode vulling om marktbeweging intuïtief weer te geven.

Het `UpDownBars`‑object biedt toegang tot de opmaak van de up‑ en down‑bars.

#### Direct antwoord
Pas `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` toe en stel de vaste kleur in op `Color.GREEN`; herhaal voor de down‑bar met `Color.RED`.

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

### Sla het PowerPoint‑bestand op
#### Overzicht
Sla je wijzigingen op in een nieuw PPTX‑bestand.

De `save`‑methode schrijft de presentatie naar schijf in het opgegeven formaat.

#### Direct antwoord
Roep `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` aan – dit schrijft de aangepaste presentatie naar schijf in het standaard PowerPoint‑formaat.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Veelvoorkomende problemen en foutopsporing

- **Grafiek verschijnt niet** – zorg ervoor dat de X/Y‑coördinaten en afmetingen van de grafiek binnen de slide‑grenzen liggen.  
- **Gegevenspunten ontbreken** – controleer of de cel‑indices van het gegevenswerkboek overeenkomen met de serie/rij die je wilt vullen.  
- **Licentie‑exception** – een tijdelijke proeflicentie verloopt na 30 dagen; vervang deze door een permanente licentie voor productie‑builds.  
- **Prestatie‑vertraging bij grote bestanden** – gebruik `Presentation.setCacheSize(0)` om caching uit te schakelen als je duizenden dia's in één batch verwerkt.

## Veelgestelde vragen

**Q: Kan ik deze code gebruiken in een webapplicatie?**  
A: Ja. De bibliotheek is pure Java, dus je kunt het uitvoeren in elke servlet‑container of Spring‑Boot‑service.

**Q: Ondersteunt Aspose.Slides andere grafiektype naast Stock?**  
A: Absoluut. Het ondersteunt meer dan 70 grafiektype, inclusief Line, Bar, Pie en Radar‑grafieken.

**Q: Hoe voeg ik programmatisch een grafiektitel toe?**  
A: Gebruik `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` en formatteer de titel vervolgens naar behoefte.

**Q: Is er een limiet aan het aantal gegevenspunten per serie?**  
A: Praktisch kun je tienduizenden punten toevoegen; het geheugenverbruik schaalt lineair, en de bibliotheek streamt data om de footprint laag te houden.

**Q: Welke Maven‑coördinaten moet ik gebruiken voor de nieuwste versie?**  
A: De nieuwste versie is altijd beschikbaar onder `com.aspose:aspose-slides:25.4` (of nieuwer) op Maven Central.

---

**Laatst bijgewerkt:** 2026-09-12  
**Getest met:** Aspose.Slides for Java 25.4  
**Auteur:** Aspose

## Gerelateerde tutorials

- [aspose slides maven afhankelijkheid: grafieken toevoegen en configureren in presentaties met Aspose.Slides voor Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint-grafiek maken Java – presentaties met grafieken opslaan met Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint-grafieken maken en opmaken Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}