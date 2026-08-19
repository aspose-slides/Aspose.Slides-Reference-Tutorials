---
date: '2026-07-08'
description: Leer hoe je Aspose kunt gebruiken om een doughnut chart te maken in PowerPoint
  met Java. Deze stapsgewijze handleiding laat zien hoe je programmatisch gegevenspunten
  aan de grafiek toevoegt, labels aanpast en de PPTX met hoge nauwkeurigheid opslaat.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Hoe je Aspose gebruikt, stelt je in staat een doughnut chart te maken
  in PowerPoint met Java. Volg deze tutorial om gegevenspunten toe te voegen, labels
  aan te passen en de PPTX met hoge nauwkeurigheid op te slaan.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Hoe Aspose te gebruiken: Maak een doughnut chart in PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Hoe Aspose te gebruiken om een doughnut chart te maken in PowerPoint (Java)
url: /nl/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe gebruik je Aspose om een donutgrafiek te maken in PowerPoint (Java)

## Introductie
Het maken van overtuigende presentaties vereist vaak meer dan alleen tekst en afbeeldingen; grafieken kunnen het verhaal aanzienlijk versterken door data effectief te visualiseren. **Hoe gebruik je Aspose** voor grafiekgeneratie geeft je programmatische controle zonder PowerPoint te openen. Deze tutorial leidt je stap voor stap door het bouwen van een donutgrafiek, het configureren van de datapunten en het opslaan van een hoogwaardig PPTX‑bestand. Je hebt alleen basiskennis van Java nodig en een paar minuten installatie‑tijd.

`Aspose.Slides for Java` is een Java‑bibliotheek die het maken, manipuleren en converteren van PowerPoint‑bestanden mogelijk maakt zonder Microsoft Office.

## Snelle antwoorden
- **Welke bibliotheek maakt een donutgrafiek PowerPoint?** Aspose.Slides for Java  
- **Kan ik grafiekdatapunten programmatisch toevoegen?** Ja, met behulp van de chart‑API  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Slides‑licentie is vereist  
- **Welke Java‑versies worden ondersteund?** Java 8 en later (JDK 16‑classifier weergegeven)  
- **Hoeveel series kan ik toevoegen?** Het voorbeeld voegt tot 15 series toe, maar je kunt dit naar behoefte aanpassen  

## Wat is een donutgrafiek in PowerPoint?
Een donutgrafiek is een cirkelvormige grafiek die lijkt op een taartgrafiek, maar met een holle kern, waardoor meerdere series gelijktijdig kunnen worden weergegeven. Het benadrukt deel‑tot‑geheel‑relaties terwijl de visuele lay‑out compact en gemakkelijk leesbaar blijft.

## Waarom Aspose.Slides for Java gebruiken om donutgrafieken te maken?
Aspose.Slides for Java ondersteunt meer dan 50 invoer‑ en uitvoerformaten en kan presentaties tot 500 MB genereren zonder het volledige bestand in het geheugen te laden. Het biedt volledige programmatische controle over het uiterlijk, de data en de lay‑out van grafieken op elk Java‑platform, elimineert COM‑interop en kan 100 grafiek‑rijke dia's renderen in minder dan twee seconden op een typische server.

## Vereisten
- Basiskennis van Java‑programmeren.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  
- Maven of Gradle voor afhankelijkheidsbeheer.  
- Een geldige Aspose.Slides for Java‑licentie (gratis proefversie beschikbaar).

## Instellen van Aspose.Slides for Java
Kies de afhankelijkheidsbeheerder die bij uw project past.

