---
title: Beräkna formler i Java Slides
linktitle: Beräkna formler i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du beräknar formler i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide med källkod för dynamiska PowerPoint-presentationer.
type: docs
weight: 10
url: /sv/java/data-manipulation/calculate-formulas-java-slides/
---

## Introduktion till att beräkna formler i Java Slides med Aspose.Slides

I den här guiden kommer vi att visa hur man beräknar formler i Java Slides med hjälp av Aspose.Slides for Java API. Aspose.Slides är ett kraftfullt bibliotek för att arbeta med PowerPoint-presentationer, och det ger funktioner för att manipulera diagram och utföra formelberäkningar i bilder.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Java utvecklingsmiljö
-  Aspose.Slides för Java-biblioteket (Du kan ladda ner det från[här](https://releases.aspose.com/slides/java/)
- Grundläggande kunskaper i Java-programmering

## Steg 1: Skapa en ny presentation

Låt oss först skapa en ny PowerPoint-presentation och lägga till en bild till den. Vi kommer att arbeta med en enda bild i detta exempel.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett diagram till bilden

Låt oss nu lägga till ett klustrat kolumndiagram till bilden. Vi kommer att använda detta diagram för att demonstrera formelberäkningar.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Steg 3: Ställ in formler och värden

Därefter kommer vi att ställa in formler och värden för diagramdatacellerna med hjälp av Aspose.Slides API. Vi kommer att beräkna formlerna för dessa celler.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Ställ in formel för cell A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Ställ in värde för cell A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Ställ in formel för cell B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Ställ in formel för cell C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Ställ in formeln för cell A1 igen
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Steg 4: Spara presentationen

Slutligen, låt oss spara den modifierade presentationen med de beräknade formlerna.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Komplett källkod för att beräkna formler i Java Slides

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här guiden har vi lärt oss hur man beräknar formler i Java Slides med Aspose.Slides för Java. Vi skapade en ny presentation, lade till ett diagram i den, ställde in formler och värden för diagramdataceller och sparade presentationen med de beräknade formlerna.

## FAQ's

### Hur ställer jag in formler för diagramdataceller?

 Du kan ställa in formler för diagramdataceller med hjälp av`setFormula` metod av`IChartDataCell` i Aspose.Slides.

### Hur ställer jag in värden för diagramdataceller?

 Du kan ställa in värden för diagramdataceller med hjälp av`setValue` metod av`IChartDataCell` i Aspose.Slides.

### Hur beräknar jag formler i en arbetsbok?

 Du kan beräkna formler i en arbetsbok med hjälp av`calculateFormulas` metod av`IChartDataWorkbook` i Aspose.Slides.
