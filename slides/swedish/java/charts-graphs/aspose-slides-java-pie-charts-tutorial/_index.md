---
date: '2026-07-17'
description: Lär dig hur du roterar pie chart, anpassar pie chart colors och exporterar
  slide till PDF med Aspose.Slides för Java – en komplett guide för datavisualisering.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Roterar pie chart och anpassar pie chart colors med Aspose.Slides
  för Java. Lär dig exportera slide till PDF och arbeta med chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Roterar Pie Chart och anpassar färger i Java – Aspose.Slides Guide
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Hur man roterar Pie Chart och anpassar färger i Java med Aspose.Slides
url: /sv/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa pajdiagram med Aspose.Slides för Java: En komplett handledning

## Introduktion
I den här guiden kommer du att lära dig hur du **roterar pajdiagram**‑element, anpassar varje skivas färg och exporterar den slutliga bilden till PDF — allt med Aspose.Slides för Java. Oavsett om du bygger en försäljningsdashboard, en finansiell rapport eller någon datadriven presentation, gör behärskning av dessa tekniker att du kan leverera tydliga, iögonfallande visualiseringar utan att förlita dig på Microsoft Office. Låt oss förbereda verktygen och sätta igång.

## Snabba svar
- **Vilken klass startar en ny presentation?** `Presentation` från `com.aspose.slides`.
- **Vilket API‑anrop lägger till ett pajdiagram?** `slide.addChart(ChartType.Pie, …)`.
- **Hur kan du ge varje skiva en unik färg?** Anropa `series.setColorVaried(true)` och sätt solida fyllningar per datapunkt.
- **Vilken metod roterar diagrammet?** `chart.setRotationAngle(double)` – använd grader från 0 till 360.
- **Kan bilden exporteras till PDF?** Ja, anropa `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Vad innebär “customize pie chart colors”?
Att anpassa färgerna i ett pajdiagram innebär att tilldela olika fyllningsfärger till varje skiva i diagrammet, vilket förbättrar läsbarheten och den visuella effekten. I Aspose.Slides uppnår du detta genom att aktivera varierade färger och sedan sätta solida fyllningsfärger för enskilda datapunkter. Detta tillvägagångssätt säkerställer att varje datasegment tydligt framträder i presentationen.

## Varför använda Aspose.Slides för Java för att skapa pajdiagram?
Aspose.Slides stöder **150+ diagramtyper** och kan rendera en 300‑sidig presentation på under **5 sekunder** på en vanlig server, helt utan att behöva Microsoft Office installerat. Biblioteket körs på Windows, Linux och macOS, vilket ger dig plattformsoberoende flexibilitet för alla Java‑baserade datavisualiseringsprojekt.

## Förutsättningar
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 eller nyare
- IDE såsom IntelliJ IDEA, Eclipse eller NetBeans
- Grundläggande Java‑kunskaper och erfarenhet av Maven eller Gradle

## Installera Aspose.Slides för Java
Lägg till biblioteket i din byggkonfiguration.

**Maven**  
Lägg till detta kodsnutt i din `pom.xml`‑fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Inkludera följande i din `build.gradle`‑fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktnedladdning**  
Om du föredrar en manuell metod, ladda ner den senaste JAR‑filen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Steg för att skaffa licens
- **Free Trial** – utforska alla funktioner utan kostnad.  
- **Temporary License** – förläng provperiodens begränsningar under en kort period.  
- **Purchase** – skaffa en permanent licens för produktionsbruk.

**Grundläggande initiering och konfiguration**  
`Presentation`‑klassen representerar en PowerPoint‑fil i minnet och tillhandahåller metoder för att manipulera bilder.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementeringsguide
Nedan följer en steg‑för‑steg‑genomgång som täcker allt från att skapa en bild till att rotera det slutgiltiga pajdiagrammet.

### Initiera Presentation och Bild
Skapa en ny `Presentation`‑instans och hämta den första bilden för att fungera som diagrammets canvas.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Lägg till pajdiagram på bilden
`addChart` lägger till en diagramform av den angivna typen på bilden på angivna koordinater.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ställ in diagramtitel
`setTitle` tilldelar en texttitel till diagrammet och placerar den centralt.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurera datalabels för serie
`setShowValue(true)` aktiverar numeriska värdelabels på varje datapunkt i serien.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Förbered diagramdatablad
`ChartDataWorkbook` lagrar den underliggande datatabellen som förser diagramserierna och kategorierna.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Lägg till kategorier i diagrammet
`addCategory` skapar en ny kategorietikett för diagrammets dataserier.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Lägg till serie och fyll i datapunkter
`addSeries` skapar en dataserie, och `addDataPointForBarSeries` infogar numeriska värden för varje kategori.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Anpassa seriefärger och kanter
`setColorVaried(true)` möjliggör färger per skiva, och `setFillFormat` tilldelar en solid fyllning till varje datapunkt.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Konfigurera anpassade datalabels
`setDataLabelFormat` anpassar etikettens utseende, position och teckensnitt för tydligare diagramanteckningar.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ställ in rotationsvinkel och spara presentation
`setRotationAngle` roterar hela pajdiagrammet, och `save` skriver presentationen till en fil.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Hur roterar man pajdiagram?
Läs in diagramobjektet, anropa `chart.setRotationAngle(45.0)` (eller vilket gradvärde som helst), och spara sedan presentationen. Att rotera ett pajdiagram förskjuter startvinkeln, vilket låter dig framhäva ett specifikt segment utan att ändra data. Detta enkla metodanrop fungerar för alla `Chart`‑instanser i Aspose.Slides. Du kan också kombinera rotation med varierade skivfärger för att rikta uppmärksamheten mot den viktigaste datapunkten.

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Se till att du aktiverar varierade färger på seriegruppen. |
| **Data labels not showing** | `showValue` flag disabled | Anropa `setShowValue(true)` på etikettformatet. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Uppgradera till version 25.4 eller senare. |
| **License exception at runtime** | Missing or invalid license file | Ladda din licens med `License license = new License(); license.setLicense("Aspose.Slides.lic");` innan du skapar `Presentation`. |

## Vanliga frågor

**Q: Hur får jag en Aspose.Slides‑licens för Java?**  
A: Begär en gratis provversion från Aspose‑webbplatsen, köp sedan en permanent licens. Ladda den vid körning som visas i tabellen under Vanliga problem.

**Q: Kan jag använda den här koden med äldre JDK‑versioner?**  
A: API‑et kräver JDK 16 eller högre; äldre versioner stöds inte.

**Q: Är det möjligt att exportera diagrammet som en bild istället för PPTX?**  
A: Ja—efter rendering, anropa `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Vad händer om jag behöver mer än en serie i ett pajdiagram?**  
A: Pajdiagram är avsedda för en enda dataserie; för flera serier, överväg att använda ett donut‑diagram.

**Q: Kör Aspose.Slides på Linux‑servrar?**  
A: Absolut—Aspose.Slides för Java är plattformsoberoende och fungerar på alla operativsystem med en kompatibel JDK.

---

**Senast uppdaterad:** 2026-07-17  
**Testad med:** Aspose.Slides for Java 25.4 (JDK 16)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar pajdiagram i Java‑presentationer med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Mästra pajdiagram i Java med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Rotera diagramtexter i Java med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}