---
date: '2026-07-27'
description: Hur du anpassar diagram med Aspose.Slides för Java. Lär dig skapa PowerPoint-diagram,
  formatera spridningsserier och spara presentationer effektivt.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Hur du anpassar diagram med Aspose.Slides för Java. Denna guide visar
  hur du skapar ett PowerPoint-diagram, formaterar spridningspunkter och exporterar
  presentationer.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Så anpassar du diagram: Spridningsdiagram Aspose i Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Så anpassar du diagram: Spridningsdiagram Aspose i Java'
url: /sv/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Anpassa Scatter Chart Aspose i Java

I den här handledningen kommer du att upptäcka **hur man anpassar diagram** — specifikt ett spridningsdiagram — med det kraftfulla Aspose.Slides för Java‑biblioteket. Vi går igenom projektinställning, skapar ett spridningsdiagram, justerar serietyper och markörer, och sparar slutligen presentationen. I slutet kommer du att kunna generera professionellt utseende spridningsdiagram programmässigt och skräddarsy varje visuellt detalj för att matcha ditt varumärke eller rapporteringsbehov.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Slides for Java (v25.4+).  
- **Vilken Java‑version stöds?** JDK 8 eller högre.  
- **Kan jag ändra markörformer?** Ja – använd `MarkerStyleType` för att välja stjärnor, cirklar osv.  
- **Hur sparar jag filen?** Anropa `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Krävs en licens?** En gratis provperiod fungerar för utveckling; en kommersiell licens behövs för produktion.

## Hur man anpassar diagram i Java med Aspose.Slides?
`Presentation` är Aspose.Slides‑klassen som representerar en hel PowerPoint‑fil i minnet. Ladda en ny `Presentation`, lägg till ett spridningsdiagram på den första bilden, konfigurera serier och markörstilar, och anropa sedan `save`. Det enkla arbetsflödet skapar ett fullt stylat diagram på bara några rader Java‑kod, redo att inkluderas i någon PowerPoint‑presentation.

## Vad är “customize scatter chart aspose”?
Att anpassa ett spridningsdiagram med Aspose innebär att programmässigt definiera diagrammets data, utseende och beteende—allt från punktkoordinater till markörsymboler—utan att öppna PowerPoint manuellt. Detta tillvägagångssätt är idealiskt för automatiserad rapportering, databaserade presentationer eller någon situation där du behöver återupprepbara, högkvalitativa visualiseringar.

## Varför anpassa spridningsdiagram med Aspose.Slides?
Aspose.Slides ger utvecklare full programmatisk kontroll över diagrammets utseende, vilket möjliggör automatiserad skapning av högkvalitativa visualiseringar, sömlös integration i rapporteringspipeline och möjlighet att anpassa varje visuellt element utan att öppna PowerPoint manuellt, vilket sparar tid och säkerställer konsistens i presentationer.

- **Full kontroll** – ändra serietyper, markörstilar, färger och mer via Java‑kod.  
- **Automation** – generera dussintals diagram i realtid för instrumentpaneler eller batch‑rapporter.  
- **Cross‑platform** – fungerar på alla OS som stöder Java, ingen Office‑installation krävs.  
- **Prestanda** – lättviktig API som bearbetar **150+ diagramtyper** och hanterar presentationer med hundratals sidor utan att ladda hela filen i minnet.

## Förutsättningar

För att följa med, se till att du har:

- **Aspose.Slides for Java** (v25.4 eller senare).  
- **Java Development Kit (JDK)** 8 + installerat.  
- Maven eller Gradle för beroendehantering (eller så kan du ladda ner JAR‑filen manuellt).  
- Grundläggande Java‑kunskaper och bekantskap med ditt valda byggverktyg.

## Konfigurera Aspose.Slides för Java

Integrera biblioteket i ditt projekt med någon av metoderna nedan.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Eller hämta den senaste versionen från [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Licensanskaffning
- **Free Trial** – 30‑dagars utvärdering.  
- **Temporary License** – förlängd testperiod.  
- **Full License** – produktionsanvändning med premium‑support.

## Steg‑för‑steg‑guide för att anpassa Scatter Chart Aspose

### 1️⃣ Förbered en mapp för dina presentationsfiler
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Varför detta är viktigt:* Att säkerställa att målmappen finns förhindrar `FileNotFoundException` när du senare sparar PPTX‑filen.

### 2️⃣ Skapa en ny presentation och hämta den första bilden
`Presentation` representerar ett PowerPoint‑dokument och ger åtkomst till bilder och former. `Presentation`‑klassen representerar en hel PowerPoint‑fil i minnet.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Lägg till ett spridningsdiagram med mjuka linjer
`ChartType.ScatterWithSmoothLines` skapar ett spridningsdiagram där punkterna är kopplade med mjuka linjer.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Rensa eventuella standardserier och lägg till dina egna
`IChartSeries` representerar en dataserie i ett diagram.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Fyll den första serien med datapunkter
`addDataPointForScatterSeries` lägger till en enskild X‑Y‑punkt i en spridningsserie.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Anpassa serietyp och markörutseende
`Marker` styr den visuella symbolen som används för varje datapunkt i en diagramserie.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Spara presentationen
`save` skriver presentationen till en fil i det angivna formatet.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Vanliga användningsområden för anpassade spridningsdiagram
- **Finansiella instrumentpaneler** – plotta aktiekurs mot volym.  
- **Vetenskaplig forskning** – visa experimentella mätningar med felmarkörer.  
- **Projektledning** – jämför planerad vs. faktisk insats över uppgifter.  

## Prestandatips
- Anropa `pres.dispose()` efter sparning för att frigöra native‑minne.  
- För stora datamängder, fyll arbetsboken först och bind sedan serierna för att undvika upprepade UI‑uppdateringar.  
- Återanvänd en enda `IChartDataWorkbook`‑instans när du lägger till många serier för att hålla minnesanvändningen låg.

## Vanliga frågor

**Q: Hur ändrar jag färgen på markörerna?**  
A: Använd `series.getMarker().getFillFormat().setFillColor(Color)` där `Color` är en `java.awt.Color`‑instans, t.ex. `Color.RED`.

**Q: Kan jag lägga till mer än två serier i ett spridningsdiagram?**  
A: Ja. Anropa `chart.getChartData().getSeries().add(...)` för varje extra serie och fyll dess punkter därefter.

**Q: Är det möjligt att ange en anpassad legend för varje serie?**  
A: Absolut. Efter att ha skapat en serie, anropa `series.getLegend().setText("Your Legend Text")` för att åsidosätta standardnamnet.

**Q: Hur kan jag exportera diagrammet som en bild istället för en PPTX?**  
A: Anropa `chart.getImage().save("chart.png", ImageFormat.Png)` efter att diagrammet konfigurerats. Detta skapar en fristående PNG‑fil.

**Q: Vad händer om jag behöver animera spridningspunkterna?**  
A: Aspose.Slides stödjer animationseffekter. Använd `chart.getTimeline().getMainSequence().addEffect(...)` för att lägga till inträdes‑ eller betoningseffekter på diagrammet eller enskilda serier.

---

**Senast uppdaterad:** 2026-07-27  
**Testad med:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa och anpassa PowerPoint-diagram i Java med Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Hur man skapar bubbeldiagram i PowerPoint med Aspose.Slides för Java (Handledning)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Skapa och anpassa diagram med trendlinjer i Aspose.Slides för Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}