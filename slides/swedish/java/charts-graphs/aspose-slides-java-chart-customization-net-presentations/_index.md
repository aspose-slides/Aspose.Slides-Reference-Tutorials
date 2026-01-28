---
date: '2026-01-17'
description: Lär dig hur du lägger till serier i diagram och anpassar staplade kolumndiagram
  i .NET-presentationer med Aspose.Slides för Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Lägg till serier i diagram med Aspose.Slides för Java i .NET
url: /sv/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mästra diagramanpassning i .NET-presentationer med Aspose.Slides för Java

## Introduktion
Inom området data‑drivna presentationer är diagram oumbärliga verktyg som förvandlar råa siffror till övertygande visuella berättelser. När du behöver **add series to chart** programatiskt, särskilt i .NET‑presentationsfiler, kan uppgiften kännas överväldigande. Lyckligtvis erbjuder **Aspose.Slides for Java** ett kraftfullt, språk‑oberoende API som gör diagramskapande och anpassning enkel – även när ditt målformat är en .NET PPTX.

I den här handledningen kommer du att upptäcka hur du **add series to chart**, hur du **how to add chart** av typen staplad kolumn, och hur du finjusterar visuella aspekter såsom gap width. I slutet kommer du kunna generera dynamiska, datarika bilder som ser polerade och professionella ut.

**Vad du kommer att lära dig**
- Hur du skapar en tom presentation med Aspose.Slides  
- Hur du **add stacked column chart** till en bild  
- Hur du **add series to chart** och definierar kategorier  
- Hur du fyller i datapunkter och justerar visuella inställningar  

Låt oss förbereda din utvecklingsmiljö.

## Snabba svar
- **Vad är den primära klassen för att starta en presentation?** `Presentation`  
- **Vilken metod lägger till ett diagram på en bild?** `slide.getShapes().addChart(...)`  
- **Hur lägger du till en ny serie?** `chart.getChartData().getSeries().add(...)`  
- **Kan du ändra gap width mellan staplar?** Ja, genom att använda `setGapWidth()` på seriegruppen  
- **Behöver jag en licens för produktion?** Ja, en giltig Aspose.Slides for Java-licens krävs  

## Vad betyder “add series to chart”?
Att lägga till en serie i ett diagram innebär att infoga en ny datainsamling som diagrammet renderar som ett separat visuellt element (t.ex. en ny stapel, linje eller del). Varje serie kan ha sin egen uppsättning värden, färger och formatering, vilket gör att du kan jämföra flera dataset sida vid sida.

## Varför använda Aspose.Slides for Java för att modifiera .NET-presentationer?
- **Cross‑platform**: Skriv Java‑kod en gång och rikta in dig på PPTX‑filer som används av .NET‑applikationer.  
- **No COM or Office dependencies**: Fungerar på servrar, CI‑pipelines och containrar.  
- **Rich chart API**: Stöder över 50 diagramtyper, inklusive staplade kolumndiagram.  

## Förutsättningar
1. **Aspose.Slides for Java**-bibliotek (version 25.4 eller senare).  
2. Maven‑ eller Gradle‑byggverktyg, eller en manuell JAR‑nedladdning.  
3. Grundläggande Java‑kunskaper och bekantskap med PPTX‑struktur.  

## Installera Aspose.Slides för Java
### Maven‑installation
Add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑installation
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternatively, grab the latest JAR from the official release page: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Licensanskaffning**  
Start with a free trial by downloading a temporary license from [here](https://purchase.aspose.com/temporary-license/). For production use, purchase a full license to unlock all features.

## Steg‑för‑steg‑implementeringsguide
Below each step you’ll find a concise code snippet (unchanged from the original tutorial) followed by an explanation of what it does.

### Steg 1: Skapa en tom presentation
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Vi börjar med en ren PPTX‑fil, som ger oss en duk för att lägga till diagram.*

### Steg 2: Lägg till ett staplat kolumndiagram på bilden
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Metoden `addChart` skapar ett **add stacked column chart** och placerar det i bildens övre vänstra hörn.*

### Steg 3: Lägg till serier i diagrammet (primärt mål)
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
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Kategorier fungerar som X‑axelns etiketter och ger varje kolumn mening.*

### Steg 5: Fyll i seriedata
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
*Datapunkter ger varje serie sina numeriska värden, som diagrammet renderar som stapelhöjder.*

### Steg 6: Ställ in gap width för diagramseriegruppen
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Justering av gap width förbättrar läsbarheten, särskilt när många kategorier finns.*

## Vanliga användningsområden
- **Finansiell rapportering** – jämför kvartalsintäkter över affärsenheter.  
- **Projekt‑dashboards** – visa procentuell slutförande av uppgifter per team.  
- **Marknadsföringsanalys** – visualisera kampanjprestanda sida vid sida.  

## Prestandatips
- **Återanvänd `Presentation`‑objektet** när du skapar flera diagram för att minska minnesbelastning.  
- **Begränsa antalet datapunkter** till endast de som behövs för den visuella berättelsen.  
- **Avsluta objekt** (`presentation.dispose()`) efter sparning för att frigöra resurser.  

## Vanliga frågor
**Q: Kan jag lägga till andra diagramtyper än staplad kolumn?**  
A: Ja, Aspose.Slides stöder linje, paj, area och många fler diagramtyper.

**Q: Behöver jag en separat licens för .NET‑utdata?**  
A: Nej, samma Java‑licens fungerar för alla utdataformat, inklusive .NET PPTX‑filer.

**Q: Hur ändrar jag diagrammets färgpalett?**  
A: Använd `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` och sätt önskad `Color`.

**Q: Är det möjligt att lägga till datalabeler programatiskt?**  
A: Absolut. Anropa `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` för att visa värden.

**Q: Vad händer om jag behöver uppdatera en befintlig presentation?**  
A: Läs in filen med `new Presentation("existing.pptx")`, modifiera diagrammet och spara tillbaka.

## Slutsats
Du har nu en komplett, end‑to‑end‑guide om hur du **add series to chart**, skapar ett **stacked column chart**, och finjusterar dess utseende i .NET‑presentationer med Aspose.Slides för Java. Experimentera med olika diagramtyper, färger och datakällor för att bygga övertygande visuella rapporter som imponerar på intressenter.

---

**Senast uppdaterad:** 2026-01-17  
**Testat med:** Aspose.Slides for Java 25.4 (jdk16)  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
