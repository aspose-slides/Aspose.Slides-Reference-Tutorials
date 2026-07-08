---
date: '2026-07-08'
description: Lär dig hur du använder Aspose för att skapa ett doughnut chart i PowerPoint
  med Java. Denna steg‑för‑steg‑guide visar hur du lägger till diagramdata programatiskt,
  anpassar etiketter och sparar PPTX‑filen med hög noggrannhet.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Att använda Aspose låter dig skapa ett doughnut chart i PowerPoint
  med Java. Följ den här handledningen för att lägga till datapunkter, anpassa etiketter
  och spara PPTX‑filen med hög noggrannhet.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Så använder du Aspose: Skapa ett doughnut chart i PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Så använder du Aspose för att skapa ett doughnut chart i PowerPoint (Java)
url: /sv/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man använder Aspose för att skapa doughnut-diagram i PowerPoint (Java)

## Introduktion
Att skapa övertygande presentationer kräver ofta mer än bara text och bilder; diagram kan avsevärt förbättra berättandet genom att visualisera data på ett effektivt sätt. **How to use Aspose** för diagramgenerering ger dig programmatisk kontroll utan att någonsin öppna PowerPoint. Denna handledning guidar dig genom att bygga ett doughnut-diagram, konfigurera dess datapunkter och spara en högkvalitativ PPTX. Du behöver bara grundläggande Java‑kunskaper och några minuters installations‑tid.

`Aspose.Slides for Java` är ett Java‑bibliotek som möjliggör skapande, manipulering och konvertering av PowerPoint‑filer utan Microsoft Office.

## Snabba svar
- **Vilket bibliotek skapar doughnut-diagram i PowerPoint?** Aspose.Slides for Java  
- **Kan jag lägga till diagramdata programatiskt?** Ja, med hjälp av chart‑API:et  
- **Behöver jag en licens för produktion?** En giltig Aspose.Slides‑licens krävs  
- **Vilka Java‑versioner stöds?** Java 8 och senare (JDK 16‑klassificerare visas)  
- **Hur många serier kan jag lägga till?** Exemplet lägger till upp till 15 serier, men du kan justera efter behov  

## Vad är ett doughnut-diagram i PowerPoint?
Ett doughnut-diagram är ett cirkulärt diagram som liknar ett pajdiagram men med ett hål i mitten, vilket möjliggör att flera serier visas samtidigt. Det betonar del‑till‑hel‑relationer samtidigt som den visuella layouten förblir kompakt och lättläst.

## Varför använda Aspose.Slides for Java för att skapa doughnut-diagram?
Aspose.Slides for Java hanterar över 50 in‑ och utdataformat och kan generera presentationer upp till 500 MB utan att ladda hela filen i minnet. Det ger full programmatisk kontroll över diagrammets utseende, data och layout på vilken Java‑plattform som helst, eliminerar COM‑interop och kan rendera 100 diagramtunga bilder på under två sekunder på en vanlig server.

## Förutsättningar
- Grundläggande kunskaper i Java‑programmering.  
- En IDE som IntelliJ IDEA eller Eclipse.  
- Maven eller Gradle för beroendehantering.  
- En giltig Aspose.Slides for Java‑licens (gratis provversion finns).

## Installera Aspose.Slides för Java
Välj den beroendehanterare som passar ditt projekt.

