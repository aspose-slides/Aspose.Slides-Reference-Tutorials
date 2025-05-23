---
"description": "Lär dig skapa fantastiska diagram och hantera egenskaper i Java-bilder med Aspose.Slides. Steg-för-steg-guide med källkod för kraftfulla presentationer."
"linktitle": "Hantera egenskapsdiagram i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Hantera egenskapsdiagram i Java Slides"
"url": "/sv/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hantera egenskapsdiagram i Java Slides


## Introduktion till hantering av egenskaper och diagram i Java Slides med hjälp av Aspose.Slides

I den här handledningen ska vi utforska hur man hanterar egenskaper och skapar diagram i Java-bilder med hjälp av Aspose.Slides. Aspose.Slides är ett kraftfullt Java API för att arbeta med PowerPoint-presentationer. Vi går igenom processen steg för steg, inklusive exempel på källkod.

## Förkunskapskrav

Innan vi börjar, se till att du har Aspose.Slides-biblioteket för Java installerat och konfigurerat i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Lägga till ett diagram i en bild

Så här lägger du till ett diagram i en bild:

1. Importera de nödvändiga klasserna och skapa en instans av Presentation-klassen.

```java
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
```

2. Gå till den bild där du vill lägga till diagrammet. I det här exemplet går vi till den första bilden.

```java
// Åtkomst till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Lägg till ett diagram med standarddata. I det här fallet lägger vi till ett StackedColumn3D-diagram.

```java
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Data för inställningsdiagram

För att ställa in diagramdata måste vi skapa en arbetsbok för diagramdata och lägga till serier och kategorier. Följ dessa steg:

4. Ställ in index för diagrammets datablad.

```java
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
```

5. Hämta arbetsboken för diagramdata.

```java
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Lägg till serier i diagrammet. I det här exemplet lägger vi till två serier med namnet "Serie 1" och "Serie 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Lägg till kategorier i diagrammet. Här lägger vi till tre kategorier.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Ställa in egenskaper för 3D-rotation

Nu ska vi ställa in 3D-rotationsegenskaper för diagrammet:

8. Ställ in de rätvinkliga axlarna.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Ställ in rotationsvinklarna för X- och Y-axlarna. I det här exemplet roterar vi X med 40 grader och Y med 270 grader.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Ställ in djupprocenten till 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Ifyllning av seriedata

11. Ta den andra diagramserien och fyll den med datapunkter.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Fyll i seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Justera överlappning

12. Ställ in överlappningsvärdet för serier. Du kan till exempel ställa in det på 100 för ingen överlappning.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Spara presentationen

Slutligen, spara presentationen på disk.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Det var allt! Du har skapat ett staplat 3D-kolumndiagram med anpassade egenskaper med hjälp av Aspose.Slides i Java.

## Komplett källkod för att hantera egenskaper i diagram i Java-presentationer

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
// Åtkomst till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Lägg till serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Lägg till kategorier
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ange Rotation3D-egenskaper
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Ta den andra diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställ in OverLap-värdet
series.getParentSeriesGroup().setOverlap((byte) 100);
// Skriv presentation till disk
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen fördjupade vi oss i hur man hanterar egenskaper och skapar diagram i Java-bilder med hjälp av Aspose.Slides. Aspose.Slides är ett robust Java API som gör det möjligt för utvecklare att arbeta effektivt med PowerPoint-presentationer. Vi har gått igenom de viktigaste stegen och tillhandahållit exempel på källkod som vägleder dig genom processen.

## Vanliga frågor

### Hur kan jag ändra diagramtypen?

Du kan ändra diagramtypen genom att modifiera `ChartType` parametern när du lägger till diagrammet. Se dokumentationen för Aspose.Slides för tillgängliga diagramtyper.

### Kan jag anpassa diagrammets färger?

Ja, du kan anpassa diagramfärgerna genom att ställa in fyllningsegenskaperna för seriedatapunkter eller kategorier.

### Hur lägger jag till fler datapunkter i en serie?

Du kan lägga till fler datapunkter i en serie genom att använda `series.getDataPoints().addDataPointForBarSeries()` metod och anger cellen som innehåller datavärdet.

### Hur kan jag ställa in en annan rotationsvinkel?

För att ställa in en annan rotationsvinkel för X- och Y-axlarna, använd `chart.getRotation3D().setRotationX()` och `chart.getRotation3D().setRotationY()` med önskade vinkelvärden.

### Vilka andra 3D-egenskaper kan jag anpassa?

Du kan utforska andra 3D-egenskaper i diagrammet, såsom djup, perspektiv och ljussättning, genom att läsa dokumentationen för Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}