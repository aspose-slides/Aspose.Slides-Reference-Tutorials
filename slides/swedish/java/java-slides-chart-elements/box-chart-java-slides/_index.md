---
"description": "Lär dig hur du skapar Boxdiagram i Java-presentationer med Aspose.Slides. Steg-för-steg-guide och källkod ingår för effektiv datavisualisering."
"linktitle": "Boxdiagram i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Boxdiagram i Java-presentationer"
"url": "/sv/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Boxdiagram i Java-presentationer


## Introduktion till Boxdiagram i Aspose.Slides för Java

den här handledningen går vi igenom processen att skapa ett boxdiagram med Aspose.Slides för Java. Boxdiagram är användbara för att visualisera statistiska data med olika kvartiler och extremvärden. Vi ger dig steg-för-steg-instruktioner tillsammans med källkod som hjälper dig att komma igång.

## Förkunskapskrav

Innan du börjar, se till att du har följande:

- Aspose.Slides för Java-biblioteket installerat och konfigurerat.
- En Java-utvecklingsmiljö konfigurerad.

## Steg 1: Initiera presentationen

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

I det här steget initierar vi ett presentationsobjekt med hjälp av sökvägen till en befintlig PowerPoint-fil ("test.pptx" i det här exemplet).

## Steg 2: Skapa låddiagrammet

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

I det här steget skapar vi en Boxdiagram-form på den första bilden i presentationen. Vi tar även bort alla befintliga kategorier och serier från diagrammet.

## Steg 3: Definiera kategorier

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

I det här steget definierar vi kategorierna för Boxdiagrammet. Vi använder `IChartDataWorkbook` att lägga till kategorier och märka dem därefter.

## Steg 4: Skapa serien

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Här skapar vi en BoxAndWhisker-serie för diagrammet och konfigurerar olika alternativ som kvartilmetod, medelvärdeslinje, medelvärdesmarkörer, innerpunkter och extrempunkter.

## Steg 5: Lägg till datapunkter

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

I det här steget lägger vi till datapunkter i BoxAndWhisker-serien. Dessa datapunkter representerar statistiska data för diagrammet.

## Steg 6: Spara presentationen

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Slutligen sparar vi presentationen med Boxdiagrammet till en ny PowerPoint-fil med namnet "BoxAndWhisker.pptx".

Grattis! Du har skapat ett Boxdiagram med Aspose.Slides för Java. Du kan anpassa diagrammet ytterligare genom att justera olika egenskaper och lägga till fler datapunkter efter behov.

## Komplett källkod för boxdiagram i Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

den här handledningen har vi lärt oss hur man skapar ett boxdiagram med hjälp av Aspose.Slides för Java. Boxdiagram är värdefulla verktyg för att visualisera statistiska data, inklusive kvartiler och extremvärden. Vi har tillhandahållit en steg-för-steg-guide tillsammans med källkod som hjälper dig att komma igång med att skapa boxdiagram i dina Java-applikationer.

## Vanliga frågor

### Hur kan jag ändra utseendet på boxdiagrammet?

Du kan anpassa utseendet på boxdiagrammet genom att ändra egenskaper som linjestilar, färger och teckensnitt. Se dokumentationen för Aspose.Slides för Java för mer information om anpassning av diagram.

### Kan jag lägga till ytterligare dataserier i boxdiagrammet?

Ja, du kan lägga till flera dataserier i Boxdiagrammet genom att skapa ytterligare `IChartSeries` objekt och lägga till datapunkter till dem.

### Vad betyder QuartileMethodType.Exclusive?

De `QuartileMethodType.Exclusive` Inställningen anger att kvartilberäkningarna ska göras med exklusivitetsmetoden. Du kan välja olika kvartilberäkningsmetoder beroende på dina data och krav.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}