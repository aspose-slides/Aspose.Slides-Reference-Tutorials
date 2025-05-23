---
"description": "Skapa ringdiagram med anpassade hålstorlekar i Java Slides med Aspose.Slides för Java. Steg-för-steg-guide med källkod för anpassning av diagram."
"linktitle": "Hål i ringdiagram i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Hål i ringdiagram i Java-bilder"
"url": "/sv/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hål i ringdiagram i Java-bilder


## Introduktion till ringdiagram med ett hål i Java-bilder

I den här handledningen guidar vi dig genom att skapa ett ringdiagram med ett hål med hjälp av Aspose.Slides för Java. Den här steg-för-steg-guiden guidar dig genom processen med exempel på källkod.

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner det från [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/).

## Steg 1: Importera de nödvändiga biblioteken

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

// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
```

## Steg 3: Skapa ringdiagrammet

```java
try {
    // Skapa ett ringdiagram på den första bilden
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ange storleken på hålet i ringdiagrammet (i procent)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Spara presentationen på disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Kassera presentationsobjektet
    if (presentation != null) presentation.dispose();
}
```

## Steg 4: Kör koden

Kör Java-koden i din IDE eller textredigerare för att skapa ett ringdiagram med en angiven hålstorlek. Se till att ersätta `"Your Document Directory"` med den faktiska sökvägen där du vill spara presentationen.

## Komplett källkod för Doughnut Chart Hole i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
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

I den här handledningen lärde du dig hur man skapar ett ringdiagram med ett hål med Aspose.Slides för Java. Du kan anpassa hålets storlek genom att justera `setDoughnutHoleSize` metodparameter.

## Vanliga frågor

### Hur kan jag ändra färgen på diagramsegmenten?

För att ändra färgen på diagramsegmenten kan du använda `setDataPointsInLegend` metod på `IChart` objektet och ange önskad färg för varje datapunkt.

### Kan jag lägga till etiketter i segmenten i ringdiagrammet?

Ja, du kan lägga till etiketter i ringdiagramsegmenten med hjälp av `setDataPointsLabelValue` metod på `IChart` objekt.

### Är det möjligt att lägga till en titel i diagrammet?

Visst! Du kan lägga till en titel till diagrammet med hjälp av `setTitle` metod på `IChart` objektet och ange önskad titeltext.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}