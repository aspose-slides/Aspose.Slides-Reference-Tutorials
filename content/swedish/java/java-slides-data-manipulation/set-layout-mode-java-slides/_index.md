---
title: Ställ in layoutläge i Java Slides
linktitle: Ställ in layoutläge i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in layoutlägen för Java-bilder med Aspose.Slides. Anpassa diagrampositionering och storlek i denna steg-för-steg-guide med källkod.
type: docs
weight: 23
url: /sv/java/data-manipulation/set-layout-mode-java-slides/
---

## Introduktion till Set Layout Mode i Java Slides

I den här handledningen kommer vi att lära oss hur du ställer in layoutläget för ett diagram i Java-bilder med Aspose.Slides för Java. Layoutläget bestämmer placeringen och storleken på diagrammet i bilden.

## Förutsättningar

 Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en presentation

Först måste vi skapa en ny presentation.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till en bild och ett diagram

Därefter lägger vi till en bild och ett diagram till den. I det här exemplet skapar vi ett klustrat kolumndiagram.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Steg 3: Ställ in diagramlayout

 Låt oss nu ställa in layouten för diagrammet. Vi kommer att justera positionen och storleken på diagrammet i bilden med hjälp av`setX`, `setY`, `setWidth`, `setHeight` metoder. Dessutom kommer vi att ställa in`LayoutTargetType` för att bestämma layoutläget.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

I det här exemplet har vi ställt in diagrammet så att dess layoutmåltyp är "Inre", vilket betyder att den kommer att placeras och dimensioneras i förhållande till det inre området av bilden.

## Steg 4: Spara presentationen

Slutligen, låt oss spara presentationen med diagramlayoutinställningarna.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Komplett källkod för Set Layout Mode i Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

 I den här handledningen har vi lärt oss hur man ställer in layoutläget för ett diagram i Java-bilder med Aspose.Slides för Java. Du kan anpassa diagrammets position och storlek enligt dina specifika krav genom att justera värdena i`setX`, `setY`, `setWidth`, `setHeight` , och`setLayoutTargetType`metoder. Detta ger dig kontroll över placeringen av diagram i dina bilder.

## FAQ's

### Hur ändrar jag layoutläget för ett diagram i Aspose.Slides för Java?

 För att ändra layoutläget för ett diagram i Aspose.Slides för Java kan du använda`setLayoutTargetType` metod på diagrammets plotarea. Du kan ställa in den på antingen`LayoutTargetType.Inner` eller`LayoutTargetType.Outer` beroende på önskad layout.

### Kan jag anpassa positionen och storleken på diagrammet i bilden?

 Ja, du kan anpassa positionen och storleken på diagrammet i bilden genom att använda`setX`, `setY`, `setWidth` , och`setHeight` metoder på diagrammets plotarea. Justera dessa värden för att placera och dimensionera diagrammet enligt dina krav.

### Var kan jag hitta mer information om Aspose.Slides för Java?

 Du kan hitta mer information om Aspose.Slides för Java i[dokumentation](https://reference.aspose.com/slides/java/). Den innehåller detaljerade API-referenser och exempel som hjälper dig att arbeta med bilder och diagram effektivt i Java.