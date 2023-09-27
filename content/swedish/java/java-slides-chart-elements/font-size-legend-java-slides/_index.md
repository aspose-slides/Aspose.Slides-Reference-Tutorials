---
title: Teckenstorleksförklaring i Java Slides
linktitle: Teckenstorleksförklaring i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Förbättra PowerPoint-presentationer med Aspose.Slides för Java. Lär dig hur du anpassar teckenstorlekar för legender och mer i vår steg-för-steg-guide.
type: docs
weight: 13
url: /sv/java/chart-elements/font-size-legend-java-slides/
---

## Introduktion till teckenstorleksförklaring i Java Slides

I den här handledningen kommer du att lära dig hur du anpassar teckenstorleken för förklaringen i en PowerPoint-bild med Aspose.Slides för Java. Vi kommer att tillhandahålla steg-för-steg-instruktioner och källkod för att utföra denna uppgift.

## Förutsättningar

 Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Initiera presentationen

Importera först de nödvändiga klasserna och initiera din PowerPoint-presentation.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Byta ut`"Your Document Directory"` med den faktiska sökvägen till din PowerPoint-fil.

## Steg 2: Lägg till ett diagram

Därefter kommer vi att lägga till ett diagram på bilden och ställa in teckenstorleken för förklaringen.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 I den här koden skapar vi ett klustrade kolumndiagram på den första bilden och ställer in teckenstorleken på förklaringstexten till 20 punkter. Du kan justera`setFontHeight`värde för att ändra teckenstorleken efter behov.

## Steg 3: Anpassa axelvärden

Låt oss nu anpassa de vertikala axelvärdena i diagrammet.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Här ställer vi in minimi- och maxvärden för den vertikala axeln. Du kan ändra värdena enligt dina datakrav.

## Steg 4: Spara presentationen

Slutligen, spara den ändrade presentationen till en ny fil.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Denna kod sparar den modifierade presentationen som "output.pptx" i den angivna katalogen.

## Komplett källkod för teckenstorleksförklaring i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

Du har framgångsrikt anpassat teckenstorleken för förklaringen i en Java PowerPoint-bild med Aspose.Slides för Java. Du kan ytterligare utforska funktionerna i Aspose.Slides för att skapa interaktiva och visuellt tilltalande presentationer.

## FAQ's

### Hur ändrar jag teckenstorleken på förklaringstexten i ett diagram?

För att ändra teckenstorleken på förklaringstexten i ett diagram kan du använda följande kod:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 I den här koden skapar vi ett diagram och ställer in teckenstorleken på förklaringstexten till 20 punkter. Du kan justera`setFontHeight`värde för att ändra teckenstorleken.

### Kan jag anpassa andra egenskaper för förklaringen i ett diagram?

Ja, du kan anpassa olika egenskaper för förklaringen i ett diagram med Aspose.Slides. Några av de vanliga egenskaperna du kan anpassa inkluderar textformatering, position, synlighet och mer. Till exempel, för att ändra förklaringens position kan du använda:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Den här koden gör att förklaringen visas längst ned i diagrammet. Utforska Aspose.Slides-dokumentationen för fler anpassningsalternativ.

### Hur ställer jag in lägsta och högsta värden för den vertikala axeln i ett diagram?

För att ställa in lägsta och högsta värden för den vertikala axeln i ett diagram kan du använda följande kod:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Här inaktiverar vi automatisk axelskalning och anger minimi- och maxvärden för den vertikala axeln. Justera värdena efter behov för dina diagramdata.

### Var kan jag hitta mer information och dokumentation för Aspose.Slides?

Du kan hitta omfattande dokumentation och API-referenser för Aspose.Slides för Java på Aspose-dokumentationswebbplatsen. Besök[här](https://reference.aspose.com/slides/java/) för detaljerad information om hur du använder biblioteket.