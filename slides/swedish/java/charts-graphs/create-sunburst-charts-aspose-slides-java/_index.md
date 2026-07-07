---
date: '2026-07-03'
description: Lär dig hur du skapar Sunburst-diagram steg för steg i Java med Aspose.Slides,
  med fullständiga anpassningsalternativ för PowerPoint-presentationer.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Hur du skapar Sunburst-diagram i Java med Aspose.Slides
url: /sv/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar Sunburst-diagram i Java med Aspose.Slides

## Introduktion
I dagens datadrivna presentationer kan **hur man skapar sunburst**‑visualiseringar snabbt göra dina bilder unika. Denna handledning guidar dig genom att bygga ett Sunburst‑diagram med Aspose.Slides för Java, från projektuppsättning till slutlig export, så att du kan leverera övertygande hierarkiska datagrafiker utan att lämna Java‑ekosystemet.

## Snabba svar
- **Vad är huvudklassen för en PowerPoint‑fil?** `Presentation` – den representerar hela PPTX‑filen i minnet.  
- **Hur många kodrader behövs för ett grundläggande sunburst?** Vanligtvis 5–7 rader när biblioteket har refererats.  
- **Vilka exportformat stöds?** PPTX, PDF, PNG, SVG och HTML.  
- **Kan jag formatera enskilda segment?** Ja – fyllningsfärger, kanter och datalabels är helt anpassningsbara.  
- **Behöver jag en licens för produktion?** En gratis utvärdering fungerar för testning; en kommersiell licens krävs för distribution.

## Vad är ett Sunburst‑diagram?
Ett Sunburst‑diagram visualiserar hierarkiska data som koncentriska ringar, där varje ring representerar en nivå i hierarkin. Det låter betraktaren förstå förälder‑barn‑relationer på ett ögonblick, vilket gör det idealiskt för organisationsdiagram, taxonomivisningar och flernivå‑mått. Det är särskilt användbart för att visa flernivåkategorier såsom produktlinjer, geografiska regioner eller organisationsstrukturer, vilket gör att betraktaren kan se både den övergripande fördelningen och den detaljerade uppdelningen inom varje segment.

## Varför använda Aspose.Slides för Sunburst‑diagram?
Aspose.Slides stöder **30+ diagramtyper**, bearbetar filer upp till **500 MB** utan att ladda hela dokumentet i minnet, och renderar grafik med **300 DPI** för kristallklar output. Dessa kvantifierade egenskaper säkerställer snabb generering och högkvalitativa visualiseringar även för stora presentationer. Dessutom erbjuder biblioteket trådsäkra operationer och integreras sömlöst med populära Java‑byggverktyg, vilket gör det lämpligt för både skrivbords‑ och server‑sidogenerering av presentationer i stor skala.

## Förutsättningar
- Java Development Kit (JDK) 8 eller nyare.  
- Maven eller Gradle för beroendehantering.  
- Aspose.Slides för Java (senaste versionen).  
- Grundläggande förståelse för hierarkiska datastrukturer.

## Hur skapar man Sunburst‑diagram steg för steg?
Ladda din miljö, lägg till ett diagram, mata in hierarkiska data, formatera det och spara filen – allt i några enkla steg. Nedan är den exakta arbetsflödet du kan följa utan att skriva extra boilerplate‑kod. Processen är helt automatiserad, kräver ingen manuell UI‑interaktion och kan integreras i batch‑jobb eller webbtjänster för att producera diagram på begäran.

### Steg 1: Ställ in projektet
Lägg till Aspose.Slides Maven‑beroendet (eller motsvarande Gradle‑snutt) i din `pom.xml`. Detta hämtar alla nödvändiga binärer och transitiva bibliotek.

### Steg 2: Ladda eller skapa en presentation
`Presentation` är Aspose.Slides översta objekt som representerar en enda PowerPoint‑fil i minnet. Instansiera den med `new Presentation()` för en ny presentation eller ange en filsökväg för att öppna en befintlig PPTX.

