---
"description": "Lär dig hur du ställer in mellanrumsbredd i Java-presentationer med Aspose.Slides för Java. Förbättra diagramgrafik för dina PowerPoint-presentationer."
"linktitle": "Ställ in mellanrumsbredd i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställ in mellanrumsbredd i Java-bilder"
"url": "/sv/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in mellanrumsbredd i Java-bilder


## Introduktion till att ställa in mellanrumsbredd i Aspose.Slides för Java

I den här handledningen guidar vi dig genom processen att ställa in mellanrumsbredden för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Mellanrumsbredden avgör avståndet mellan kolumnerna eller staplarna i ett diagram, vilket gör att du kan styra diagrammets visuella utseende.

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat. Du kan ladda ner det från Asposes webbplats. [här](https://releases.aspose.com/slides/java/).

## Steg-för-steg-guide

Följ dessa steg för att ställa in mellanrumsbredden i ett diagram med Aspose.Slides för Java:

### 1. Skapa en tom presentation

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Skapa en tom presentation 
Presentation presentation = new Presentation();
```

### 2. Öppna den första bilden

```java
// Åtkomst till den första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Lägg till ett diagram med standarddata

```java
// Lägg till ett diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Ställ in index för diagramdatablad

```java
// Ställa in index för diagramdatablad
int defaultWorksheetIndex = 0;
```

### 5. Hämta arbetsboken för diagramdata

```java
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Lägg till serier i diagrammet

```java
// Lägg till serier i diagrammet
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Lägg till kategorier i diagrammet

```java
// Lägg till kategorier i diagrammet
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Fyll i seriedata

```java
// Fyll i seriedata
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Fylla i seriedatapunkter
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Ställ in mellanrumsbredden

```java
// Ställ in värdet för mellanrumsbredd
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Spara presentationen

```java
// Spara presentationen med diagrammet
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för att ställa in gap width i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar en tom presentation 
Presentation presentation = new Presentation();
// Åtkomst till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
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
// Ta den andra diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Nu fyller seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställ in GapWidth-värdet
series.getParentSeriesGroup().setGapWidth(50);
// Spara presentation med diagram
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen har du lärt dig hur du ställer in mellanrumsbredden för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Genom att justera mellanrumsbredden kan du kontrollera avståndet mellan kolumner eller staplar i diagrammet, vilket förbättrar den visuella representationen av dina data.

## Vanliga frågor

### Hur ändrar jag värdet för mellanrumsbredden?

För att ändra mellanrumsbredden, använd `setGapWidth` metod på `ParentSeriesGroup` av diagramserien. I det visade exemplet ställer vi in mellanrumsbredden till 50, men du kan justera detta värde till önskat avstånd.

### Kan jag anpassa andra diagramegenskaper?

Ja, Aspose.Slides för Java erbjuder omfattande möjligheter för anpassning av diagram. Du kan ändra olika diagramegenskaper, till exempel färger, etiketter, titlar med mera. Se API-referensen för detaljerad information om alternativ för anpassning av diagram.

### Var kan jag hitta fler resurser och dokumentation?

Du hittar omfattande dokumentation och ytterligare resurser om Aspose.Slides för Java på [Asposes webbplats](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}