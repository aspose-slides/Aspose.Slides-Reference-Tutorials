---
date: '2026-06-08'
description: Leer hoe u reeksen aan een diagram kunt toevoegen en gestapelde kolomdiagrammen
  kunt aanpassen in .NET-presentaties met Aspose.Slides for Java.
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
title: Reeks toevoegen aan diagram met Aspose.Slides for Java in .NET
url: /nl/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meesterschap in Grafiekaanpassing in .NET‑presentaties met Aspose.Slides voor Java

## Inleiding
In het domein van data‑gedreven presentaties zijn grafieken onmisbare hulpmiddelen die ruwe cijfers omzetten in overtuigende visuele verhalen. Wanneer je programmatically **add series to chart** moet toevoegen, vooral binnen .NET‑presentatiebestanden, kan de taak overweldigend aanvoelen. Gelukkig biedt **Aspose.Slides for Java** een krachtige, taal‑agnostische API die het maken en aanpassen van grafieken eenvoudig maakt — zelfs wanneer je doelformaat een .NET PPTX is. Deze gids leidt je stap voor stap door het toevoegen van series, het bouwen van een gestapelde kolomgrafiek en het fijn afstellen van visuele aspecten zoals de gatbreedte, zodat je dynamische, data‑rijke dia's kunt genereren die er gepolijst en professioneel uitzien.

## Snelle Antwoorden
De `Presentation`‑klasse vertegenwoordigt een PPTX‑bestand, en `slide.getShapes().addChart(...)` voegt een grafiekvorm toe. Gebruik `chart.getChartData().getSeries().add(...)` om een serie toe te voegen, en `setGapWidth()` past de afstand aan.

- **Wat is de primaire klasse om een presentatie te starten?** `Presentation` – het vertegenwoordigt een PPTX‑bestand in het geheugen.  
- **Welke methode voegt een grafiek toe aan een dia?** `slide.getShapes().addChart(...)` maakt het grafiekobject op de dia.  
- **Hoe voeg je een nieuwe serie toe?** `chart.getChartData().getSeries().add(...)` voegt een nieuwe gegevensserie in.  
- **Kun je de gatbreedte tussen balken wijzigen?** Ja — roep `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` aan (waarde is een percentage).  
- **Heb ik een licentie nodig voor productie?** Absoluut — een geldige Aspose.Slides for Java‑licentie ontgrendelt alle functies en verwijdert evaluatiewatermerken.

## Wat betekent “add series to chart”?
Een serie aan een grafiek toevoegen betekent het invoegen van een nieuwe verzameling gegevenspunten die de grafiek weergeeft als een afzonderlijk visueel element (bijv. een aparte kolomgroep). Elke serie kan zijn eigen waarden, kleuren en opmaak hebben, waardoor een naast‑elkaar vergelijking van meerdere datasets mogelijk is.

## Waarom Aspose.Slides voor Java gebruiken om .NET‑presentaties te wijzigen?
Aspose.Slides for Java stelt je in staat PPTX‑bestanden te genereren of te bewerken die volledig compatibel zijn met .NET‑PowerPoint‑viewers, zonder dat er een Microsoft Office‑installatie nodig is. Gebruik Aspose.Slides for Java wanneer je een server‑side, cross‑platform oplossing nodig hebt die .NET PPTX‑bestanden maakt of bijwerkt, meer dan 50 grafiektype‑s ondersteunt en bestanden tot 500 MB verwerkt zonder het volledige document in het geheugen te laden. De API werkt in Java, Kotlin, Scala of elke JVM‑taal en levert dezelfde output die .NET‑ontwikkelaars verwachten.

## Vereisten
- **Aspose.Slides for Java** bibliotheek (versie 25.4 of hoger).  
- Maven, Gradle, of een handmatige JAR‑download.  
- Basiskennis van Java en vertrouwdheid met de PPTX‑bestandstructuur.  

