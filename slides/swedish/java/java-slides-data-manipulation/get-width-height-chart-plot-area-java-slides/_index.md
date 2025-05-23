---
"description": "Lär dig hur du hämtar diagramdiagramsdimensioner i Java Slides med hjälp av Aspose.Slides för Java. Förbättra dina PowerPoint-automatiseringsfärdigheter."
"linktitle": "Hämta bredd och höjd från diagrammets plottområde i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Hämta bredd och höjd från diagrammets plottområde i Java-bilder"
"url": "/sv/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hämta bredd och höjd från diagrammets plottområde i Java-bilder


## Introduktion

Diagram är ett kraftfullt sätt att visualisera data i PowerPoint-presentationer. Ibland kan du behöva veta måtten på ett diagrams plottområde av olika anledningar, till exempel för att ändra storlek eller flytta element i diagrammet. Den här guiden visar hur man får fram bredden och höjden på plottområdet med hjälp av Java och Aspose.Slides för Java.

## Förkunskapskrav

Innan vi går in på koden, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från Asposes webbplats. [här](https://releases.aspose.com/slides/java/).

## Steg 1: Konfigurera miljön

Se till att du har lagt till biblioteket Aspose.Slides för Java i ditt Java-projekt. Du kan göra detta genom att inkludera biblioteket i projektets beroenden eller genom att manuellt lägga till JAR-filen.

## Steg 2: Skapa en PowerPoint-presentation

Låt oss börja med att skapa en PowerPoint-presentation och lägga till en bild i den. Detta kommer att fungera som behållare för vårt diagram.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Ersätta `"Your Document Directory"` med sökvägen till din dokumentkatalog.

## Steg 3: Lägga till ett diagram

Nu ska vi lägga till ett klustrat stapeldiagram i bilden. Vi ska också validera diagramlayouten.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Den här koden skapar ett klustrat stapeldiagram vid position (100, 100) med dimensioner (500, 350).

## Steg 4: Hämta plottområdets dimensioner

För att hämta bredden och höjden på diagrammets plottområde kan vi använda följande kod:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Nu, variablerna `x`, `y`, `w`och `h` innehåller respektive värden för plottområdets X-koordinat, Y-koordinat, bredd och höjd.

## Steg 5: Spara presentationen

Spara slutligen presentationen med diagrammet.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Se till att byta ut `"Chart_out.pptx"` med ditt önskade utdatafilnamn.

## Komplett källkod för att hämta bredd och höjd från diagrammets plotta område i Java Slides

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
	// Spara presentation med diagram
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

den här artikeln har vi gått igenom hur man får fram bredden och höjden på ett diagrams plottarea i Java Slides med hjälp av Aspose.Slides för Java API. Denna information kan vara värdefull när du behöver dynamiskt justera layouten för dina diagram i PowerPoint-presentationer.

## Vanliga frågor

### Hur kan jag ändra diagramtypen till något annat än klustrade kolumner?

Du kan ändra diagramtypen genom att ersätta `ChartType.ClusteredColumn` med önskad uppräkning av diagramtyp, till exempel `ChartType.Line` eller `ChartType.Pie`.

### Kan jag ändra andra egenskaper i diagrammet?

Ja, du kan ändra olika egenskaper i diagrammet, till exempel data, etiketter och formatering, med hjälp av Aspose.Slides för Java API. Se dokumentationen för mer information.

### Är Aspose.Slides för Java lämpligt för professionell PowerPoint-automatisering?

Ja, Aspose.Slides för Java är ett kraftfullt bibliotek för att automatisera PowerPoint-uppgifter i Java-applikationer. Det erbjuder omfattande funktioner för att arbeta med presentationer, bilder, former, diagram och mer.

### Hur kan jag lära mig mer om Aspose.Slides för Java?

Du hittar omfattande dokumentation och exempel på dokumentationssidan för Aspose.Slides för Java. [här](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}