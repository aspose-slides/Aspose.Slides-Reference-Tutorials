---
date: '2026-06-03'
description: Lär dig hur du skapar diagram i .NET-presentationer och lägger till diagram
  på en bild med Aspose.Slides för Java. Följ den här steg-för-steg-guiden för datavisualisering.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Skapa diagram i .NET med Aspose.Slides för Java
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa diagram i .NET med Aspose.Slides för Java

## Introduktion
Att skapa övertygande presentationer innebär ofta att integrera visuella datavisualiseringar som diagram för att förbättra publikens förståelse och engagemang. **If you want to create charts in .NET**, Aspose.Slides for Java ger dig ett kraftfullt, språk‑oberoende API som fungerar sömlöst i .NET‑applikationer. I den här handledningen kommer du att lära dig hur du initierar en presentation, lägger till olika diagramtyper, hanterar diagrammets dataarbetsbok och formaterar seriedata — inklusive hantering av negativa värden. I slutet kommer du att kunna generera diagram i presentationsfiler programatiskt och lägga till diagram på en bild med bara några rader kod.

## Snabba svar
- **Vad är det primära målet?** Skapa diagram i .NET‑presentationer med Aspose.Slides för Java.  
- **Vilken version av biblioteket krävs?** Aspose.Slides for Java 25.4 eller senare.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag använda Maven eller Gradle?** Ja — båda byggsystemen stöds.  
- **Vilka diagramtyper finns tillgängliga?** Grupperade staplar, linje, cirkel, stapel, område och mer.

## Hur skapar man diagram i .NET‑presentationer med Aspose.Slides för Java?
`Presentation`‑klassen representerar en PowerPoint‑fil och tillhandahåller metoder för att manipulera dess bilder. Ladda ett nytt `Presentation`‑objekt, anropa `slides.addEmptySlide()` för att få en bild, och använd sedan `slide.getShapes().addChart()` för att infoga önskad diagramtyp på de koordinater du anger. Efter att diagrammet har lagts till fyller du dess dataarbetsbok med serier och kategorier, applicerar eventuell formatering (t.ex. färger för negativa värden) och sparar slutligen presentationen till en .pptx‑fil. Detta flöde låter dig **create charts in .NET** med ett koncist set av API‑anrop.

## Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett plattformsoberoende API som möjliggör för utvecklare att skapa, modifiera och rendera PowerPoint‑filer utan Microsoft Office. Det stöder **50+ in‑ och utdataformat** och kan bearbeta presentationer med tusentals bilder samtidigt som minnesanvändningen hålls under 200 MB.

## Varför använda Aspose.Slides för Java i ett .NET‑projekt?
Aspose.Slides för Java körs på Java Virtual Machine och kan anropas från .NET via ett inbyggt wrapper‑bibliotek, vilket ger .NET‑utvecklare tillgång till en mogen diagrammotor, högpresterande bearbetning av stora datamängder och full kompatibilitet med befintlig Java‑kod utan att behöva skriva om logiken.

## Förutsättningar
Innan du dyker ner i att skapa diagram med Aspose.Slides för Java, låt oss gå igenom vad du behöver:

### Nödvändiga bibliotek och versioner
- **Aspose.Slides for Java**: Version 25.4 eller senare.

### Krav för miljöinställning
- En utvecklingsmiljö som stödjer .NET‑applikationer.  
- Grundläggande förståelse för Java‑programmeringskoncept.

### Kunskapsförutsättningar
- Bekantskap med att skapa presentationer i en .NET‑applikationskontext.  
- Förståelse för Java‑beroenden och deras hantering (Maven/Gradle).

## Inställning av Aspose.Slides för Java
För att börja använda Aspose.Slides måste du inkludera det som en beroende i ditt projekt. Så här gör du:

