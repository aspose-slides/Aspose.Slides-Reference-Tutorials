---
date: '2026-08-16'
description: Lär dig hur du lägger till doughnut charts i Java med Aspose.Slides.
  Denna steg‑för‑steg‑guide täcker Maven‑beroendeinstallation, diagramkonfiguration,
  färger, etiketter och sparande av PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Hur du lägger till doughnut charts i Java med Aspose.Slides. Följ
  den här guiden för att konfigurera Maven, anpassa färger, etiketter och generera
  PPTX‑filer.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Hur du lägger till doughnut chart i Java med Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Hur du lägger till doughnut chart i Java med Aspose.Slides
url: /sv/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man lägger till ett munkdiagram i Java med Aspose.Slides

## Introduktion

Att skapa ett **munkdiagram** programmässigt kan förvandla råa siffror till en iögonfallande visualisering som omedelbart berättar en historia. I Java gör **Aspose.Slides** den här processen enkel, så att du kan generera presentationsklara diagram utan att någonsin öppna PowerPoint. I den här handledningen lär du dig **hur man lägger till munkdiagram** i en PPTX‑fil steg för steg – från att konfigurera Maven‑beroendet för Aspose Slides till att anpassa serier, kategorier, färger och etiketter, och slutligen spara presentationen.

När du är klar med den här guiden kan du bädda in dynamiska munkdiagram i vilken PPTX‑fil som helst, perfekt för rapporter, instrumentpaneler eller automatiserade bildspel.

### Snabba svar
- **Vilket bibliotek används?** Aspose.Slides för Java  
- **Primär uppgift?** Lägg till ett munkdiagram i en PPTX‑fil  
- **Hur lägger man till biblioteket?** Använd Maven‑beroendet för Aspose Slides (eller Gradle)  
- **Minsta Java‑version?** JDK 16 eller högre  
- **Kan jag anpassa färger och etiketter?** Ja, API‑et ger full kontroll över formatering  

## Vad är ett munkdiagram och varför använda det?

Ett munkdiagram är en variant av ett pajdiagram med ett tomt centrum, vilket möjliggör att flera dataserier visas som koncentriska ringar. **Det visualiserar delar‑av‑en‑helhet över flera kategorier samtidigt som det behåller utrymme för ytterligare information i mitten.** Detta gör det idealiskt för att jämföra försäljning per region över flera kvartal, budgetfördelning mellan avdelningar eller någon situation där du behöver visa hierarkisk proportionell data.

## Varför använda Aspose.Slides för Java?

Du kan lägga till ett munkdiagram utan att installera Microsoft Office, och biblioteket hanterar **över 50 + in‑ och utdataformat** samtidigt som det bearbetar presentationer med mer än 500 bilder. Aspose.Slides levererar **upp till 3× snabbare rendering** jämfört med inbyggd Office‑automatisering på samma hårdvara, och det fungerar på Windows, Linux och macOS. Dessa kvantifierade fördelar innebär att du kan generera stora bildspel på huvudlösa servrar med förutsägbar prestanda.

## Förutsättningar

- **Nödvändiga bibliotek**  
  - Aspose.Slides för Java 25.4 eller senare (biblioteket som möjliggör att du kan lägga till munkdiagram).  

- **Miljö**  
  - JDK 16 eller högre installerat på din maskin.  
  - En IDE såsom IntelliJ IDEA, Eclipse eller NetBeans.  

- **Kunskap**  
  - Grundläggande Java‑syntax och objektorienterade koncept.  
  - Bekantskap med Maven eller Gradle för beroendehantering.  

## Maven‑beroende för Aspose Slides

