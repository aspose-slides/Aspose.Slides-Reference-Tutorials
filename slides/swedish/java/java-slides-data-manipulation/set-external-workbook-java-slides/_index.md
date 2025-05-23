---
"description": "Lär dig hur du skapar externa arbetsböcker i Java Slides med Aspose.Slides för Java. Skapa dynamiska presentationer med Excel-dataintegration."
"linktitle": "Ställ in extern arbetsbok i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställ in extern arbetsbok i Java Slides"
"url": "/sv/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in extern arbetsbok i Java Slides


## Introduktion till att ställa in extern arbetsbok i Java-presentationer

den här handledningen ska vi utforska hur man skapar en extern arbetsbok i Java Slides med hjälp av Aspose.Slides. Du kommer att lära dig hur du skapar en PowerPoint-presentation med ett diagram som refererar till data från en extern Excel-arbetsbok. I slutet av den här guiden kommer du att ha en tydlig förståelse för hur du integrerar externa data i dina Java Slides-presentationer.

## Förkunskapskrav

Innan vi går in i implementeringen, se till att du har följande förutsättningar:

- Java Development Kit (JDK) installerat på ditt system.
- Aspose.Slides för Java-biblioteket har lagts till i ditt projekt.
- En Excel-arbetsbok med de data du vill referera till i din presentation.

## Steg 1: Skapa en ny presentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Vi börjar med att skapa en ny PowerPoint-presentation med hjälp av Aspose.Slides.

## Steg 2: Lägg till ett diagram

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Nästa steg är att infoga ett cirkeldiagram i presentationen. Du kan anpassa diagramtypen och positionen efter behov.

## Steg 3: Åtkomst till extern arbetsbok

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

För att komma åt den externa arbetsboken använder vi `setExternalWorkbook` metod och ange sökvägen till Excel-arbetsboken som innehåller data.

## Steg 4: Bind diagramdata

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Vi binder diagrammet till data från den externa arbetsboken genom att ange cellreferenser för serier och kategorier.

## Steg 5: Spara presentationen

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Slutligen sparar vi presentationen med den externa arbetsboksreferensen som en PowerPoint-fil.

## Komplett källkod för Set External Workbook i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen har vi lärt oss hur man skapar en extern arbetsbok i Java Slides med hjälp av Aspose.Slides. Du kan nu skapa presentationer som dynamiskt refererar till data från Excel-arbetsböcker, vilket förbättrar flexibiliteten och interaktiviteten hos dina bilder.

## Vanliga frågor

### Hur installerar jag Aspose.Slides för Java?

Aspose.Slides för Java kan installeras genom att lägga till biblioteket i ditt Java-projekt. Du kan ladda ner biblioteket från Asposes webbplats och följa installationsanvisningarna i dokumentationen.

### Kan jag använda olika diagramtyper med externa arbetsböcker?

Ja, du kan använda olika diagramtyper som stöds av Aspose.Slides och binda dem till data från externa arbetsböcker. Processen kan variera något beroende på vilken diagramtyp du väljer.

### Vad händer om datastrukturen i min externa arbetsbok ändras?

Om strukturen för din externa arbetsbok ändras kan du behöva uppdatera cellreferenserna i din Java-kod för att säkerställa att diagramdata förblir korrekta.

### Är Aspose.Slides kompatibel med de senaste Java-versionerna?

Aspose.Slides för Java uppdateras regelbundet för att säkerställa kompatibilitet med de senaste Java-versionerna. Se till att söka efter uppdateringar och använd den senaste versionen av biblioteket för optimal prestanda och kompatibilitet.

### Kan jag lägga till flera diagram som refererar till samma externa arbetsbok?

Ja, du kan lägga till flera diagram i din presentation, som alla refererar till samma externa arbetsbok. Upprepa bara stegen som beskrivs i den här handledningen för varje diagram du vill skapa.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}