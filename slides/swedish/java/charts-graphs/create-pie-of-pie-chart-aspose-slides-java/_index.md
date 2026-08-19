---
date: '2026-07-17'
description: Lär dig hur du lägger till ett diagram i PowerPoint genom att skapa ett
  Pie of Pie-diagram med Aspose.Slides för Java. Inkluderar installation, kod, anpassning
  och sparande som PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Lägg till diagram i PowerPoint med Aspose.Slides för Java. Denna guide
  visar hur du skapar, anpassar och sparar ett Pie of Pie-diagram som PPTX på några
  minuter.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Lägg till diagram i PowerPoint – Skapa ett Pie of Pie-diagram i Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Lägg till diagram i PowerPoint – Skapa ett Pie of Pie-diagram i Java med Aspose.Slides
url: /sv/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Lägg till diagram i PowerPoint – Skapa ett Pie of Pie-diagram i Java med Aspose.Slides

## Diagram & Grafer

### Introduktion

I moderna datadrivna presentationer är **att lägga till ett diagram i PowerPoint** ofta det snabbaste sättet att omvandla råa siffror till visuell insikt. Ett vanligt cirkeldiagram fungerar bra för ett fåtal kategorier, men när några segment är mycket små blir de oläsliga. Ett *Pie of Pie*-diagram löser detta problem genom att extrahera de små segmenten till ett sekundärt cirkeldiagram, vilket håller huvuddiagrammet rent och detaljerna tillgängliga.

I den här handledningen kommer du att lära dig hur du **lägger till ett diagram i PowerPoint** genom att skapa ett Pie of Pie-diagram med Aspose.Slides för Java. Vi går igenom miljöinställning, diagramskapande, anpassning av etiketter, justering av delningsposition och slutligen sparar presentationen som en PPTX-fil. När du är klar är du redo att bädda in avancerade diagram i vilken bildspel som helst.

## Snabba svar
I Aspose.Slides representerar `Presentation` en PPTX-fil, `ChartType.PieOfPie` väljer Pie of Pie-diagrammet, `setShowValue(true)` visar värden på etiketter, och `save` skriver filen.

- **Vad är den primära klassen för PowerPoint-manipulation?** `Presentation` – den representerar en hel PPTX-fil i minnet.  
- **Vilken diagramtyp skapar ett sekundärt cirkeldiagram för små segment?** `ChartType.PieOfPie`.  
- **Hur visar du värden på varje segment?** Sätt `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Kan du spara filen direkt som PPTX?** Ja – anropa `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Behöver du en licens för utveckling?** En gratis 30‑dagars provperiod fungerar för testning; en permanent licens tar bort utvärderingsvattenstämplar.

## Vad är ett Pie of Pie-diagram?

Ett **Pie of Pie-diagram** är en tvånivå-cirkeldiagramvisualisering som isolerar ett eller flera små segment i ett separat, länkat cirkeldiagram, vilket gör dem lättare att läsa. Aspose.Slides stöder denna diagramtyp direkt, så att du kan kontrollera delningsstorlek, position och etikettformatering.

## Varför lägga till diagram i PowerPoint med Aspose.Slides?

Aspose.Slides kan generera, redigera och rendera PowerPoint-filer utan att Microsoft Office är installerat. Det stöder **50+ in- och utdataformat**, bearbetar presentationer med **upp till 500 bilder** på under en sekund på vanlig serverhårdvara, och ger **full API-kontroll** över diagramstil, datalabels och layout—perfekt för automatiserade rapporteringspipelines.

## Förutsättningar

Innan du börjar, se till att du har:

- **Java Development Kit (JDK) 16+** installerat.
- En IDE såsom **IntelliJ IDEA**, **Eclipse**, eller **NetBeans**.
- Maven eller Gradle för beroendehantering (se avsnitten nedan).
- Grundläggande Java-kunskaper och erfarenhet av att bygga projekt.

## Konfigurera Aspose.Slides för Java

### Installationsinformation

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direktnedladdning:** Du kan ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Steg för att skaffa licens

- **Gratis provperiod:** Börja med en 30‑dagars provperiod för att utforska alla funktioner.  
- **Tillfällig licens:** Begär en tillfällig nyckel för förlängd utvärdering.  
- **Köp:** Skaffa en permanent licens för produktionsbruk för att ta bort utvärderingsvattenstämplar.

### Grundläggande initiering och konfiguration

`Presentation` är huvudobjektet för att skapa PowerPoint-filer, och `Chart` representerar ett diagram i en bild.

