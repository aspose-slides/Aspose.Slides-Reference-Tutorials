---
date: '2026-02-17'
description: Leer hoe je een donutgrafiek in PowerPoint maakt met Aspose.Slides voor
  Java en grafiekdatapunten via code toevoegt. Volg eenvoudige stappen en codevoorbeelden.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Maak een donutgrafiek PowerPoint met Aspose.Slides voor Java
url: /nl/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak een doughnut‑grafiek PowerPoint met Aspose.Slides voor Java

## Introductie
Het maken van overtuigende presentaties vereist vaak meer dan alleen tekst en afbeeldingen; grafieken kunnen het verhaal aanzienlijk versterken door data effectief te visualiseren. Veel ontwikkelaars vinden het echter lastig om dynamische grafiekfuncties programmatisch in PowerPoint‑bestanden te integreren. Deze tutorial laat zien hoe je **een doughnut‑grafiek PowerPoint** maakt met Aspose.Slides voor Java – een krachtig hulpmiddel dat flexibiliteit en gebruiksgemak combineert.

**Wat je leert:**
- Hoe je een presentatie initialiseert met Aspose.Slides voor Java
- Een stap‑voor‑stap‑gids voor het toevoegen van een doughnut‑grafiek aan je dia's
- Het configureren van datapunten en het aanpassen van label‑eigenschappen
- Het opslaan van de gewijzigde presentatie met hoge nauwkeurigheid

Laten we ontdekken hoe je deze functies kunt benutten om je presentaties te verbeteren. Zorg ervoor dat je bekend bent met de basisprincipes van Java voordat we beginnen.

## Snelle antwoorden
- **Welke bibliotheek maakt doughnut‑grafiek PowerPoint?** Aspose.Slides voor Java  
- **Kan ik grafiek‑datapunten programmatisch toevoegen?** Ja, via de chart‑API  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Slides‑licentie is vereist  
- **Welke Java‑versies worden ondersteund?** Java 8 en later (JDK 16‑classifier weergegeven)  
- **Hoeveel series kan ik toevoegen?** Het voorbeeld voegt tot 15 series toe, maar je kunt dit aanpassen naar behoefte  

## Wat is een doughnut‑grafiek in PowerPoint?
Een doughnut‑grafiek is een variant van een cirkeldiagram met een holle kern, waardoor je meerdere dataseries compact en visueel aantrekkelijk kunt weergeven. Het is ideaal om deel‑van‑geheel‑relaties te tonen terwijl het ontwerp overzichtelijk blijft.

## Waarom Aspose.Slides voor Java gebruiken om doughnut‑grafieken te maken?
- **Volledige controle** over het uiterlijk, de data en de lay‑out van de grafiek zonder PowerPoint te openen  
- **Geen COM‑interop** – werkt op elk platform dat Java ondersteunt  
- **Hoge prestaties** voor het genereren van grote presentaties of integratie met webservices  
- **Rijke aanpassingsmogelijkheden** zoals explosie, gatgrootte, slice‑hoeken en label‑opmaak  

## Vereisten
- Basiskennis van Java‑programmeren.  
- Een IDE zoals IntelliJ IDEA of Eclipse.  
- Maven of Gradle voor afhankelijkheidsbeheer.  
- Een geldige Aspose.Slides voor Java‑licentie (gratis proefversie beschikbaar).  

