---
date: '2026-07-17'
description: Lär dig hur du lägger till Sunburst Charts i PowerPoint med Aspose Slides
  for Java. Steg‑för‑steg‑guiden täcker installation, diagramskapande, anpassning
  och verkliga användningsfall.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Hur du lägger till Sunburst Charts i PowerPoint med Aspose Slides
  for Java. Följ den här handledningen för att installera biblioteket, skapa ett diagram,
  anpassa datapunkter och använda det i riktiga projekt.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Hur man lägger till Sunburst Charts i PowerPoint med Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Hur man lägger till Sunburst Charts i PowerPoint med Aspose (Java)
url: /sv/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man lägger till Sunburst-diagram i PowerPoint med Aspose (Java)

## Introduktion

Att lägga till ett Sunburst-diagram i en PowerPoint-presentation kan omedelbart förvandla en platt datatabell till en engagerande visuell hierarki. I den här handledningen kommer du att lära dig **hur man lägger till Sunburst**-diagram i PowerPoint med Aspose.Slides för Java, från miljöinställning till finjustering av färger och etiketter. Oavsett om du bygger en försäljningsdashboard, en projekt‑uppgiftsuppdelning eller en utbildningspresentation, kommer stegen nedan att ge dig en produktionsklar lösning.

**Vad du kommer att lära dig**
- Hur man konfigurerar Aspose.Slides i ett Maven- eller Gradle‑projekt  
- Hur man skapar en ny presentation och infogar ett Sunburst‑diagram  
- Hur man anpassar datapunkter, etiketter och fyllningsfärger  
- Verkliga scenarier där Sunburst‑diagram glänser  

Låt oss komma igång och se hur enkelt det är att omvandla rå hierarkidata till en polerad PowerPoint‑visualisering.

## Snabba svar
- **Primary library?** Aspose.Slides for Java  
- **Supported chart type?** Sunburst (radial hierarchical)  
- **Minimum Java version?** JDK 16  
- **Typical implementation time?** 10‑15 minuter för ett grundläggande diagram  
- **License needed for production?** Ja, en giltig Aspose‑licens  

## Vad är ett Sunburst‑diagram?
Ett Sunburst-diagram är ett radiellt diagram som visualiserar hierarkisk data genom att nästla ringar utåt från en central punkt. Det är perfekt för att visa flernivårelationer såsom organisationsstrukturer, produktkategorier eller filsystemsträd. Varje koncentrisk ring representerar en nivå i hierarkin, och storleken på varje segment återspeglar dess kvantitativa värde, vilket gör att betraktaren snabbt kan förstå både struktur och omfattning.

## Varför använda Aspose.Slides för Java?
Aspose.Slides stödjer **50+ diagramtyper** och kan manipulera presentationer med **upp till 10 000 bilder** utan att ladda in hela filen i minnet, vilket ger hög prestanda för företags‑omfattande rapportering. Det fungerar plattformsoberoende, erbjuder omfattande API‑täckning och inkluderar robusta licensalternativ som tar bort utvärderingsgränser, vilket gör det idealiskt för produktionsmiljöer.

## Förutsättningar
- **Java Development Kit (JDK)** 16 eller nyare  
- **IDE** – IntelliJ IDEA, Eclipse eller någon Java‑kompatibel redigerare  
- Grundläggande kunskap om Java‑syntax och Maven/Gradle‑byggverktyg  

## Installera Aspose.Slides för Java

### Maven‑beroende
Add the Aspose.Slides Maven artifact to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑beroende
If you prefer Gradle, include the following line in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direktnedladdning
Du kan också ladda ner den senaste JAR-filen direkt från den officiella releases‑sidan: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensanskaffning
To run without evaluation limits, obtain a license:
- **Gratis provperiod** – temporär licens för snabb utvärdering.  
- **Tillfällig licens** – begär en från [Aspose website](https://purchase.aspose.com/temporary-license).  
- **Fullt köp** – köp ett abonnemang för obegränsad produktionsanvändning.

### Grundläggande initiering
The `Presentation` class is the entry point for creating or opening PowerPoint files.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Implementeringsguide

### Hur man lägger till ett Sunburst‑diagram i en PowerPoint‑presentation med Aspose.Slides för Java?

Load a new `Presentation`, add a slide, insert an `IChart` of type `ChartType.Sunburst`, and call `save`. This concise three‑step pattern creates a fully functional sunburst chart ready for further customization.

#### Steg 1: Initiera presentationen
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Steg 2: Lägg till Sunburst‑diagram
The `IChart` interface defines a chart object that can be placed on any slide. Here we add a sunburst chart at coordinates (100, 100) with a size of 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Steg 3: Spara presentationen
Always persist your changes by calling `save`. You can choose PPTX, PDF, or any of the 50+ supported output formats.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Ändra datapunkter i diagrammet

#### Översikt
You can tailor every slice of the sunburst—labels, colors, and visibility—through the chart’s data point collection.

#### Steg 1: Åtkomst till datapunktssamlingen
The first series of the chart holds a collection of `IChartDataPoint` objects that represent each slice.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Steg 2: Visa värde för en specifik datapunkt
Set `IsValueShown` to `true` on the desired data point to display its numeric value directly on the slice.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Steg 3: Ändra etikettformat
Adjust label visibility, font color, and background to improve readability.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Steg 4: Ställ in fyllningsfärg för datapunkter
Customize the fill color of individual slices to match your brand palette or to highlight key segments.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Steg 5: Spara den modifierade presentationen
Persist the customized chart by saving the presentation again.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktiska tillämpningar

1. **Affärsanalys** – Visualisera försäljning per region → produktlinje → SKU i en enda radiell vy.  
2. **Projektledning** – Visa arbetsnedbrytningsstrukturer, från faser till uppgifter till deluppgifter.  
3. **Utbildning** – Kartlägg läroplanshierarkier, såsom avdelningar → kurser → moduler.  

## Prestandaöverväganden

- **Minneseffektivitet:** Aspose.Slides strömmar data, så även en 500‑sidig presentation med flera diagram håller sig under 200 MB RAM.  
- **Soppsamling:** Frigör slide‑objekt (`slide.dispose()`) när de inte längre behövs för att undvika minnesläckor.  

## Vanliga frågor

**Q: What is a sunburst chart?**  
A: A sunburst chart visualizes hierarchical data in concentric rings, with each ring representing a level of the hierarchy.

**Q: How do I install Aspose.Slides for Java using Maven?**  
A: Add the Maven dependency shown in the “Maven Dependency” section to your `pom.xml` and run `mvn clean install`.

**Q: Can I customize other chart types with Aspose.Slides?**  
A: Yes, the library supports over 50 chart types, including column, line, pie, and radar charts.

**Q: My presentation isn’t saving—what should I check?**  
A: Verify the file path is correct, the directory exists, and you have write permissions. Also, ensure the `Presentation.save()` method is called.

**Q: Where can I get more help or examples?**  
A: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).

## Resurser
- **Dokumentation:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referens (gemener):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Community‑forum:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Nedladdningar:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animera diagram i PowerPoint med Aspose.Slides för Java – En steg‑för‑steg‑guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Skapa diagram i Java med Aspose.Slides – Lägg till & validera diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}