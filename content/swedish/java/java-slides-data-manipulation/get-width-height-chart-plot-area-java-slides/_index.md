---
title: Få bredd och höjd från sjökortsområdet i Java Slides
linktitle: Få bredd och höjd från sjökortsområdet i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du hämtar dimensioner för diagramplottarea i Java Slides med Aspose.Slides för Java. Förbättra dina färdigheter i PowerPoint-automatisering.
type: docs
weight: 21
url: /sv/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## Introduktion

Diagram är ett kraftfullt sätt att visualisera data i PowerPoint-presentationer. Ibland kan du behöva känna till måtten på ett diagrams plotområde av olika anledningar, som att ändra storlek på eller flytta element i diagrammet. Den här guiden kommer att demonstrera hur man får fram bredden och höjden på tomtområdet med Java och Aspose.Slides för Java.

## Förutsättningar

 Innan vi dyker in i koden, se till att du har Aspose.Slides for Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från Asposes webbplats[här](https://releases.aspose.com/slides/java/).

## Steg 1: Konfigurera miljön

Se till att du har lagt till Aspose.Slides for Java-biblioteket i ditt Java-projekt. Du kan göra detta genom att inkludera biblioteket i ditt projekts beroenden eller genom att manuellt lägga till JAR-filen.

## Steg 2: Skapa en PowerPoint-presentation

Låt oss börja med att skapa en PowerPoint-presentation och lägga till en bild till den. Detta kommer att fungera som behållaren för vårt diagram.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Byta ut`"Your Document Directory"` med sökvägen till din dokumentkatalog.

## Steg 3: Lägga till ett diagram

Låt oss nu lägga till ett klustrat kolumndiagram till bilden. Vi kommer också att validera diagramlayouten.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Den här koden skapar ett klustrat kolumndiagram vid position (100, 100) med dimensioner (500, 350).

## Steg 4: Skaffa mått på tomtytan

För att hämta bredden och höjden på diagrammets plotarea kan vi använda följande kod:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Nu variablerna`x`, `y`, `w` , och`h` innehålla respektive värden för tomtområdets X-koordinat, Y-koordinat, bredd och höjd.

## Steg 5: Spara presentationen

Spara slutligen presentationen med diagrammet.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Se till att byta ut`"Chart_out.pptx"` med önskat utdatafilnamn.

## Komplett källkod för att få bredd och höjd från sjökortsområdet i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Spara presentationen med diagram
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här artikeln har vi behandlat hur du får bredden och höjden på ett diagrams plotområde i Java Slides med hjälp av Aspose.Slides för Java API. Denna information kan vara värdefull när du dynamiskt behöver justera layouten för dina diagram i PowerPoint-presentationer.

## FAQ's

### Hur kan jag ändra diagramtypen till något annat än klustrade kolumner?

 Du kan ändra diagramtypen genom att ersätta`ChartType.ClusteredColumn` med önskad diagramtypsuppräkning, som t.ex`ChartType.Line` eller`ChartType.Pie`.

### Kan jag ändra andra egenskaper i diagrammet?

Ja, du kan ändra olika egenskaper för diagrammet, såsom data, etiketter och formatering, med Aspose.Slides för Java API. Se dokumentationen för mer information.

### Är Aspose.Slides för Java lämplig för professionell PowerPoint-automatisering?

Ja, Aspose.Slides för Java är ett kraftfullt bibliotek för att automatisera PowerPoint-uppgifter i Java-applikationer. Den tillhandahåller omfattande funktioner för att arbeta med presentationer, bilder, former, diagram och mer.

### Hur kan jag lära mig mer om Aspose.Slides för Java?

 Du kan hitta omfattande dokumentation och exempel på dokumentationssidan för Aspose.Slides för Java[här](https://reference.aspose.com/slides/java/).