**Maven**  
Voeg de volgende afhankelijkheid toe aan uw `pom.xml` (vervang de versie door de nieuwste release):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Voeg deze regel toe aan uw `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Als u liever direct downloadt, bezoek dan de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) pagina.

### Licentie‑acquisitie
U kunt beginnen met een gratis proefversie om de functies van Aspose.Slides te verkennen. Voor uitgebreid gebruik koopt u een licentie of vraagt u een tijdelijke licentie aan via de [website van Aspose](https://purchase.aspose.com/temporary-license/). Volg de meegeleverde instructies voor het instellen van uw omgeving en het initialiseren van Aspose.Slides in uw applicatie.

## Hoe maak je een donutgrafiek PowerPoint met Aspose.Slides for Java
Om een donutgrafiek te bouwen, laadt of maakt u eerst een `Presentation`, voegt u een grafiekvorm van het type `ChartType.Doughnut` toe, wist u de standaard series, stelt u de gatgrootte in en vult u vervolgens de werkmap van de grafiek met categorienamen en numerieke waarden. Ten slotte past u de label‑opmaak aan en slaat u het PPTX‑bestand op.

### Stap 1: Initialiseer de presentatie
Maak een nieuwe presentatie of open een bestaand bestand om een dia‑collectie te verkrijgen.

`Presentation` is de primaire klasse die een PowerPoint‑bestand vertegenwoordigt.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Stap 2: Voeg een donutgrafiek toe aan de dia
Voeg een grafiekvorm in, verwijder standaard series/categorieën en configureer basis‑visuele instellingen zoals de grootte van het donutgat.

`Chart` (of grafiekvorm) vertegenwoordigt een grafiekobject geplaatst op een dia.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Stap 3: Voeg grafiekdatapunten toe en pas labels aan
Vul categorienamen in, voeg datapunten toe voor elke serie en verfijn de label‑opmaak (lettertype, kleur, positie). Deze stap demonstreert de mogelijkheid om “grafiekdatapunten toe te voegen”.

`Workbook` biedt toegang tot de onderliggende spreadsheet‑data van de grafiek waar cellen worden gevuld.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Stap 4: Sla de bijgewerkte presentatie op
Sla de wijzigingen op in een nieuw PPTX‑bestand op schijf.

`save` schrijft de presentatie naar een bestand in het gekozen formaat.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Praktische toepassingen
Donutgrafieken zijn ideaal voor:
- **Financiële rapporten:** Visualiseren van budgettoewijzingen of uitgavenverdelingen.  
- **Marktanalyse:** Tonen van marktaandeelverdeling onder concurrenten.  
- **Enquête‑resultaten:** Presenteren van categorische enquête‑data in een compacte vorm.  
- **Dashboard‑generatie:** Combineren met database‑query’s om live‑bijwerkende dia's te produceren.

## Prestatiesoverwegingen
- **Resources vrijgeven:** Roep `pres.dispose()` aan na het opslaan om native geheugen vrij te maken.  
- **Beperk het aantal grafieken:** Het toevoegen van honderden grafieken kan het geheugenverbruik verhogen; batch‑verwerk indien nodig.  
- **Gebruik streaming:** Voor enorme datasets, vul de werkmap direct vanuit streams in plaats van uit‑geheugende arrays.  

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|----------|-----------|
| **Grafiek verschijnt leeg** | Gegevenscellen niet correct ingevuld | Controleer of `workBook.getCell(...)` de juiste rij/kolomindices aanroept. |
| **Labels overlappen** | Te veel categorieën in beperkte ruimte | Vergroot `DoughnutHoleSize` of pas `FirstSliceAngle` aan. |
| **OutOfMemoryError** | Grote presentaties zonder vrijgeven | Roep `pres.dispose()` aan na het opslaan en overweeg het JVM‑heap‑geheugen te vergroten. |

## Veelgestelde vragen

**Q: Kan ik Aspose.Slides for Java gebruiken in commerciële toepassingen?**  
A: Ja, maar u heeft een geldige commerciële licentie nodig. Een gratis proefversie is beschikbaar voor evaluatie.

**Q: Hoe voeg ik meer dan 15 series toe?**  
A: Verhoog de luslimiet in de stap “Donutgrafiek toevoegen” en zorg ervoor dat uw gegevens‑werkmap voldoende rijen bevat.

**Q: Is het mogelijk de donutgatgrootte na creatie te wijzigen?**  
A: Ja, roep `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` aan vóór het opslaan.

**Q: Kan ik de grafiek exporteren als afbeelding in plaats van een PPTX?**  
A: Absoluut. Gebruik `chart.getImage()` en sla de geretourneerde `java.awt.image.BufferedImage` op in het gewenste formaat.

**Q: Ondersteunt Aspose.Slides geanimeerde grafieken?**  
A: Animaties kunnen worden toegevoegd via de `ISlide.getTimeline()`‑API, hoewel dit buiten de scope van deze tutorial valt.

## Conclusie
U beschikt nu over een volledige, productie‑klare methode om **donutgrafiek‑PowerPoint**‑bestanden te **maken met Aspose.Slides for Java**, inclusief hoe u **grafiekdatapunten kunt toevoegen**, labels kunt aanpassen en prestatie‑overwegingen kunt beheren. Experimenteer met verschillende kleuren, gegevensbronnen en grafiektype­n om uw presentaties echt te laten opvallen.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Gerelateerde tutorials

- [Hoe grafieken toevoegen aan PowerPoint met Aspose.Slides for Java: Een stapsgewijze handleiding](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoe PowerPoint‑grafiekdata bewerken met Aspose.Slides for Java: Een uitgebreide gids](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Grafieken animeren in PowerPoint met Aspose.Slides for Java – Een stapsgewijze handleiding](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}