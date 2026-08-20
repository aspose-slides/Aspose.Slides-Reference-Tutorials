---
date: '2026-08-16'
description: Leer hoe je donutgrafieken kunt toevoegen in Java met Aspose.Slides.
  Deze stapsgewijze handleiding behandelt het instellen van Maven‑afhankelijkheden,
  grafiekconfiguratie, kleuren, labels en het opslaan van de PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Hoe je donutgrafieken kunt toevoegen in Java met Aspose.Slides. Volg
  deze handleiding om Maven in te stellen, kleuren en labels aan te passen en PPTX‑bestanden
  te genereren.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Hoe een donutgrafiek toe te voegen in Java met Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Hoe een donutgrafiek toe te voegen in Java met Aspose.Slides
url: /nl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een donutgrafiek toe te voegen in Java met Aspose.Slides

## Introductie

Het programmatically maken van een **donutgrafiek** kan ruwe cijfers omzetten in een opvallende visual die meteen een verhaal vertelt. In Java maakt **Aspose.Slides** dit proces eenvoudig, waardoor je presentatiewaardige grafieken kunt genereren zonder PowerPoint te openen. In deze tutorial leer je **hoe je donutgrafieken** toevoegt aan een PPTX‑bestand stap voor stap — van het instellen van de Maven Aspose Slides‑dependency tot het aanpassen van series, categorieën, kleuren en labels, en uiteindelijk het opslaan van de presentatie.

Aan het einde van deze gids kun je dynamische donutgrafieken in elk PPTX‑bestand insluiten, perfect voor rapporten, dashboards of geautomatiseerde presentaties.

### Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Slides for Java  
- **Primaire taak?** Een donutgrafiek toevoegen in een PPTX‑bestand  
- **Hoe voeg je de bibliotheek toe?** Gebruik de Maven Aspose Slides‑dependency (of Gradle)  
- **Minimale Java‑versie?** JDK 16 of hoger  
- **Kan ik kleuren en labels aanpassen?** Ja, de API biedt volledige opmaakcontrole  

## Wat is een donutgrafiek en waarom gebruiken?

Een donutgrafiek is een variant van een taartgrafiek met een lege kern, waardoor meerdere gegevensreeksen als concentrische ringen kunnen worden weergegeven. **Het visualiseert delen‑van‑een‑geheel over verschillende categorieën terwijl er ruimte behouden blijft voor extra informatie in het midden.** Dit maakt het ideaal voor het vergelijken van verkoop per regio over meerdere kwartalen, budgettoewijzingen per afdeling, of elke situatie waarin je hiërarchische proportiedata moet tonen.

## Waarom Aspose.Slides voor Java gebruiken?

Je kunt een donutgrafiek toevoegen zonder Microsoft Office te installeren, en de bibliotheek verwerkt **meer dan 50 + invoer‑ en uitvoerformaten** terwijl hij presentaties aankan die meer dan 500 dia's bevatten. Aspose.Slides levert **tot 3× snellere rendering** vergeleken met native Office‑automatisering op dezelfde hardware, en werkt op Windows, Linux en macOS. Deze kwantificeerbare voordelen betekenen dat je grote presentaties kunt genereren op headless servers met voorspelbare prestaties.

## Vereisten

- **Vereiste bibliotheken**  
  - Aspose.Slides for Java 25.4 of later (de bibliotheek die je in staat stelt donutgrafieken toe te voegen).  

- **Omgeving**  
  - JDK 16 of hoger geïnstalleerd op je machine.  
  - Een IDE zoals IntelliJ IDEA, Eclipse of NetBeans.  

- **Kennis**  
  - Basis Java‑syntaxis en object‑georiënteerde concepten.  
  - Vertrouwdheid met Maven of Gradle voor dependency‑beheer.  

## Maven Aspose Slides‑dependency

Voeg de volgende Maven‑dependency toe aan je `pom.xml`. Dit is de **Maven Aspose Slides‑dependency** die je nodig hebt om de bibliotheek in je project te halen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Als je de voorkeur geeft aan Gradle, gebruik dan het equivalente fragment hieronder.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

