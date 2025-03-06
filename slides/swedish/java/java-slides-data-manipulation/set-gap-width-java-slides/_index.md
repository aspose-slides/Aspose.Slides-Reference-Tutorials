---
title: Ställ in Gap Width i Java Slides
linktitle: Ställ in Gap Width i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in Gap Width i Java Slides med Aspose.Slides för Java. Förbättra diagramgrafik för dina PowerPoint-presentationer.
weight: 21
url: /sv/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in Gap Width i Java Slides


## Introduktion till inställning av gapbredd i Aspose.Slides för Java

I den här handledningen kommer vi att guida dig genom processen att ställa in Gap Width för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Gap Width bestämmer avståndet mellan kolumnerna eller staplarna i ett diagram, så att du kan styra diagrammets visuella utseende.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat. Du kan ladda ner den från Asposes webbplats[här](https://releases.aspose.com/slides/java/).

## Steg-för-steg-guide

Följ dessa steg för att ställa in Gap Width i ett diagram med Aspose.Slides för Java:

### 1. Skapa en tom presentation

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Skapa en tom presentation
Presentation presentation = new Presentation();
```

### 2. Öppna den första bilden

```java
// Gå till den första bilden
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Lägg till ett diagram med standarddata

```java
// Lägg till ett diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Ställ in index för diagramdatablad

```java
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
```

### 5. Skaffa arbetsboken för diagramdata

```java
// Hämta arbetsbladet för diagramdata
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

// Fyller seriedatapunkter
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Ställ in gapbredden

```java
// Ställ in Gap Width-värdet
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Spara presentationen

```java
// Spara presentationen med diagrammet
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Komplett källkod för Set Gap Width i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar tom presentation
Presentation presentation = new Presentation();
// Få tillgång till första bilden
ISlide slide = presentation.getSlides().get_Item(0);
// Lägg till diagram med standarddata
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Ställa in index för diagramdatabladet
int defaultWorksheetIndex = 0;
// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Lägg till serier
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Lägg till Catrgories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Ta andra diagramserien
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Fyller nu på seriedata
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ställ in GapWidth-värdet
series.getParentSeriesGroup().setGapWidth(50);
// Spara presentationen med diagram
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Slutsats

I den här handledningen har du lärt dig hur du ställer in Gap Width för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Genom att justera gapbredden kan du kontrollera avståndet mellan kolumner eller staplar i ditt diagram, vilket förbättrar den visuella representationen av dina data.

## FAQ's

### Hur ändrar jag Gap Width-värdet?

 För att ändra gapbredden, använd`setGapWidth` metod på`ParentSeriesGroup`av diagramserien. I exemplet ställer vi in Gap Width till 50, men du kan justera detta värde till önskat avstånd.

### Kan jag anpassa andra diagramegenskaper?

Ja, Aspose.Slides för Java tillhandahåller omfattande möjligheter för diagramanpassning. Du kan ändra olika diagramegenskaper, såsom färger, etiketter, titlar och mer. Se API-referensen för detaljerad information om alternativ för diagramanpassning.

### Var kan jag hitta mer resurser och dokumentation?

 Du kan hitta omfattande dokumentation och ytterligare resurser på Aspose.Slides för Java på[Aspose hemsida](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