Lägg till följande Maven‑beroende i din `pom.xml`. Detta är **maven aspose slides‑beroendet** du behöver för att dra in biblioteket i ditt projekt.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Om du föredrar Gradle, använd motsvarande kodsnutt nedan.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Du kan också ladda ner JAR‑filen direkt från den officiella releases‑sidan:  
[ Aspose.Slides för Java‑utgåvor ](https://releases.aspose.com/slides/java/)

### Skaffa en licens

För att ta bort utvärderingsvattenstämpeln och låsa upp hela funktionsuppsättningen:

- **Gratis provversion** – börja med en tillfällig licens.  
- **Tillfällig licens** – begär en från [Aspose‑webbplatsen](https://purchase.aspose.com/temporary-license/).  
- **Kommersiell licens** – köp för produktionsbruk.

Applicera licensen i din kod:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Implementeringsguide

### Initiera en presentation och lägg till ett munkdiagram

`Presentation` är Aspose.Slides‑klassen som representerar en PowerPoint‑presentation.  
Läs in en befintlig PPTX eller skapa ett nytt `Presentation`‑objekt, och lägg sedan till ett munkdiagram på den första bilden.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Konfigurera diagrammets data‑arbetsbok och rensa befintliga data

Arbetsboken är ett internt kalkylblad som lagrar diagrammets data.  
Hämta arbetsboken som stödjer diagrammet, och rensa sedan eventuella standardserier eller -kategorier så att du kan börja med en ren slate.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Lägg till serier i diagrammet

En serie representerar en samling datapunkter som plottas i diagrammet.  
Du kan lägga till upp till 15 serier. Varje serie kan anpassas – här sätter vi explosion, storlek på munkhålet och startvinkel för den första sektorn.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Lägg till kategorier och datapunkter

Kategorier är etiketter för varje datapunkt längs diagrammets axel.  
Skapa 15 kategorier och fyll varje serie med en datapunkt. Den sista serien får speciell etikettformatering.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Anpassa färger och datalabels

`FillType.Solid` anger en solid fyllningsfärg för diagrammets element.  
Ställ in en solid fyllningsfärg för varje serie och aktivera datalabels. För den sista serien ändrar vi även etikettens teckenfärg.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Spara presentationen

`save` skriver presentationen till en fil i valt format.  
Skriv den uppdaterade presentationen till disk i PPTX‑format, eller exportera till PDF om så önskas.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Vanliga problem och lösningar

- **Licens ej hittad** – Verifiera att sökvägen till `license.lic` är korrekt och att filen är läsbar.  
- **Diagrammet visas tomt** – Säkerställ att du rensade befintliga serier/kategorier innan du lade till nya.  
- **Fel färger** – Bekräfta att `FillType.Solid` är satt för både fyllnings‑ och linjeformat.  
- **Prestanda med många serier** – Begränsa antalet serier/kategorier eller återanvänd arbetsboks‑celler för att hålla minnesanvändningen under kontroll.  

## Vanliga frågor

**Q: Kan jag generera ett munkdiagram utan en befintlig PPTX‑fil?**  
A: Ja, instansiera `new Presentation()` för att börja från en tom bildsamling, och lägg sedan till ett diagram som visat ovan.

**Q: Stöder Aspose.Slides export till PDF?**  
A: Absolut. Efter att diagrammet skapats, anropa `pres.save("output.pdf", SaveFormat.Pdf);` för att få en PDF‑version av bilden.

**Q: Hur ändrar jag storleken på munkhålet?**  
A: Använd `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` där `value` ligger mellan 0 och 100.

**Q: Är det möjligt att lägga till datalabels för alla serier, inte bara den sista?**  
A: Ja, flytta blocket för etikett‑formatering utanför `if (i == ...)`‑villkoret och applicera det på varje `dataPoint`.

**Q: Vilka Java‑versioner stöds?**  
A: Aspose.Slides 25.4 stöder JDK 16 och nyare. Äldre JDK‑versioner kräver rätt klassificerare i Maven‑beroendet.

---

**Senast uppdaterad:** 2026-08-16  
**Testad med:** Aspose.Slides för Java 25.4 (jdk16‑klassificerare)  
**Författare:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hur man anpassar färger i pajdiagram i Java med Aspose.Slides – En komplett guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animera PowerPoint‑diagramkategorier med Aspose.Slides för Java | Steg‑för‑steg‑guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}