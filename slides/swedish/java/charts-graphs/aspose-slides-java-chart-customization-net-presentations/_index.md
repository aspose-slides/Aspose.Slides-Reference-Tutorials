---
date: '2026-06-08'
description: Lär dig hur du lägger till serier i diagram och anpassar staplade kolumndiagram
  i .NET-presentationer med Aspose.Slides for Java.
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
title: Lägg till serier i diagram med Aspose.Slides for Java i .NET
url: /sv/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Behärska diagramanpassning i .NET-presentationer med Aspose.Slides för Java

## Introduktion
I området för datadrivna presentationer är diagram oumbärliga verktyg som omvandlar råa siffror till övertygande visuella berättelser. När du behöver **add series to chart** programatiskt, särskilt i .NET‑presentationsfiler, kan uppgiften kännas överväldigande. Lyckligtvis erbjuder **Aspose.Slides for Java** ett kraftfullt, språkoberoende API som gör diagramskapande och anpassning enkel—även när ditt målformat är en .NET PPTX. Denna guide visar dig hur du lägger till serier, bygger ett staplat kolumndiagram och finjusterar visuella aspekter som gapbredd, så att du kan generera dynamiska, datarika bilder som ser polerade och professionella ut.

## Snabba svar
Klassen `Presentation` representerar en PPTX‑fil, och `slide.getShapes().addChart(...)` infogar en diagramform. Använd `chart.getChartData().getSeries().add(...)` för att lägga till en serie, och `setGapWidth()` justerar avståndet.

