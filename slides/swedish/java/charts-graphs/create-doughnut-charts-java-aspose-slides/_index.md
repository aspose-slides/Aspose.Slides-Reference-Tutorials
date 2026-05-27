---
date: '2026-03-07'
description: Lär dig hur du skapar ett ringdiagram i Java med Aspose.Slides. Denna
  steg‑för‑steg‑guide täcker installation av Maven‑beroendet för Aspose Slides, diagramkonfiguration
  och sparande av presentationer.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Skapa ringdiagram i Java med Aspose.Slides guide
url: /sv/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa Doughnut Chart Java med Aspose.Slides Guide

## Introduktion

Att skapa ett **doughnut chart** programatiskt kan förvandla råa siffror till en iögonfallande visualisering som omedelbart berättar en historia. I Java gör **Aspose.Slides** denna process enkel och låter dig generera presentationsklara diagram utan att någonsin öppna PowerPoint. I den här handledningen kommer du att lära dig hur du **skapar doughnut chart java** steg för steg – från att konfigurera Maven Aspose Slides‑beroendet till att anpassa serier, kategorier och slutligen spara presentationen.

När du har gått igenom guiden kommer du att kunna bädda in dynamiska doughnut-diagram i vilken PPTX‑fil som helst, perfekt för rapporter, instrumentpaneler eller automatiserade bildspel.

### Snabba svar
- **Vilket bibliotek används?** Aspose.Slides for Java  
- **Primär uppgift?** Skapa doughnut chart java i en PPTX‑fil  
- **Hur lägger man till biblioteket?** Använd Maven Aspose Slides‑beroendet (eller Gradle)  
- **Minsta Java‑version?** JDK 16 eller högre  
- **Kan jag anpassa färger och etiketter?** Ja, API‑et ger full kontroll över formatering  

## Vad är ett Doughnut Chart och varför använda det?

Ett doughnut chart är en variant av ett pajdiagram med ett tomt centrum, vilket gör det möjligt att visa flera dataserier i koncentriska ringar. Detta gör det idealiskt för att jämföra delar av en helhet över flera kategorier – tänk försäljning per region över flera kvartal eller budgetfördelning över avdelningar.

## Varför använda Aspose.Slides för Java?

- **Ingen Office‑installation krävs** – generera PPTX‑filer på vilken server som helst.  
- **Rik API** – full kontroll över diagramtyper, datapunkter och styling.  
- **Hög prestanda** – optimerad för stora presentationer.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS.

## Förutsättningar

- **Krävda bibliotek:**  
  - Aspose.Slides for Java version 25.4 eller senare.  

- **Miljöinställning:**  
  - JDK 16 eller högre.  
  - Din favoriteditor (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Kunskapsförutsättningar:**  
  - Grundläggande Java‑programmering.  
  - Bekantskap med Maven eller Gradle för beroendehantering.

## Maven Aspose Slides‑beroende

Lägg till följande Maven‑beroende i din `pom.xml`. Detta är **maven aspose slides dependency** som du behöver för att hämta biblioteket till ditt projekt.

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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Du kan också ladda ner JAR‑filen direkt från den officiella releasesidan:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Skaffa en licens

För att ta bort utvärderingsvattenstämpeln och låsa upp hela funktionsuppsättningen:

- **Gratis provperiod** – börja med en temporär licens.  
- **Temporär licens** – begär en från [Aspose‑webbplatsen](https://purchase.aspose.com/temporary-license/).  
- **Kommersiell licens** – köp för produktionsbruk.

Applicera licensen i din kod:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementeringsguide

### Initiering av Presentation och Tillägg av ett Doughnut Chart

Först, skapa eller läs in en presentation och lägg till ett doughnut chart på den första bilden.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurering av Diagrammets Dataarbetsbok och Rensning av Befintliga Data

Därefter, hämta arbetsboken som stödjer diagrammet och rensa eventuella standardserier eller -kategorier.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Lägg till Serier i Diagrammet

Nu kommer vi att lägga till upp till 15 serier. Varje serie kan anpassas – här sätter vi explosion, doughnut‑hålstorlek och första‑skivvinkel.

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

### Lägg till Kategorier och Datapunkter

Vi kommer att skapa 15 kategorier och fylla varje serie med en datapunkt. Den sista serien får speciell etikettformatering.

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

### Spara Presentationen

Slutligen, skriv den uppdaterade presentationen till disk.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Vanliga problem och lösningar

- **Licens ej hittad** – Verifiera att sökvägen till `license.lic` är korrekt och att filen är läsbar.  
- **Diagrammet visas tomt** – Se till att du rensade befintliga serier/kategorier innan du lade till nya.  
- **Fel färger** – Kontrollera att `FillType.Solid` är satt för både fyllnings- och linjeformat.  
- **Prestanda med många serier** – Begränsa antalet serier/kategorier eller återanvänd arbetsbokens celler.

## Vanliga frågor

**Q: Kan jag generera ett doughnut chart utan en befintlig PPTX‑fil?**  
A: Ja, skapa en `new Presentation()` för att börja med en tom bildsamling.

**Q: Stöder Aspose.Slides export till PDF?**  
A: Absolut. Efter att diagrammet skapats, anropa `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Hur ändrar jag storleken på doughnut‑hålet?**  
A: Använd `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` där värdet är 0‑100.

**Q: Är det möjligt att lägga till datalabels till alla serier, inte bara den sista?**  
A: Ja, flytta etikett‑formateringsblocket utanför `if (i == ...)`‑villkoret och applicera det på varje `dataPoint`.

**Q: Vilka Java‑versioner stöds?**  
A: Aspose.Slides 25.4 stöder JDK 16 och nyare. Äldre JDK‑versioner kräver rätt classifier.

---

**Senast uppdaterad:** 2026-03-07  
**Testat med:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}