## Aspose.Slides voor Java installeren
### Maven‑installatie
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑installatie
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
Alternatief kun je de nieuwste JAR downloaden van de officiële release‑pagina: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition**  
Begin met een gratis proefversie door een tijdelijke licentie te downloaden via [hier](https://purchase.aspose.com/temporary-license/). Voor productiegebruik koop je een volledige licentie om alle functies te ontgrendelen en evaluatiewatermerken te verwijderen.

## Stapsgewijze Implementatiegids
Onder elke stap vind je een beknopt code‑fragment (ongewijzigd ten opzichte van de originele tutorial) gevolgd door een uitleg van wat het doet.

### Stap 1: Maak een lege presentatie
`Presentation` is de instapklasse die een PowerPoint‑bestand in het geheugen vertegenwoordigt.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*We beginnen met een leeg PPTX‑bestand, wat ons een canvas geeft om grafieken toe te voegen.*

### Stap 2: Voeg een gestapelde kolomgrafiek toe aan de dia
`Chart` vertegenwoordigt een grafiekvorm binnen een dia. `ChartType.StackedColumn` geeft een gestapelde kolomgrafiek aan.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*De `addChart`‑methode maakt een **gestapelde kolomgrafiek** aan en plaatst deze in de linkerbovenhoek van de dia.*

### Stap 3: Voeg series toe aan de grafiek (Hoofddoel)
`Series` omvat een enkele gegevensreeks in een grafiek.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Hier **voegen we series toe aan de grafiek** – elke aanroep maakt een nieuwe gegevensreeks die verschijnt als een aparte kolomgroep.*

### Stap 4: Voeg categorieën toe aan de grafiek
`Category` definieert een X‑as‑label voor grafiekgegevens.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Categorieën fungeren als X‑as‑labels en geven betekenis aan elke kolom.*

### Stap 5: Vul seriesgegevens in
`DataPoint` bevat een numerieke waarde voor een serie bij een specifieke categorie.  
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
*Gegevenspunten geven elke serie zijn numerieke waarden, die de grafiek weergeeft als balkhoogtes.*

### Stap 6: Stel de gatbreedte in voor de serie‑groep van de grafiek
`SeriesGroup` regelt lay‑out‑eigenschappen voor een groep series, zoals de gatbreedte.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Het aanpassen van de gatbreedte verbetert de leesbaarheid, vooral wanneer er veel categorieën aanwezig zijn.*

## Veelvoorkomende Toepassingsgevallen
- **Financiële rapportage** – vergelijk kwartaalomzet over bedrijfsunits.  
- **Projectdashboards** – toon taakvoltooiingspercentages per team.  
- **Marketinganalyse** – visualiseer campagneprestaties naast elkaar.  
Deze scenario's profiteren van het **voorbeeld van een gestapelde kolomgrafiek** omdat ze de bijdragen van individuele categorieën aan een totaal benadrukken.

## Prestatietips
- **Herbruik het `Presentation`‑object** bij het maken van meerdere grafieken om het geheugenverbruik te verminderen.  
- **Beperk het aantal gegevenspunten** tot alleen die nodig zijn voor het visuele verhaal; Aspose.Slides kan 10.000 punten aan, maar de weergavesnelheid daalt na ~5.000.  
- **Maak objecten vrij** (`presentation.dispose()`) na het opslaan om bronnen vrij te geven en geheugenlekken te voorkomen.  

## Veelgestelde Vragen
**Q: Kan ik andere grafiektype‑s toevoegen naast gestapelde kolom?**  
A: Ja, Aspose.Slides ondersteunt lijn-, taart-, gebied-, radar-, bubbel‑ en meer dan 50 andere grafiektype‑s, allemaal toegankelijk via dezelfde `addChart`‑methode.

**Q: Heb ik een aparte licentie nodig voor .NET‑output?**  
A: Nee, dezelfde Java‑licentie werkt voor alle outputformaten, inclusief .NET PPTX‑bestanden.

**Q: Hoe wijzig ik het kleurenpalet van de grafiek?**  
A: Gebruik `series.getFormat().getFill().setFillType(FillType.Solid)` en stel vervolgens het gewenste `Color`‑object in voor elke serie.

**Q: Is het mogelijk om gegevenslabels programmatisch toe te voegen?**  
A: Absoluut. Roep `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` aan om de numerieke waarde op elke kolom weer te geven.

**Q: Wat als ik een bestaande presentatie moet bijwerken?**  
A: Laad het bestand met `new Presentation("existing.pptx")`, wijzig de grafiek met dezelfde API‑aanroepen en sla het terug op naar schijf.

## Conclusie
Je hebt nu een volledige, end‑to‑end gids over hoe je **series aan een grafiek toevoegt**, een **gestapelde kolomgrafiek** maakt en het uiterlijk ervan verfijnt in .NET‑presentaties met Aspose.Slides voor Java. Experimenteer met verschillende grafiektype‑s, kleuren en gegevensbronnen om overtuigende visuele rapporten te bouwen die belanghebbenden imponeren en data‑gedreven beslissingen stimuleren.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde Tutorials

- [Hoe Percentage‑Gebaseerde Gestapelde Kolomgrafieken te Maken in .NET met Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Meesterlijke Creatie en Manipulatie van Grafiekseries met Aspose.Slides .NET voor Effectieve Datavisualisatie](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Specifieke Gegevenspunten van Grafiekseries Wissen met Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}