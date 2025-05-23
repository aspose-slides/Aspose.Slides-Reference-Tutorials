---
"description": "Lär dig hur du ställer in anpassade förklaringsalternativ i Java Slides med Aspose.Slides för Java. Anpassa förklaringens position och storlek i dina PowerPoint-diagram."
"linktitle": "Ange anpassade alternativ för förklaring i Java-presentationer"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ange anpassade alternativ för förklaring i Java-presentationer"
"url": "/sv/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ange anpassade alternativ för förklaring i Java-presentationer


## Introduktion till att ange anpassade alternativ för förklaring i Java-presentationer

den här handledningen visar vi hur du anpassar förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med hjälp av Aspose.Slides för Java. Du kan ändra förklaringens position, storlek och andra attribut för att passa dina presentationsbehov.

## Förkunskapskrav

Innan du börjar, se till att du har följande:

- Aspose.Slides för Java API installerat.
- Java-utvecklingsmiljö konfigurerad.

## Steg 1: Importera nödvändiga klasser:

```java
// Importera Aspose.Slides för Java-klasser
import com.aspose.slides.*;
```

## Steg 2: Ange sökvägen till din dokumentkatalog:

```java
String dataDir = "Your Document Directory";
```

## Steg 3: Skapa en instans av `Presentation` klass:

```java
Presentation presentation = new Presentation();
```

## Steg 4: Lägg till en bild i presentationen:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Steg 5: Lägg till ett klustrat stapeldiagram på bilden:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Steg 6. Ange förklaringsegenskaper:

- Ställ in X-positionen för förklaringen (relativt till diagrammets bredd):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Ställ in Y-positionen för förklaringen (i förhållande till diagrammets höjd):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Ange bredden på förklaringen (i förhållande till diagrammets bredd):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Ställ in höjden på förklaringen (i förhållande till diagrammets höjd):

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

Det var allt! Du har framgångsrikt anpassat förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med Aspose.Slides för Java.

## Komplett källkod för anpassade alternativ för ange förklaring i Java-bilder

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation presentation = new Presentation();
try
{
	// Hämta referens till bilden
	ISlide slide = presentation.getSlides().get_Item(0);
	// Lägg till ett klustrat stapeldiagram på bilden
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Ange förklaringsegenskaper
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

I den här handledningen lärde vi oss hur man anpassar förklaringsegenskaperna för ett diagram i en PowerPoint-presentation med hjälp av Aspose.Slides för Java. Du kan ändra förklaringens position, storlek och andra attribut för att skapa visuellt tilltalande och informativa presentationer.

## Vanliga frågor

## Hur kan jag ändra förklaringens position?

För att ändra förklaringens position, använd `setX` och `setY` metoder för legendobjektet. Värdena anges i förhållande till diagrammets bredd och höjd.

## Hur kan jag justera storleken på förklaringen?

Du kan justera storleken på förklaringen med hjälp av `setWidth` och `setHeight` metoder för legendobjektet. Dessa värden är också relativa till diagrammets bredd och höjd.

## Kan jag anpassa andra förklaringsattribut?

Ja, du kan anpassa olika attribut för förklaringen, till exempel teckensnitt, kantlinje, bakgrundsfärg med mera. Utforska Aspose.Slides-dokumentationen för detaljerad information om hur du anpassar förklaringar ytterligare.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}