```java
Presentation presentation = new Presentation();
```  

Detta skapar en tom presentation klar för bilder och diagram.

## Implementeringsguide

### Hur lägger du till ett diagram i PowerPoint med Aspose.Slides för Java?

Läs in en ny `Presentation`, lägg till en bild och infoga ett `Chart` av typen `PieOfPie`. API-anropkedjan är kortfattad: skapa diagrammet, fyll i seriedata, justera etikettens synlighet, konfigurera storleken på det sekundära cirkeldiagrammet och spara slutligen. Hela processen ryms vanligtvis i under 20 kodrader, vilket gör den idealisk för automatiserad rapportgenerering.

### Skapa ett 'Pie of Pie'-diagram

#### Översikt
Vi kommer att bygga ett Pie of Pie-diagram på den första bilden, separera de minsta segmenten och märka varje segment med dess värde.

#### Steg 1: Skapa en instans av Presentation-klassen
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Detta initierar behållaren för alla efterföljande bilder och diagram.

#### Steg 2: Lägg till ett 'Pie of Pie'-diagram på den första bilden
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Här specificerar vi `ChartType.PieOfPie` och definierar diagrammets position (X, Y) och storlek (bredd, höjd) på bildens canvas.

#### Steg 3: Ställ in datalabels för att visa värden för serien
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Att aktivera `showValue` får varje segment att visa sitt numeriska värde, vilket är viktigt för snabb datatolkning.

#### Steg 4: Konfigurera storleken på det sekundära cirkeldiagrammet och dela efter procent
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Dessa alternativ låter dig bestämma hur stor del av diagrammet som tilldelas det sekundära cirkeldiagrammet och vilka segment som flyttas baserat på en procentuell tröskel.

#### Steg 5: Spara presentationen till disk i PPTX-format
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Proffstips:** Använd en absolut sökväg eller Javas `Paths.get()` för att undvika plattforms‑specifika avgränsare.

## Vanliga problem och lösningar

`License`-klassen laddar en licensfil för att ta bort utvärderingsrestriktioner.

- **Varning om saknad licens:** Om du ser “Evaluation Only” på diagrammet, se till att du har tillämpat en giltig licensfil via `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Felaktig segmentdelning:** Verifiera att egenskapen `splitBy` är satt till `SplitBy.Percentage` och att `secondPieSize` är ett värde mellan 0 och 100.
- **Data visas inte:** Bekräfta att diagrammets serie innehåller minst en datapunkt; annars renderas diagrammet tomt.

## Vanliga frågor

`IChart` representerar ett diagramobjekt som kan läggas till på en bild.

**Q: Kan jag generera flera diagram i en enda presentation?**  
A: Ja, skapa en ny `IChart` för varje bild eller plats; API:et tillåter obegränsat antal diagramobjekt per fil.

`SaveFormat.Pdf` specificerar PDF-utdataformat för sparande.

**Q: Stöder Aspose.Slides att spara som PDF också?**  
A: Absolut – anropa `presentation.save("output.pdf", SaveFormat.Pdf)` för att exportera samma bildspel till PDF.

`IPortion` representerar ett enskilt segment i ett cirkeldiagram.

**Q: Vad är det maximala antalet datapunkter ett Pie of Pie-diagram kan hantera?**  
A: Biblioteket stöder upp till **10 000** datapunkter per serie, begränsat endast av tillgängligt minne.

**Q: Är det möjligt att anpassa färgerna på enskilda segment?**  
A: Ja, få åtkomst till varje `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()` och sätt `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Hur bäddar jag in den genererade PPTX-filen i en webbapplikation?**  
A: Efter att ha sparat filen, strömma den direkt till klienten med `HttpServletResponse` och `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Slutsats

Du har nu ett komplett, produktionsklart recept för **att lägga till ett diagram i PowerPoint** genom att skapa ett Pie of Pie-diagram med Aspose.Slides för Java. Experimentera med olika delningströsklar, etikettformat och färgscheman för att matcha dina varumärkesriktlinjer. Nästa steg är att utforska andra diagramtyper—såsom staplat stapeldiagram eller radardiagram—för att ytterligare berika dina automatiserade bildspel.

---

**Senast uppdaterad:** 2026-07-17  
**Testat med:** Aspose.Slides for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa dynamiskt diagram Java – PowerPoint-diagramhandledningar för Aspose.Slides](/slides/java/charts-graphs/)
- [Hur man lägger till cirkeldiagram i PowerPoint med Aspose.Slides för Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}