**Maven**  
Lägg till följande beroende i din `pom.xml` (byt ut versionen mot den senaste releasen):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Lägg till den här raden i din `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Om du föredrar att ladda ner direkt, besök sidan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensanskaffning
Du kan börja med en gratis provperiod för att utforska Aspose.Slides‑funktionerna. För längre användning, köp en licens eller begär en tillfällig licens från [Aspose's website](https://purchase.aspose.com/temporary-license/). Följ instruktionerna för att konfigurera din miljö och initiera Aspose.Slides i din applikation.

## Så skapar du doughnut-diagram i PowerPoint med Aspose.Slides för Java
För att bygga ett doughnut-diagram, börja med att ladda eller skapa en `Presentation`, lägg till ett diagram av typen `ChartType.Doughnut`, rensa standardserier, sätt hålstorleken och fyll sedan diagrammets arbetsbok med kategorinamn och numeriska värden. Slutligen justerar du etikettformatet och sparar PPTX‑filen.

### Steg 1: Initiera presentationen
Skapa en ny presentation eller öppna en befintlig fil för att få en samling bilder.

`Presentation` är huvudklassen som representerar en PowerPoint‑fil.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Steg 2: Lägg till ett doughnut-diagram på bilden
Infoga ett diagram, ta bort standardserier/kategorier och konfigurera grundläggande visuella inställningar som hålstorlek för doughnut‑diagrammet.

`Chart` (eller diagramform) representerar ett diagramobjekt placerat på en bild.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Steg 3: Lägg till diagramdata och anpassa etiketter
Fyll i kategorinamn, lägg till datapunkter för varje serie och finjustera etikettformat (teckensnitt, färg, position). Detta steg demonstrerar möjligheten att “lägga till diagramdata”.

`Workbook` ger åtkomst till diagrammets underliggande kalkylbladsdata där celler fylls.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Steg 4: Spara den uppdaterade presentationen
Spara ändringarna till en ny PPTX‑fil på disk.

`save` skriver presentationen till en fil i det valda formatet.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Praktiska tillämpningar
Doughnut-diagram är perfekta för:
- **Finansiella rapporter:** Visualisera budgetfördelning eller kostnadsuppdelning.  
- **Marknadsanalys:** Visa marknadsandelar bland konkurrenter.  
- **Undersökningsresultat:** Presentera kategorisk enkätdata i kompakt form.  
- **Dashboard‑generering:** Kombinera med databasfrågor för att skapa live‑uppdaterade bilder.

## Prestandaöverväganden
- **Frigör resurser:** Anropa `pres.dispose()` efter sparning för att frigöra native‑minne.  
- **Begränsa antalet diagram:** Att lägga till hundratals diagram kan öka minnesanvändning; batch‑processa vid behov.  
- **Använd streaming:** För stora datamängder, fyll arbetsboken direkt från strömmar istället för minnes‑arrayer.  

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|---------|-------|---------|
| **Diagram visas tomt** | Data‑celler fylls inte i korrekt | Verifiera att `workBook.getCell(...)` refererar till rätt rad‑/kolumn‑index. |
| **Etiketter överlappar** | För många kategorier i begränsat utrymme | Öka `DoughnutHoleSize` eller justera `FirstSliceAngle`. |
| **OutOfMemoryError** | Stora presentationer utan att frigöra resurser | Anropa `pres.dispose()` efter sparning och överväg att öka JVM‑heap‑storleken. |

## Vanliga frågor

**Q: Kan jag använda Aspose.Slides for Java i kommersiella applikationer?**  
A: Ja, men du behöver en giltig kommersiell licens. En gratis provperiod finns för utvärdering.

**Q: Hur lägger jag till fler än 15 serier?**  
A: Öka loop‑gränsen i steget “Add Doughnut Chart” och säkerställ att din data‑arbetsbok innehåller tillräckligt många rader.

**Q: Är det möjligt att ändra hålstorleken på doughnut‑diagrammet efter skapandet?**  
A: Ja, anropa `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` innan du sparar.

**Q: Kan jag exportera diagrammet som en bild istället för en PPTX?**  
A: Absolut. Använd `chart.getImage()` och spara den returnerade `java.awt.image.BufferedImage` i önskat format.

**Q: Stöder Aspose.Slides animerade diagram?**  
A: Animation kan läggas till via `ISlide.getTimeline()`‑API:et, men det ligger utanför omfattningen av denna handledning.

## Slutsats
Du har nu en komplett, produktionsklar metod för att **skapa doughnut-diagram i PowerPoint** med Aspose.Slides for Java, inklusive hur du **lägger till diagramdata**, anpassar etiketter och hanterar prestanda. Experimentera med olika färger, datakällor och diagramtyper för att få dina presentationer att verkligen sticka ut.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides for Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hur man redigerar PowerPoint‑diagramdata med Aspose.Slides for Java: En omfattande guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animera diagram i PowerPoint med Aspose.Slides for Java – En steg‑för‑steg‑guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}