U kunt de JAR ook rechtstreeks downloaden van de officiële release‑pagina:  
[ Aspose.Slides voor Java releases ](https://releases.aspose.com/slides/java/)

### Een licentie verkrijgen

Om het evaluatiewatermerk te verwijderen en de volledige functionaliteit te ontgrendelen:

- **Gratis proefversie** – begin met een tijdelijke licentie.  
- **Tijdelijke licentie** – vraag er een aan via de [Aspose‑website](https://purchase.aspose.com/temporary-license/).  
- **Commerciële licentie** – koop voor productiegebruik.

Pas de licentie toe in je code:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Implementatie‑gids

### Een presentatie initialiseren en een donutgrafiek toevoegen

Presentation is de Aspose.Slides‑klasse die een PowerPoint‑presentatie vertegenwoordigt.  
Laad een bestaande PPTX of maak een nieuw `Presentation`‑object aan, en voeg vervolgens een donutgrafiek toe aan de eerste dia.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Het configureren van de grafiek‑databoek en het wissen van bestaande gegevens

Het werkboek is een intern spreadsheet dat de gegevens van de grafiek opslaat.  
Verkrijg het werkboek dat de grafiek ondersteunt, en wis vervolgens eventuele standaardreeksen of -categorieën zodat je met een schone lei kunt beginnen.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Series toevoegen aan de grafiek

Een serie vertegenwoordigt een verzameling gegevenspunten die op de grafiek worden geplot.  
Je kunt tot 15 series toevoegen. Elke serie kan worden aangepast — hier stellen we de explosie, de grootte van het donut‑gat en de hoek van het eerste segment in.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Categorieën en gegevenspunten toevoegen

Categorieën zijn de labels voor elk gegevenspunt langs de as van de grafiek.  
Maak 15 categorieën aan en vul elke serie met een gegevenspunt. De laatste serie krijgt speciale labelopmaak.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Kleuren en gegevenslabels aanpassen

`FillType.Solid` specificeert een effen vulkleur voor grafiekelementen.  
Stel een effen vulkleur in voor elke serie en schakel gegevenslabels in. Voor de laatste serie wijzigen we ook de letterkleur van het label.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### De presentatie opslaan

`save` schrijft de presentatie naar een bestand in het gekozen formaat.  
Schrijf de bijgewerkte presentatie naar schijf in PPTX‑formaat, of exporteer naar PDF indien nodig.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Veelvoorkomende problemen en oplossingen

- **Licentie niet gevonden** – Controleer of het pad naar `license.lic` correct is en het bestand leesbaar is.  
- **Grafiek verschijnt leeg** – Zorg ervoor dat je bestaande series/categorieën hebt gewist voordat je nieuwe toevoegt.  
- **Onjuiste kleuren** – Controleer of `FillType.Solid` is ingesteld voor zowel vul‑ als lijnformaten.  
- **Prestaties bij veel series** – Beperk het aantal series/categorieën of hergebruik werkboekcellen om het geheugenverbruik onder controle te houden.  

## Veelgestelde vragen

**V: Kan ik een donutgrafiek genereren zonder een bestaande PPTX‑file?**  
A: Ja, maak een `new Presentation()` aan om vanuit een lege presentatiereeks te beginnen, en voeg vervolgens een grafiek toe zoals hierboven getoond.

**V: Ondersteunt Aspose.Slides exporteren naar PDF?**  
A: Zeker. Na het maken van de grafiek roep je `pres.save("output.pdf", SaveFormat.Pdf);` aan om een PDF‑versie van de dia te krijgen.

**V: Hoe wijzig ik de grootte van het donut‑gat?**  
A: Gebruik `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` waarbij `value` varieert van 0 tot 100.

**V: Is het mogelijk om gegevenslabels toe te voegen aan alle series, niet alleen de laatste?**  
A: Ja, verplaats het label‑opmaakblok buiten de `if (i == ...)`‑conditie en pas het toe op elk `dataPoint`.

**V: Welke Java‑versies worden ondersteund?**  
A: Aspose.Slides 25.4 ondersteunt JDK 16 en nieuwer. Oudere JDK’s vereisen de juiste classifier in de Maven‑dependency.

---

**Laatst bijgewerkt:** 2026-08-16  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Gerelateerde tutorials

- [Hoe een grafiek toe te voegen aan PowerPoint met Aspose.Slides voor Java: Een stapsgewijze handleiding](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoe taartgrafiekkleuren aanpassen in Java met Aspose.Slides – Een volledige gids](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [PowerPoint‑grafiekcategorieën animeren met Aspose.Slides voor Java | Stapsgewijze handleiding](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}