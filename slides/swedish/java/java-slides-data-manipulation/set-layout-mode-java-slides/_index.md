---
"description": "Lär dig hur du ställer in layoutlägen för Java-bilder med Aspose.Slides. Anpassa diagrampositionering och storlek i den här steg-för-steg-guiden med källkod."
"linktitle": "Ställ in layoutläge i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställ in layoutläge i Java-presentationer"
"url": "/sv/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in layoutläge i Java-presentationer


## Introduktion till att ställa in layoutläge i Java-presentationer

den här handledningen lär vi oss hur man ställer in layoutläget för ett diagram i Java-bilder med hjälp av Aspose.Slides för Java. Layoutläget avgör diagrammets position och storlek i bilden.

## Förkunskapskrav

Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en presentation

Först måste vi skapa en ny presentation.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till en bild och ett diagram

Nästa steg är att lägga till en bild och ett diagram. I det här exemplet skapar vi ett klustrat stapeldiagram.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Steg 3: Ställ in diagramlayout

Nu ska vi ställa in layouten för diagrammet. Vi justerar diagrammets position och storlek i bilden med hjälp av `setX`, `setY`, `setWidth`, `setHeight` metoder. Dessutom kommer vi att ställa in `LayoutTargetType` för att bestämma layoutläget.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

det här exemplet har vi ställt in diagrammet så att det har sin layoutmåltyp som "Inre", vilket innebär att det kommer att placeras och storleksändras i förhållande till bildens inre område.

## Steg 4: Spara presentationen

Slutligen, låt oss spara presentationen med inställningarna för diagramlayout.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Komplett källkod för att ange layoutläge i Java Slides

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

I den här handledningen har vi lärt oss hur man ställer in layoutläget för ett diagram i Java-bilder med hjälp av Aspose.Slides för Java. Du kan anpassa diagrammets position och storlek efter dina specifika behov genom att justera värdena i `setX`, `setY`, `setWidth`, `setHeight`och `setLayoutTargetType` metoder. Detta ger dig kontroll över placeringen av diagram i dina bilder.

## Vanliga frågor

### Hur ändrar jag layoutläget för ett diagram i Aspose.Slides för Java?

För att ändra layoutläget för ett diagram i Aspose.Slides för Java kan du använda `setLayoutTargetType` metod på diagrammets plottområde. Du kan ställa in den till antingen `LayoutTargetType.Inner` eller `LayoutTargetType.Outer` beroende på önskad layout.

### Kan jag anpassa diagrammets position och storlek i bilden?

Ja, du kan anpassa diagrammets position och storlek i bilden med hjälp av `setX`, `setY`, `setWidth`och `setHeight` metoder på diagrammets plottområde. Justera dessa värden för att placera och storlekssätta diagrammet efter dina behov.

### Var kan jag hitta mer information om Aspose.Slides för Java?

Du hittar mer information om Aspose.Slides för Java i [dokumentation](https://reference.aspose.com/slides/java/)Den innehåller detaljerade API-referenser och exempel som hjälper dig att arbeta effektivt med bilder och diagram i Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}