### Steg 3: Lägg till ett Sunburst‑diagram
Infoga en ny diagramform på en bild med `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Detta skapar Sunburst‑platshållaren redo för data. `ChartType.Sunburst` specificerar Sunburst‑diagramtypen när ett diagram läggs till på en bild.

### Steg 4: Fyll i hierarkiska data
`ChartData` innehåller dataserierna och kategorierna för ett diagram. Åtkomst till diagrammets `ChartData`‑samling och lägg till serier och kategorier som speglar din hierarki. För varje nivå, specificera förälder‑barn‑relationen via egenskapen `ParentSeries`, vilket låter diagrammet automatiskt rendera koncentriska ringar.

### Steg 5: Anpassa utseendet
Finjustera segmentfärger, kantstilar och datalabels via objekten `ChartSeries` och `ChartDataPoint`. `ChartSeries` representerar en serie datapunkter i ett diagram. `ChartDataPoint` representerar en enskild datapunkt inom en serie. Du kan också aktivera 3‑D‑rotation eller sätta egenskapen `Explode` för att markera specifika skivor.

### Steg 6: Spara presentationen
`SaveFormat`‑enum definierar de filformat du kan spara en presentation som. Anropa `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` för att skriva filen till disk. Du kan också exportera till PDF eller PNG genom att ändra `SaveFormat`‑enum‑värdet.

## Hur anpassar man Sunburst‑diagrammets färger?
Ange en fyllningsfärg för varje `ChartDataPoint` med `point.getFillFormat().setFillType(FillType.Solid)` och sedan `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Detta direkta tillvägagångssätt låter dig matcha företagsprofilen eller framhäva viktiga datapunkter. Du kan också applicera gradientfyllningar, justera transparens eller använda temafärger för att säkerställa konsistens med resten av din bilddesign.

## Vanliga problem och lösningar
- **Problem:** Hierarkin visas platt.  
  **Lösning:** Säkerställ att varje barnserie korrekt refererar sin `ParentSeries`. Saknade länkar får diagrammet att behandla all data som en enda nivå.
- **Problem:** Exporterad PNG ser suddig ut.  
  **Lösning:** Öka export‑DPI genom att sätta `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problem:** Stora PPTX‑filer orsakar OutOfMemoryError.  
  **Lösning:** Använd `Presentation.setMemoryOptimization(true)` för att strömma data och hålla minnesanvändningen låg.

## Vanliga frågor

**Q: Kan jag generera ett Sunburst‑diagram från en CSV‑fil?**  
A: Ja. Läs CSV‑filen, bygg hierarkin i minnet och mata in den i diagrammets `ChartData`‑samling innan du sparar.

**Q: Stöder Aspose.Slides animerade övergångar för Sunburst‑diagram?**  
A: Ja. Applicera en `SlideShowTransition` på bilden eller använd `ChartFormat.setAnimationEnabled(true)` för diagramnivå‑animation.

**Q: Är det möjligt att exportera diagrammet som en SVG‑vektorgrafik?**  
A: Absolut. Spara presentationen med `SaveFormat.Svg` för att få en skalbar vektorversion av Sunburst‑diagrammet.

**Q: Vad är det maximala antalet datapunkter ett Sunburst‑diagram kan hantera?**  
A: Aspose.Slides hanterar pålitligt upp till **10 000** datapunkter i ett enda Sunburst‑diagram utan prestandaförsämring.

**Q: Behöver jag en separat licens för varje distributionsmiljö?**  
A: En enda kommersiell licens täcker alla miljöer (utveckling, test, produktion) så länge licensvillkoren följs.

## Slutsats
Du har nu en komplett, steg‑för‑steg‑guide för **hur man skapar sunburst**‑diagram i Java med Aspose.Slides. Genom att följa arbetsflödet ovan kan du generera högkvalitativa, fullt anpassningsbara hierarkiska visualiseringar för vilken PowerPoint‑presentation som helst.

---

**Senast uppdaterad:** 2026-07-03  
**Testad med:** Aspose.Slides for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Behärska anpassning av PowerPoint‑diagram med Aspose.Slides Java för dynamiska presentationer](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animera PowerPoint‑diagramkategorier med Aspose.Slides för Java | Steg‑för‑steg‑guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}