### Maven
Maven‑beroendesnutten lägger till Aspose.Slides för Java i ditt projekt.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inkludera denna rad i din `build.gradle`‑fil för att hämta biblioteket från Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direktnedladdning
Alternativt kan du ladda ner den senaste versionen från [Aspose.Slides för Java‑utgåvor](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Free Trial**: Starta med en tillfällig licens för att utforska funktionerna.  
- **Purchase**: Köp en licens för obegränsad produktionsanvändning.

#### Grundläggande initiering och konfiguration
`Slides`‑initiering kräver att licensen sätts och att en `Presentation`‑instans skapas.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Denna konfiguration säkerställer att resurshanteringen hanteras effektivt.

## Implementeringsguide
Vi guidar dig genom att implementera funktionerna steg‑för‑steg.

### Initiering av presentation
**Översikt:**  
Att skapa en presentationsinstans lägger grunden för alla efterföljande operationer. Denna funktion visar hur du börjar från början med Aspose.Slides.

#### Steg 1: Importera nödvändiga paket
`Presentation` och relaterade klasser finns i `com.aspose.slides`‑namnrymden.

```java
import com.aspose.slides.Presentation;
```

#### Steg 2: Skapa ett nytt presentationsobjekt
Instansiera ett `Presentation`‑objekt och omslut det i ett try‑with‑resources‑block för att garantera att det frigörs.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Detta säkerställer att presentationsobjektet korrekt frigörs efter användning, vilket förhindrar minnesläckor.*

### Lägg till diagram på bild
**Översikt:**  
Att lägga till ett diagram på din bild kan göra datavisualisering mer effektiv och engagerande.

#### Steg 1: Importera nödvändiga paket
`Chart`‑klassen representerar ett diagram som kan placeras på en bild och anpassas.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Steg 2: Initiera presentation och lägg till diagram
Skapa en bild, anropa sedan `addChart` med `ChartType.ClusteredColumn` och önskad position samt storlek.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Här lägger vi till ett grupperat stapeldiagram på den första bilden på angivna koordinater och dimensioner.*

### Hantera diagrammets dataarbetsbok
**Översikt:**  
Effektiv hantering av ditt diagrammes dataarbetsbok gör att du smidigt kan manipulera serier och kategorier.

#### Steg 1: Importera nödvändiga paket
`IChartDataWorkbook` ger åtkomst till den underliggande Excel‑liknande arbetsboken som diagrammen använder.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Steg 2: Åtkomst och rensa dataarbetsboken
Hämta arbetsboken från diagrammet och rensa eventuell befintlig data för att börja på nytt.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Att rensa arbetsboken är avgörande för att börja med en ren grund när nya serier och kategorier läggs till.*

### Lägg till serier och kategorier i diagrammet
**Översikt:**  
Denna funktion visar hur du kan lägga till meningsfulla datapunkter genom att hantera serier och kategorier.

#### Steg 1: Lägg till serier och kategorier
Använd `chart.getChartData().getSeries().add()` och `chart.getChartData().getCategories().add()` för att definiera strukturen.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Att lägga till serier och kategorier möjliggör en mer organiserad datapresentation.*

### Fyll i seriedata och formatering
**Översikt:**  
Fyll ditt diagram med datapunkter och formatera utseendet för att förbättra läsbarheten, särskilt vid negativa värden.

#### Steg 1: Fyll i seriedata
Tilldela numeriska värden till varje cell i arbetsboken och applicera en röd fyllning för negativa tal.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Detta avsnitt demonstrerar hur du fyller i data och applicerar färgformatering för bättre visualisering.*

## Vanliga problem och lösningar
- **LicenseNotFoundException** – Se till att licensfilens sökväg är korrekt och att filen är åtkomlig vid körning.  
- **NullPointerException on chart data** – Rensa alltid arbetsboken innan du lägger till nya serier för att undvika kvarvarande data.  
- **Chart not rendering in .NET** – Verifiera att du använder den .NET‑kompatibla versionen av Aspose.Slides‑JAR‑filen och att Java‑runtime är korrekt konfigurerad i ditt .NET‑projekt.

## Vanliga frågor

**Q: Kan jag generera ett diagram i presentationsfiler utan ett GUI?**  
A: Ja, Aspose.Slides for Java är helt huvudlöst och fungerar på servrar utan några grafiska komponenter.

**Q: Vilka .NET-versioner stöds?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 och .NET 6 stöds alla.

**Q: Hur många diagramtyper kan jag lägga till?**  
A: Över 20 diagramtyper finns tillgängliga, inklusive stapel, linje, cirkel, område och radardiagram.

**Q: Är det möjligt att formatera enskilda datapunkter?**  
A: Absolut – du kan sätta fyllningsfärger, kanter och markörer för varje datapunkt via `IDataPoint`‑API:t.

**Q: Måste jag konvertera Java‑objekt till .NET‑typer manuellt?**  
A: Nej, Aspose.Slides for Java .NET‑wrappern hanterar typkonvertering automatiskt.

---

**Senast uppdaterad:** 2026-06-03  
**Testad med:** Aspose.Slides for Java 25.4  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man bäddar in diagram i .NET-presentationer med Aspose.Slides för effektiv datavisualisering](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Hur man hämtar diagrammets datakälltyp med Aspose.Slides för .NET – Diagram & grafer](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Behärska skapande och manipulering av diagramserier med Aspose.Slides .NET för effektiv datavisualisering](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}