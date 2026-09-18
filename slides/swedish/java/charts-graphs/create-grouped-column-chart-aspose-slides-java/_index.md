---
date: '2026-09-17'
description: Lär dig hur du lägger till ett clustered column chart i en PowerPoint-presentation,
  anpassar PowerPoint-diagram och infogar ett data series-diagram med Aspose.Slides
  för Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Lär dig hur du lägger till ett clustered column chart i en PowerPoint-presentation
  med Aspose.Slides för Java, inklusive steg för att infoga data series, anpassa gruppering
  och spara filen som PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Lägg till ett clustered column chart i PowerPoint med Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Hur du lägger till ett clustered column chart i PowerPoint med Aspose.Slides
  för Java
url: /sv/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man lägger till stapeldiagram med klustrade kolumner i PowerPoint med Aspose.Slides för Java

## Introduktion

När du behöver **add clustered column chart** till en PowerPoint-presentation kan en tydlig visualisering förvandla råa siffror till en omedelbart förståelig berättelse. Att göra detta manuellt i PowerPoint kan vara tidskrävande, särskilt när du måste generera många bilder programmässigt. **Aspose.Slides for Java** tar bort friktionen – det låter dig skapa, anpassa PowerPoint-diagram och infoga data series diagram med bara några rader kod.

I den här handledningen kommer du att lära dig hur du:
- Initiera en ny PowerPoint-presentation med Aspose.Slides for Java.  
- **Add chart to slide** och konfigurera den som ett stapeldiagram med klustrade kolumner.  
- **Create grouped column chart** genom att definiera grupperingnivåer för kategorier.  
- **Insert data series chart** så att dina data visas korrekt.  
- Spara den färdiga presentationen som en PPTX-fil.

## Snabba svar
- **What is the primary class?** `Presentation` från `com.aspose.slides`.  
- **Which chart type is used?** `ChartType.ClusteredColumn`.  
- **Do I need a license for testing?** En gratis provperiod fungerar, men en licens tar bort utvärderingsgränser.  
- **What Java version is supported?** JDK 16 eller nyare (exemplet använder JDK 16).  
- **How to run the sample?** Lägg till Maven/Gradle‑beroendet, kompilera och kör `main`‑metoden.

## Vad är “add clustered column chart”?

Ett stapeldiagram med klustrade kolumner visar flera dataserier sida‑vid‑sida för varje kategori, vilket låter dig jämföra värden över grupper i en enda visualisering. Det är idealiskt för kvartalsförsäljning, enkätresultat eller någon situation där du behöver kontrastera flera dataset inom samma kategori.

## Varför använda Aspose.Slides för att lägga till stapeldiagram med klustrade kolumner?

Du kan generera dussintals bilder automatiskt, anpassa varje visuellt element och köra koden på vilket operativsystem som helst som stödjer Java—ingen Microsoft Office‑installation krävs. Aspose.Slides stöder **50+ diagramtyper** och kan bearbeta presentationer med **upp till 500 bilder** utan att ladda hela filen i minnet, vilket gör det lämpligt för rapporteringspipelines i stor skala.

## Förutsättningar

- **Aspose.Slides for Java**‑biblioteket (senaste versionen rekommenderas).  
- JDK 16 eller senare.  
- Maven‑ eller Gradle‑byggverktyg (eller så kan du lägga till JAR‑filen manuellt).  
- En IDE eller textredigerare för att köra Java‑kod.

## Konfigurera Aspose.Slides för Java

Lägg till biblioteket i ditt projekt med ett av följande byggskript.

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

Alternativt kan du ladda ner den senaste versionen direkt från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensförvärv

