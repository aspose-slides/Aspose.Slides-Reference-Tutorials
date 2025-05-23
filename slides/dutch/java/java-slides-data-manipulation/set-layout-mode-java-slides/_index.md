---
"description": "Leer hoe u lay-outmodi voor Java-dia's instelt met Aspose.Slides. Pas de positie en grootte van diagrammen aan in deze stapsgewijze handleiding met broncode."
"linktitle": "Lay-outmodus instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Lay-outmodus instellen in Java-dia's"
"url": "/nl/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lay-outmodus instellen in Java-dia's


## Inleiding tot de lay-outmodus in Java-dia's

In deze tutorial leren we hoe je de lay-outmodus voor een grafiek in Java-dia's instelt met Aspose.Slides voor Java. De lay-outmodus bepaalt de positie en grootte van de grafiek in de dia.

## Vereisten

Voordat we beginnen, zorg ervoor dat je de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd en ingesteld in je Java-project. Je kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Een presentatie maken

Eerst moeten we een nieuwe presentatie maken.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een dia en grafiek toe

Vervolgens voegen we er een dia en een grafiek aan toe. In dit voorbeeld maken we een geclusterde kolomgrafiek.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Stap 3: Stel de grafiekindeling in

Laten we nu de lay-out van de grafiek instellen. We passen de positie en grootte van de grafiek binnen de dia aan met behulp van de `setX`, `setY`, `setWidth`, `setHeight` methoden. Daarnaast zullen we de `LayoutTargetType` om de lay-outmodus te bepalen.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In dit voorbeeld hebben we het diagram ingesteld op het lay-outdoeltype 'Inner'. Dit betekent dat de positie en grootte van het diagram worden aangepast ten opzichte van het binnenste gebied van de dia.

## Stap 4: Sla de presentatie op

Ten slotte slaan we de presentatie op met de instellingen voor de grafiekindeling.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor de set-layoutmodus in Java-dia's

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

## Conclusie

In deze tutorial hebben we geleerd hoe je de lay-outmodus voor een grafiek in Java-dia's instelt met Aspose.Slides voor Java. Je kunt de positie en grootte van de grafiek aanpassen aan je specifieke wensen door de waarden in de `setX`, `setY`, `setWidth`, `setHeight`, En `setLayoutTargetType` methoden. Hiermee hebt u controle over de plaatsing van grafieken in uw dia's.

## Veelgestelde vragen

### Hoe wijzig ik de lay-outmodus voor een grafiek in Aspose.Slides voor Java?

Om de lay-outmodus voor een grafiek in Aspose.Slides voor Java te wijzigen, kunt u de `setLayoutTargetType` methode op het tekengebied van de grafiek. U kunt het instellen op `LayoutTargetType.Inner` of `LayoutTargetType.Outer` afhankelijk van de door u gewenste indeling.

### Kan ik de positie en de grootte van het diagram in de dia aanpassen?

Ja, u kunt de positie en de grootte van het diagram binnen de dia aanpassen met behulp van de `setX`, `setY`, `setWidth`, En `setHeight` Methoden op het tekengebied van de grafiek. Pas deze waarden aan om de grafiek naar wens te positioneren en te formatteren.

### Waar kan ik meer informatie vinden over Aspose.Slides voor Java?

Meer informatie over Aspose.Slides voor Java vindt u in de [documentatie](https://reference.aspose.com/slides/java/)Het bevat gedetailleerde API-referenties en voorbeelden waarmee u effectief met dia's en grafieken in Java kunt werken.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}