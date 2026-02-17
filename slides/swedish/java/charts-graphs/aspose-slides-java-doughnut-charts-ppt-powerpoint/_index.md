---
date: '2026-02-17'
description: Lär dig hur du skapar ett munkdiagram i PowerPoint med Aspose.Slides
  för Java och lägger till diagramdata programatiskt. Följ enkla steg och kodexempel.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Skapa donutdiagram i PowerPoint med Aspose.Slides för Java
url: /sv/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

 >}}

Now ensure we didn't miss any markdown formatting.

We need to keep code block placeholders unchanged.

Also ensure we keep the table formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa munkdiagram i PowerPoint med Aspose.Slides för Java

## Introduction
Att skapa övertygande presentationer kräver ofta mer än bara text och bilder; diagram kan avsevärt förbättra berättandet genom att visualisera data på ett effektivt sätt. Många utvecklare har dock svårt att programatiskt integrera dynamiska diagramfunktioner i PowerPoint‑filer. Denna handledning visar hur du **skapar munkdiagram i PowerPoint** med Aspose.Slides för Java – ett kraftfullt verktyg som kombinerar flexibilitet och användarvänlighet.

**What You'll Learn:**
- Hur du initierar en presentation med Aspose.Slides för Java
- En steg‑för‑steg‑guide för att lägga till ett munkdiagram i dina bilder
- Konfigurera datapunkter och anpassa etikettens egenskaper
- Spara den modifierade presentationen med hög noggrannhet

Låt oss utforska hur du kan utnyttja dessa funktioner för att förbättra dina presentationer. Innan vi börjar, se till att du är bekant med grundläggande Java‑programmeringskoncept.

## Quick Answers
- **Vilket bibliotek skapar munkdiagram i PowerPoint?** Aspose.Slides för Java
- **Kan jag lägga till diagramdatapunkter programatiskt?** Ja, med hjälp av diagram‑API:et
- **Behöver jag en licens för produktion?** En giltig Aspose.Slides‑licens krävs
- **Vilka Java‑versioner stöds?** Java 8 och senare (JDK 16‑klassificerare visas)
- **Hur många serier kan jag lägga till?** Exemplet lägger till upp till 15 serier, men du kan justera efter behov

## What is a doughnut chart in PowerPoint?
Ett munkdiagram är en variant av ett cirkeldiagram med ett hål i mitten, vilket gör att du kan visa flera dataserier på ett kompakt och visuellt tilltalande sätt. Det är idealiskt för att visa del‑till‑hel‑förhållanden samtidigt som designen hålls ren.

## Why use Aspose.Slides for Java to create doughnut charts?
- **Full kontroll** över diagrammets utseende, data och layout utan att öppna PowerPoint
- **Ingen COM‑interoperabilitet** – fungerar på alla plattformar som stödjer Java
- **Hög prestanda** för att generera stora presentationer eller integrera med webbtjänster
- **Rich customization** såsom utsprängning, hålstorlek, segmentvinklar och etikettformatering

## Prerequisites
- Grundläggande kunskaper i Java‑programmering.
- En IDE som IntelliJ IDEA eller Eclipse.
- Maven eller Gradle för beroendehantering.
- En giltig Aspose.Slides för Java‑licens (gratis provversion finns).

## Setting Up Aspose.Slides for Java
Välj den beroendehanterare som passar ditt projekt.

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

Om du föredrar att ladda ner direkt, besök sidan [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) .

### License Acquisition
Du kan börja med en gratis provversion för att utforska Aspose.Slides‑funktionerna. För längre användning, köp en licens eller begär en tillfällig licens från [Aspose's website](https://purchase.aspose.com/temporary-license/). Följ de instruktioner som ges för att konfigurera din miljö och initiera Aspose.Slides i din applikation.

## How to create doughnut chart PowerPoint using Aspose.Slides for Java
Nedan följer en komplett steg‑för‑steg‑guide. Varje kodblock förklaras precis innan det, så du vet exakt vad som händer.

### Step 1: Initialize the presentation
Först, läs in en befintlig PPTX eller skapa en ny. Detta förbereder bildsamlingen för vidare ändringar.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Step 2: Add a doughnut chart to the slide
Vi lägger till diagramformen, rensar eventuella standardserier/kategorier och sätter grundläggande visuella egenskaper.

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

### Step 3: Add chart data points and customize labels
Här fyller vi i kategorier, lägger till datapunkter för varje serie och finjusterar etikettens utseende. Det är här nyckelordet **add chart data points** kommer in i bilden.

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

### Step 4: Save the updated presentation
Slutligen sparas ändringarna till en ny PPTX‑fil.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Finansiella rapporter:** Visualisera budgetfördelning eller kostnadsuppdelning.
- **Marknadsanalys:** Visa marknadsandelar bland konkurrenter.
- **Undersökningsresultat:** Presentera kategorisk enkätdata i kompakt form.
- **Dashboard‑generering:** Kombinera med databasfrågor för att skapa live‑uppdaterade bilder.

## Performance Considerations
- **Frigör resurser:** Anropa `pres.dispose()` när du är klar för att frigöra native‑minne.
- **Begränsa antalet diagram:** Att lägga till hundratals diagram kan öka minnesanvändning; batch‑processa vid behov.
- **Använd streaming:** För enorma datamängder, fyll arbetsboken direkt från strömmar istället för minnes‑arrayer.

## Common Issues and Solutions
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Diagram visas tomt** | Dataceller är inte korrekt fyllda | Verifiera att `workBook.getCell(...)` refererar till rätt rad‑/kolumnindex. |
| **Etiketter överlappar** | För många kategorier i begränsat utrymme | Öka `DoughnutHoleSize` eller justera `FirstSliceAngle`. |
| **OutOfMemoryError** | Stora presentationer utan att frigöra resurser | Anropa `pres.dispose()` efter sparning och överväg att öka JVM:s heap‑storlek. |

## Frequently Asked Questions

**Q: Kan jag använda Aspose.Slides för Java i kommersiella applikationer?**  
A: Ja, men du behöver en giltig kommersiell licens. En gratis provversion finns för utvärdering.

**Q: Hur lägger jag till mer än 15 serier?**  
A: Öka loop‑gränsen i steget “Add Doughnut Chart” och säkerställ att din dataarbetsbok har tillräckligt många rader.

**Q: Är det möjligt att ändra munkens hålstorlek efter skapandet?**  
A: Ja, anropa `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` när som helst före sparning.

**Q: Kan jag exportera diagrammet som en bild istället för en PPTX?**  
A: Absolut. Använd `chart.getImage()` och spara den returnerade `java.awt.image.BufferedImage` i önskat format.

**Q: Stöder Aspose.Slides animerade diagram?**  
A: Animation kan läggas till via `ISlide.getTimeline()`‑API:et, men det ligger utanför denna handlednings omfattning.

## Conclusion
Du har nu en komplett, produktionsklar metod för att **skapa munkdiagram i PowerPoint**‑filer med Aspose.Slides för Java, inklusive hur du **lägger till diagramdatapunkter**, anpassar etiketter och hanterar prestandaöverväganden. Experimentera med olika färger, datakällor och diagramtyper för att få dina presentationer att verkligen sticka ut.

---

**Senast uppdaterad:** 2026-02-17  
**Testat med:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}