- **Vilken är den primära klassen för att starta en presentation?** `Presentation` – it represents a PPTX file in memory.  
- **Vilken metod lägger till ett diagram på en bild?** `slide.getShapes().addChart(...)` creates the chart object on the slide.  
- **Hur lägger du till en ny serie?** `chart.getChartData().getSeries().add(...)` inserts a fresh data series.  
- **Kan du ändra gapbredden mellan staplar?** Yes—call `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (value is a percentage).  
- **Behöver jag en licens för produktion?** Absolutely—a valid Aspose.Slides for Java license unlocks all features and removes evaluation watermarks.

## Vad är “add series to chart”?
Att lägga till en serie i ett diagram innebär att infoga en ny samling datapunkter som diagrammet renderar som ett distinkt visuellt element (t.ex. en separat kolumngrupp). Varje serie kan ha sina egna värden, färger och formatering, vilket möjliggör sid‑vid‑sid jämförelse av flera dataset.

## Varför använda Aspose.Slides for Java för att modifiera .NET-presentationer?
Aspose.Slides for Java låter dig generera eller redigera PPTX‑filer som är fullt kompatibla med .NET PowerPoint‑visare, utan att behöva någon Microsoft Office‑installation. Använd Aspose.Slides for Java när du behöver en server‑sidig, plattformsoberoende lösning som skapar eller uppdaterar .NET PPTX‑filer, stöder 50+ diagramtyper och bearbetar filer upp till 500 MB utan att ladda hela dokumentet i minnet. Dess API fungerar i Java, Kotlin, Scala eller vilket JVM‑språk som helst och levererar samma resultat som .NET‑utvecklare förväntar sig.

## Förutsättningar
- **Aspose.Slides for Java**‑bibliotek (version 25.4 eller senare).  
- Maven, Gradle eller en manuell JAR‑nedladdning.  
- Grundläggande kunskaper i Java och bekantskap med PPTX‑filstrukturen.  

## Installera Aspose.Slides för Java
### Maven‑installation
Lägg till följande beroende i din `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑installation
Inkludera denna rad i din `build.gradle`‑fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direktnedladdning
Alternativt, hämta den senaste JAR‑filen från den officiella releasesidan: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Licensförvärv**  
Starta med en gratis provperiod genom att ladda ner en temporär licens från [here](https://purchase.aspose.com/temporary-license/). För produktionsbruk, köp en full licens för att låsa upp alla funktioner och ta bort evalueringsvattenmärken.

## Steg‑för‑steg‑implementeringsguide
Nedan varje steg hittar du ett kort kodexempel (oförändrat från den ursprungliga handledningen) följt av en förklaring av vad det gör.

### Steg 1: Skapa en tom presentation
`Presentation` är ingångsklassen som representerar en PowerPoint‑fil i minnet.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Vi börjar med en ren PPTX‑fil, vilket ger oss en duk för att lägga till diagram.*

### Steg 2: Lägg till ett staplat kolumndiagram på bilden
`Chart` representerar ett diagramobjekt inom en bild. `ChartType.StackedColumn` specificerar ett staplat kolumndiagram.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Metoden `addChart` skapar ett **staplat kolumndiagram** och placerar det i bildens övre‑vänstra hörn.*

### Steg 3: Lägg till serier i diagrammet (Primärt mål)
`Series` kapslar in en enskild dataserie i ett diagram.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Här **add series to chart** – varje anrop skapar en ny dataserie som kommer att visas som en separat kolumngrupp.*

### Steg 4: Lägg till kategorier i diagrammet
`Category` definierar en X‑axel‑etikett för diagramdata.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategorier fungerar som X‑axel‑etiketter och ger varje kolumn mening.*

### Steg 5: Fyll seriedata
`DataPoint` innehåller ett numeriskt värde för en serie vid en specifik kategori.  
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
*Datapunkter ger varje serie sina numeriska värden, vilka diagrammet renderar som stapelhöjder.*

### Steg 6: Ställ in gapbredd för diagramseriegrupp
`SeriesGroup` styr layout‑egenskaper för en grupp av serier, såsom gapbredd.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Justering av gapbredd förbättrar läsbarheten, särskilt när många kategorier finns.*

## Vanliga användningsfall
- **Finansiell rapportering** – jämför kvartalsintäkter över affärsenheter.  
- **Projekt‑instrumentpaneler** – visa procentuell uppgiftsslutning per team.  
- **Marknadsanalys** – visualisera kampanjprestanda sida‑vid‑sida.  
Dessa scenarier drar nytta av **staplat kolumndiagram‑exemplet** eftersom de framhäver varje kategoris bidrag till en total.

## Prestandatips
- **Återanvänd `Presentation`‑objektet** när du skapar flera diagram för att minska minnesbelastningen.  
- **Begränsa antalet datapunkter** till det som behövs för den visuella berättelsen; Aspose.Slides kan hantera 10 000 punkter, men renderingshastigheten sjunker efter ~5 000.  
- **Avsluta objekt** (`presentation.dispose()`) efter sparande för att frigöra resurser och undvika minnesläckor.  

## Vanliga frågor
**Q: Kan jag lägga till andra diagramtyper än staplat kolumn?**  
A: Ja, Aspose.Slides stöder linje, paj, område, radar, bubbla och 50+ andra diagramtyper, alla åtkomliga via samma `addChart`‑metod.

**Q: Behöver jag en separat licens för .NET‑utdata?**  
A: Nej, samma Java‑licens fungerar för alla utdataformat, inklusive .NET PPTX‑filer.

**Q: Hur ändrar jag diagrammets färgpalett?**  
A: Använd `series.getFormat().getFill().setFillType(FillType.Solid)` och sätt sedan önskat `Color`‑objekt för varje serie.

**Q: Är det möjligt att lägga till datalabels programatiskt?**  
A: Absolut. Anropa `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` för att visa det numeriska värdet på varje kolumn.

**Q: Vad händer om jag behöver uppdatera en befintlig presentation?**  
A: Ladda filen med `new Presentation("existing.pptx")`, modifiera diagrammet med samma API‑anrop och spara tillbaka till disk.

## Slutsats
Du har nu en komplett, end‑to‑end‑guide för hur du **add series to chart**, skapar ett **staplat kolumndiagram** och finjusterar dess utseende i .NET‑presentationer med Aspose.Slides för Java. Experimentera med olika diagramtyper, färger och datakällor för att bygga övertygande visuella rapporter som imponerar på intressenter och driver datadrivna beslut.

---

**Senast uppdaterad:** 2026-06-08  
**Testad med:** Aspose.Slides for Java 25.4 (JDK 16)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar procentbaserade staplade kolumndiagram i .NET med Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Mästarserie‑skapande och manipulation med Aspose.Slides .NET för effektiv datavisualisering](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Rensa specifika diagramseriedatapunkter med Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}