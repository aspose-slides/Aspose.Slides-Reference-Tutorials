---
date: '2026-03-07'
description: Leer hoe je een donutgrafiek in Java maakt met Aspose.Slides. Deze stapsgewijze
  gids behandelt het instellen van de Maven Aspose Slides‑afhankelijkheid, grafiekconfiguratie
  en het opslaan van presentaties.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Maak een donutgrafiek in Java met de Aspose.Slides-gids
url: /nl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak doughnut chart Java met Aspose.Slides-gids

## Inleiding

Het programmatically maken van een **doughnut chart** kan ruwe cijfers omzetten in een opvallende visual die meteen een verhaal vertelt. In Java maakt **Aspose.Slides** dit proces eenvoudig, zodat je presentatieklaar diagrammen kunt genereren zonder PowerPoint te openen. In deze tutorial leer je hoe je **create doughnut chart java** stap voor stap kunt doen — van het instellen van de Maven Aspose Slides‑dependency tot het aanpassen van series, categorieën en uiteindelijk het opslaan van de presentatie.

Aan het einde van deze gids kun je dynamische doughnut charts in elk PPTX‑bestand insluiten, perfect voor rapporten, dashboards of geautomatiseerde presentaties.

### Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.Slides for Java  
- **Primaire taak?** Create doughnut chart java in a PPTX file  
- **Hoe voeg je de bibliotheek toe?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimale Java‑versie?** JDK 16 or higher  
- **Kan ik kleuren en labels aanpassen?** Yes, the API provides full formatting control  

## Wat is een doughnut chart en waarom gebruiken?

Een doughnut chart is een variant van een taartdiagram met een leeg midden, waardoor je meerdere gegevensreeksen in concentrische ringen kunt weergeven. Dit maakt het ideaal voor het vergelijken van delen van een geheel over verschillende categorieën — denk aan verkoop per regio over meerdere kwartalen of budgettoewijzingen per afdeling.

## Waarom Aspose.Slides voor Java gebruiken?

- **No Office installation required** – genereer PPTX‑bestanden op elke server.  
- **Rich API** – volledige controle over diagramtypen, gegevenspunten en styling.  
- **High performance** – geoptimaliseerd voor grote presentaties.  
- **Cross‑platform** – werkt op Windows, Linux en macOS.

## Vereisten

- **Vereiste bibliotheken:**  
  - Aspose.Slides for Java version 25.4 of later.  

- **Omgevingsconfiguratie:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Vereiste kennis:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Maven Aspose Slides Dependency

Voeg de volgende Maven‑dependency toe aan je `pom.xml`. Dit is de **maven aspose slides dependency** die je nodig hebt om de bibliotheek in je project te halen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Als je Gradle verkiest, gebruik dan het equivalente fragment hieronder.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Je kunt de JAR ook direct downloaden van de officiële release‑pagina:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Een licentie verkrijgen

Om de evaluatiewatermerk te verwijderen en de volledige functionaliteit te ontgrendelen:

- **Free trial** – Gratis proefversie – start met een tijdelijke licentie.  
- **Temporary license** – Tijdelijke licentie – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – Commerciële licentie – purchase for production use.

Pas de licentie toe in je code:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementatie‑gids

### Presentatie initialiseren en een doughnut chart toevoegen

Eerst maak of laad je een presentatie en voeg je een doughnut chart toe aan de eerste dia.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Het chart‑data‑werkboek configureren en bestaande gegevens wissen

Vervolgens haal je het werkboek op dat de chart ondersteunt en wis je eventuele standaardreeksen of -categorieën.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Series aan de chart toevoegen

Nu voegen we tot 15 series toe. Elke series kan worden aangepast — hier stellen we de explosie, de doughnut‑hole‑grootte en de eerste‑slice‑hoek in.

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

### Categorieën en gegevenspunten toevoegen

We maken 15 categorieën aan en vullen elke series met een gegevenspunt. De laatste series krijgt een speciale labelopmaak.

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

### De presentatie opslaan

Tot slot schrijf je de bijgewerkte presentatie naar schijf.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Veelvoorkomende problemen en oplossingen

- **License not found** – Licentie niet gevonden – Verify the path to `license.lic` is correct and the file is readable.  
- **Chart appears blank** – Chart verschijnt leeg – Ensure you cleared existing series/categories before adding new ones.  
- **Incorrect colors** – Onjuiste kleuren – Check that `FillType.Solid` is set for both fill and line formats.  
- **Performance with many series** – Prestaties bij veel series – Limit the number of series/categories or reuse the workbook cells.

## Veelgestelde vragen

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Ja, instantiate `new Presentation()` om te beginnen met een lege slide deck.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absoluut. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: How do I change the doughnut hole size?**  
A: Gebruik `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` waarbij value 0‑100 is.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Ja, verplaats het label‑formatting‑blok buiten de `if (i == ...)`‑conditie en pas het toe op elk `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 ondersteunt JDK 16 en nieuwer. Oudere JDK's vereisen de juiste classifier.

---

**Laatst bijgewerkt:** 2026-03-07  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}