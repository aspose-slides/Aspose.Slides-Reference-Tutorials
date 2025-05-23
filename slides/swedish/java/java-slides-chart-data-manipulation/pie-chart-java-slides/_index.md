---
"description": "Lär dig hur du skapar fantastiska cirkeldiagram i PowerPoint-presentationer med Aspose.Slides för Java. Steg-för-steg-guide med källkod för Java-utvecklare."
"linktitle": "Cirkeldiagram i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Cirkeldiagram i Java-presentationer"
"url": "/sv/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cirkeldiagram i Java-presentationer


## Introduktion till att skapa ett cirkeldiagram i Java Slides med hjälp av Aspose.Slides

I den här handledningen visar vi hur man skapar ett cirkeldiagram i en PowerPoint-presentation med Aspose.Slides för Java. Vi ger dig steg-för-steg-instruktioner och Java-källkod som hjälper dig att komma igång. Den här guiden förutsätter att du redan har konfigurerat din utvecklingsmiljö med Aspose.Slides för Java.

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Importera nödvändiga bibliotek

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Se till att importera nödvändiga klasser från Aspose.Slides-biblioteket.

## Steg 2: Initiera presentationen

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Instansiera presentationsklassen som representerar en PPTX-fil
Presentation presentation = new Presentation();
```

Skapa ett nytt presentationsobjekt som representerar din PowerPoint-fil. Ersätt `"Your Document Directory"` med den faktiska sökvägen där du vill spara presentationen.

## Steg 3: Lägg till en bild

```java
// Åtkomst till den första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```

Hämta den första bilden i presentationen där du vill lägga till cirkeldiagrammet.

## Steg 4: Lägg till ett cirkeldiagram

```java
// Lägg till ett cirkeldiagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Lägg till ett cirkeldiagram på bilden på den angivna positionen och storleken.

## Steg 5: Ange diagramtitel

```java
// Ange diagramtitel
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Ange en titel för cirkeldiagrammet. Du kan anpassa titeln efter behov.

## Steg 6: Anpassa diagramdata

```java
// Ställ in den första serien för att visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;

// Hämta diagramdataarbetsbladet
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Ta bort standardgenererade serier och kategorier
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Lägger till nya kategorier
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Lägger till nya serier
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Ifyllning av seriedata
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Anpassa diagramdata genom att lägga till kategorier och serier och ange deras värden. I det här exemplet har vi tre kategorier och en serie med motsvarande datapunkter.

## Steg 7: Anpassa cirkeldiagramsektorer

```java
// Ange sektorfärger
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Anpassa utseendet på varje sektor
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Anpassa sektorgränsen
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Anpassa andra sektorer på liknande sätt
```

Anpassa utseendet på varje sektor i cirkeldiagrammet. Du kan ändra färger, kantlinjer och andra visuella egenskaper.

## Steg 8: Anpassa dataetiketter

```java
// Anpassa dataetiketter
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Anpassa dataetiketter för andra datapunkter på liknande sätt
```

Anpassa dataetiketter för varje datapunkt i cirkeldiagrammet. Du kan styra vilka värden som visas i diagrammet.

## Steg 9: Visa utfästningslinjer

```java
// Visa utfyllnadslinjer för diagrammet
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Aktivera hänvisningslinjer för att koppla dataetiketter till motsvarande sektorer.

## Steg 10: Ställ in cirkeldiagrammets rotationsvinkel

```java
// Ställ in rotationsvinkeln för cirkeldiagramsektorer
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Ställ in rotationsvinkeln för cirkeldiagrammets sektorer. I det här exemplet ställer vi in den till 180 grader.

## Steg 11: Spara presentationen

```java
// Spara presentationen med cirkeldiagrammet
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Spara presentationen med cirkeldiagrammet i den angivna katalogen.

## Komplett källkod för cirkeldiagram i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instansiera presentationsklassen som representerar en PPTX-fil
Presentation presentation = new Presentation();
// Åtkomst till första bilden
ISlide slides = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Titel för sättningstabell
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ställ in första serien på Visa värden
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ta bort standardgenererade serier och kategorier
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Lägger till nya kategorier
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Lägger till nya serier
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Nu fyller seriedata
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Fungerar inte i den nya versionen
// Lägga till nya punkter och ställa in sektorfärg
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Ställa in sektorgräns
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Ställa in sektorgräns
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Ställa in sektorgräns
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Skapa anpassade etiketter för varje kategori för nya serier
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setVisaKategoriNamn(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Visar utfästningslinjer för diagrammet
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Ställa in rotationsvinkel för cirkeldiagramsektorer
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Spara presentation med diagram
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

Du har skapat ett cirkeldiagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan anpassa diagrammets utseende och dataetiketter efter dina specifika behov. Den här handledningen ger ett grundläggande exempel, och du kan ytterligare förbättra och anpassa dina diagram efter behov.

## Vanliga frågor

### Hur kan jag ändra färgerna på enskilda sektorer i cirkeldiagrammet?

För att ändra färgerna på enskilda sektorer i cirkeldiagrammet kan du anpassa fyllningsfärgen för varje datapunkt. I det medföljande kodexemplet visade vi hur man ställer in fyllningsfärgen för varje sektor med hjälp av `getSolidFillColor().setColor()` metod. Du kan ändra färgvärdena för att uppnå önskat utseende.

### Kan jag lägga till fler kategorier och dataserier i cirkeldiagrammet?

Ja, du kan lägga till ytterligare kategorier och dataserier i cirkeldiagrammet. För att göra detta kan du använda `getChartData().getCategories().add()` och `getChartData().getSeries().add()` metoder, som visas i exemplet. Ange helt enkelt lämpliga data och etiketter för de nya kategorierna och serierna för att utöka ditt diagram.

### Hur anpassar jag utseendet på dataetiketter?

Du kan anpassa utseendet på dataetiketter med hjälp av `getDataLabelFormat()` metod på varje datapunkts etikett. I exemplet visade vi hur man visar värdet på dataetiketter med hjälp av `getDataLabelFormat().setShowValue(true)`Du kan ytterligare anpassa dataetiketter genom att styra vilka värden som visas, visa förklaringsnycklar och justera andra formateringsalternativ.

### Kan jag ändra titeln på cirkeldiagrammet?

Ja, du kan ändra cirkeldiagrammets titel. I den medföljande koden ställer vi in diagrammets titel med hjälp av `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`Du kan ersätta `"Sample Title"` med önskad titeltext.

### Hur sparar jag den genererade presentationen med cirkeldiagrammet?

För att spara presentationen med cirkeldiagrammet, använd `presentation.save()` metod. Ange önskad sökväg och namn för filen tillsammans med det format du vill spara presentationen i. Till exempel:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Se till att ange rätt filsökväg och format.

### Kan jag skapa andra typer av diagram med Aspose.Slides för Java?

Ja, Aspose.Slides för Java stöder olika diagramtyper, inklusive stapeldiagram, linjediagram och mer. Du kan skapa olika typer av diagram genom att ändra `ChartType` när du lägger till ett diagram. Se dokumentationen för Aspose.Slides för mer information om hur du skapar olika typer av diagram.

### Hur kan jag hitta mer information och exempel på hur man arbetar med Aspose.Slides för Java?

För mer information, detaljerad dokumentation och ytterligare exempel kan du besöka [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/)Den tillhandahåller omfattande resurser som hjälper dig att använda biblioteket effektivt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}