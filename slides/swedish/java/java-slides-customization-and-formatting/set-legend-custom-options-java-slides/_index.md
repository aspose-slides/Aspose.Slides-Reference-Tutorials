---
title: Ställ in anpassade förklaringsalternativ i Java Slides
linktitle: Ställ in anpassade förklaringsalternativ i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in anpassade förklaringsalternativ i Java Slides med Aspose.Slides för Java. Anpassa förklaringens position och storlek i dina PowerPoint-diagram.
type: docs
weight: 14
url: /sv/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

## Introduktion till att ställa in anpassade förklaringsalternativ i Java Slides

I den här självstudien kommer vi att visa hur man anpassar förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan ändra förklaringens position, storlek och andra attribut för att passa dina presentationsbehov.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Aspose.Slides för Java API installerat.
- Java utvecklingsmiljö inrättad.

## Steg 1: Importera nödvändiga klasser:

```java
// Importera Aspose.Slides för Java-klasser
import com.aspose.slides.*;
```

## Steg 2: Ange sökvägen till din dokumentkatalog:

```java
String dataDir = "Your Document Directory";
```

##  Steg 3: Skapa en instans av`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Steg 4: Lägg till en bild i presentationen:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Steg 5: Lägg till ett klustrat kolumndiagram till bilden:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Steg 6. Ställ in förklaringsegenskaper:

- Ställ in X-positionen för förklaringen (relativt diagrambredden):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Ställ in Y-positionen för förklaringen (relativt diagramhöjden):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Ställ in förklaringens bredd (relativt diagrambredden):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Ställ in höjden på förklaringen (relativt diagramhöjden):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Steg 7: Spara presentationen på disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Det är allt! Du har framgångsrikt anpassat förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java.

## Komplett källkod för Ange anpassade alternativ för förklaring i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation presentation = new Presentation();
try
{
	// Få referens till bilden
	ISlide slide = presentation.getSlides().get_Item(0);
	// Lägg till ett klustrat kolumndiagram på bilden
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Ställ in teckenegenskaper
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Skriv presentation till disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Slutsats

I den här handledningen lärde vi oss hur man anpassar förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Du kan ändra förklaringens position, storlek och andra attribut för att skapa visuellt tilltalande och informativa presentationer.

## FAQ's

## Hur kan jag ändra legendens position?

 För att ändra förklaringens position, använd`setX` och`setY` metoder för legendobjektet. Värdena anges i förhållande till diagrammets bredd och höjd.

## Hur kan jag justera legendens storlek?

 Du kan justera förklaringens storlek genom att använda`setWidth` och`setHeight` metoder för legendobjektet. Dessa värden är också relativa till diagrammets bredd och höjd.

## Kan jag anpassa andra förklaringsattribut?

Ja, du kan anpassa olika attribut för förklaringen, såsom teckensnitt, ram, bakgrundsfärg och mer. Utforska Aspose.Slides-dokumentationen för detaljerad information om hur du anpassar förklaringar ytterligare.