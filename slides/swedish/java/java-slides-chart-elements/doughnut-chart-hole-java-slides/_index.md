---
title: Donut Chart Hål i Java Slides
linktitle: Donut Chart Hål i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Skapa donutdiagram med anpassade hålstorlekar i Java Slides med Aspose.Slides för Java. Steg-för-steg guide med källkod för diagramanpassning.
weight: 11
url: /sv/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till Donut Chart med ett hål i Java Slides

I den här handledningen kommer vi att guida dig genom att skapa ett munkdiagram med ett hål med Aspose.Slides för Java. Den här steg-för-steg-guiden leder dig genom processen med exempel på källkod.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner den från[Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/).

## Steg 1: Importera de obligatoriska biblioteken

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Steg 2: Initiera presentationen

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
```

## Steg 3: Skapa Donut-diagrammet

```java
try {
    // Skapa ett munkdiagram på den första bilden
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ställ in storleken på hålet i munkdiagrammet (i procent)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Spara presentationen på disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Kassera presentationsobjektet
    if (presentation != null) presentation.dispose();
}
```

## Steg 4: Kör koden

 Kör Java-koden i din IDE eller textredigerare för att skapa ett munkdiagram med en specificerad hålstorlek. Se till att byta ut`"Your Document Directory"` med den faktiska sökvägen där du vill spara presentationen.

## Komplett källkod för Donut Chart Hole i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Skriv presentation till disk
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

 I den här handledningen lärde du dig hur du skapar ett munkdiagram med ett hål med Aspose.Slides för Java. Du kan anpassa storleken på hålet genom att justera`setDoughnutHoleSize` metodparameter.

## FAQ's

### Hur kan jag ändra färgen på diagramsegmenten?

 För att ändra färgen på diagramsegmenten kan du använda`setDataPointsInLegend` metod på`IChart` objekt och ställ in önskad färg för varje datapunkt.

### Kan jag lägga till etiketter till segmenten i munkdiagrammet?

 Ja, du kan lägga till etiketter till segmenten i munkdiagrammet med hjälp av`setDataPointsLabelValue` metod på`IChart` objekt.

### Är det möjligt att lägga till en titel i diagrammet?

 Säkert! Du kan lägga till en titel till diagrammet med hjälp av`setTitle` metod på`IChart` objekt och tillhandahålla önskad titeltext.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