## Aspose.Slides voor Java installeren
Kies de afhankelijkheidsbeheerder die bij je project past.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Als je liever direct downloadt, ga dan naar de pagina [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie
Je kunt beginnen met een gratis proefversie om de functies van Aspose.Slides te verkennen. Voor langdurig gebruik koop je een licentie of vraag je een tijdelijke licentie aan via de [website van Aspose](https://purchase.aspose.com/temporary-license/). Volg de meegeleverde instructies om je omgeving in te stellen en Aspose.Slides in je applicatie te initialiseren.

## Hoe maak je een doughnut‑grafiek PowerPoint met Aspose.Slides voor Java
Hieronder vind je een volledige stap‑voor‑stap‑gids. Elk code‑blok wordt direct voorafgegaan door een uitleg, zodat je precies weet wat er gebeurt.

### Stap 1: Initialiseert de presentatie
Laad een bestaande PPTX of maak een nieuwe aan. Dit bereidt de collectie dia's voor verdere aanpassingen voor.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Stap 2: Voeg een doughnut‑grafiek toe aan de dia
We voegen de grafiekvorm toe, wissen eventuele standaard series/categorieën en stellen basis‑visuele eigenschappen in.

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

### Stap 3: Voeg grafiek‑datapunten toe en pas labels aan
Hier vullen we de categorieën, voegen datapunten toe voor elke serie en verfijnen we de label‑weergave. Dit is waar de **add chart data points**‑keyword van pas komt.

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

### Stap 4: Sla de bijgewerkte presentatie op
Tot slot persisteren we de wijzigingen in een nieuw PPTX‑bestand.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Praktische toepassingen
Doughnut‑grafieken kunnen in diverse scenario's worden ingezet:
- **Financiële rapporten:** Visualiseer budgettoewijzingen of uitgavenverdelingen.  
- **Marktanalyse:** Toon marktaandeelverdeling onder concurrenten.  
- **Enquête‑resultaten:** Presenteer categorische enquête‑data compact.  
- **Dashboard‑generatie:** Combineer met database‑queries om live‑bijwerkende dia's te maken.  

## Prestatie‑overwegingen
- **Resources vrijgeven:** Roep `pres.dispose()` aan wanneer je klaar bent om native geheugen vrij te maken.  
- **Beperk het aantal grafieken:** Het toevoegen van honderden grafieken kan het geheugenverbruik verhogen; batch‑verwerk indien nodig.  
- **Gebruik streaming:** Voor enorme datasets kun je de workbook direct vanuit streams vullen in plaats van uit in‑memory arrays.  

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Grafiek verschijnt leeg** | Data‑cellen niet correct gevuld | Controleer of `workBook.getCell(...)` de juiste rij‑/kolom‑indices gebruikt. |
| **Labels overlappen** | Te veel categorieën in beperkte ruimte | Verhoog `DoughnutHoleSize` of pas `FirstSliceAngle` aan. |
| **OutOfMemoryError** | Grote presentaties zonder vrijgeven | Roep `pres.dispose()` aan na het opslaan en overweeg de JVM‑heap te vergroten. |

## Veelgestelde vragen

**V: Kan ik Aspose.Slides voor Java gebruiken in commerciële toepassingen?**  
A: Ja, maar je hebt een geldige commerciële licentie nodig. Een gratis proefversie is beschikbaar voor evaluatie.

**V: Hoe voeg ik meer dan 15 series toe?**  
A: Verhoog de luslimiet in de stap “Add Doughnut Chart” en zorg ervoor dat je workbook voldoende rijen bevat.

**V: Is het mogelijk de grootte van het doughnut‑gat later aan te passen?**  
A: Ja, roep `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` aan op elk moment vóór het opslaan.

**V: Kan ik de grafiek exporteren als afbeelding in plaats van een PPTX?**  
A: Absoluut. Gebruik `chart.getImage()` en sla de geretourneerde `java.awt.image.BufferedImage` op in het gewenste formaat.

**V: Ondersteunt Aspose.Slides geanimeerde grafieken?**  
A: Animaties kunnen worden toegevoegd via de `ISlide.getTimeline()`‑API, hoewel dit buiten de scope van deze tutorial valt.

## Conclusie
Je beschikt nu over een volledige, productie‑klare methode om **doughnut‑grafiek PowerPoint**‑bestanden te maken met Aspose.Slides voor Java, inclusief hoe je **grafiek‑datapunten** toevoegt, labels aanpast en prestatie‑aspecten beheert. Experimenteer met verschillende kleuren, databronnen en grafiektype­n om je presentaties echt te laten opvallen.

---

**Laatst bijgewerkt:** 2026-02-17  
**Getest met:** Aspose.Slides voor Java 25.4 (JDK 16‑classifier)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}