Innan du distribuerar i produktion, skaffa en licens:
- **Free trial** – utforska alla funktioner utan köp.  
- **Temporary license** – utvärdera utökade funktioner under en kort period.  
- **Full license** – lås upp obegränsad användning. Skaffa den från [Aspose's purchase page](https://purchase.aspose.com/buy).

## Hur man lägger till ett stapeldiagram med klustrade kolumner i PowerPoint med Aspose.Slides för Java?

Läs in en ny `Presentation`, lägg till en bild, infoga ett `Chart` av typen `ChartType.ClusteredColumn`, fyll dess interna arbetsbok med kategorier och serier, och spara sedan filen som en PPTX. Denna sekvens skapar ett fullt funktionellt stapeldiagram med grupperade kolumner med bara ett fåtal API‑anrop.

### Initiera presentation

`Presentation` är klassen som representerar en PowerPoint‑fil i minnet, vilket låter dig lägga till bilder, former och diagram programmässigt.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Lägg till diagram på bild

`ChartType.ClusteredColumn` instruerar Aspose.Slides att rendera ett stapeldiagram med grupperade kolumner.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Förbered diagrammets datarbok

Diagrammet lagrar sina data i en intern arbetsbok. Att rensa den ger dig en ren start för anpassade data.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Lägg till kategorier med grupperingnivåer

Att gruppera kategorier skapar effekten av ett stapeldiagram med grupperade kolumner. Varje kategori kan tillhöra en logisk grupp som visas i axelns etiketter.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Lägg till dataserier i diagrammet

`Series`‑objekt representerar enskilda kolumner i diagrammet. Att lägga till flera serier resulterar i kolumner sida‑vid‑sida för varje kategori.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Spara presentation med diagram

Att spara `Presentation` skriver en standard PPTX‑fil som kan öppnas i vilken PowerPoint‑visare som helst.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktiska tillämpningar

- **Business reports** – jämför kvartalsintäkter över regioner.  
- **Academic research** – visa experimentresultat grupperade efter testförhållanden.  
- **Project management** – visualisera uppgiftsslutförande för flera team på en enda bild.

## Prestandaöverväganden

- **Memory management** – frigör stora arbetsböcker efter användning.  
- **Batch operations** – undvik att uppdatera diagrammet i täta loopar; samla data först, applicera sedan.  
- **Built‑in optimizations** – Aspose.Slides tillhandahåller metoder som `Presentation.optimize()` för stora filer, vilket minskar minnesavtrycket med upp till **30 %**.

## Vanliga fallgropar & tips

- **Pitfall:** Att glömma att rensa befintliga serier/kategorier kan leda till duplicerade data.  
  **Tip:** Anropa alltid `clear()` innan du fyller på ny data.  
- **Pitfall:** Använda fel celladress (t.ex. "c2" istället för "C2").  
  **Tip:** Cellreferenser är skiftlägesokänsliga, men håll dem konsekventa för läsbarhet.  
- **Tip:** Använd `setGroupingItem` för att skapa meningsfulla gruppetiketter; de visas automatiskt i diagrammets legend.

## Vanliga frågor

**Q1: Hur kan jag lägga till flera serier i mitt diagram?**  
A1: Anropa `ch.getChartData().getSeries().add()` upprepade gånger och ange ett unikt namn samt datapunkter för varje serie.

**Q2: Vilka är vanliga problem med Aspose.Slides-diagram?**  
A2: Problem uppstår ofta på grund av felaktiga dataområden eller saknade arbetsboks-celler. Verifiera att varje kategori och datapunkt har en motsvarande cell.

**Q3: Kan jag använda Aspose.Slides med andra programmeringsspråk?**  
A3: Ja, Aspose tillhandahåller motsvarande bibliotek för .NET, C++, Python och mer.

**Q4: Hur uppdaterar jag ett befintligt diagram i en presentation?**  
A4: Läs in presentationen, lokalisera diagrammet via `slide.getShapes().get_Item(index)`, och modifiera dess serier eller formatering efter behov.

**Q5: Finns det begränsningar för diagramtyper i Aspose.Slides?**  
A5: Biblioteket stöder över **50 diagramtyper** och lägger kontinuerligt till nya; kontrollera alltid den senaste dokumentationen för den mest aktuella listan.

## Resurser

- **Dokumentation:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Nedladdning:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Köp:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Gratis provperiod:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Tillfällig licens:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Supportforum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Senast uppdaterad:** 2026-09-17  
**Testad med:** Aspose.Slides for Java 25.4 (JDK 16)  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa diagramguide i Java med Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Lägg till animation i PowerPoint‑diagram med Aspose.Slides för Java – En steg‑för‑steg‑guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}