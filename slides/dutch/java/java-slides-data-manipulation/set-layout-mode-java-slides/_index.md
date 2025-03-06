---
title: Stel de lay-outmodus in Java-dia's in
linktitle: Stel de lay-outmodus in Java-dia's in
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de lay-outmodi voor Java-dia's instelt met Aspose.Slides. Pas de positionering en grootte van diagrammen aan in deze stapsgewijze handleiding met broncode.
weight: 23
url: /nl/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot het instellen van de lay-outmodus in Java-dia's

In deze zelfstudie leren we hoe u de lay-outmodus voor een diagram in Java-dia's kunt instellen met behulp van Aspose.Slides voor Java. De lay-outmodus bepaalt de positionering en grootte van het diagram binnen de dia.

## Vereisten

 Voordat we beginnen, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Maak een presentatie

Eerst moeten we een nieuwe presentatie maken.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Stap 2: Voeg een dia en grafiek toe

Vervolgens voegen we er een dia en een diagram aan toe. In dit voorbeeld maken we een geclusterd kolomdiagram.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Stap 3: Stel de diagramindeling in

 Laten we nu de lay-out voor het diagram instellen. We passen de positie en grootte van het diagram binnen de dia aan met behulp van de`setX`, `setY`, `setWidth`, `setHeight` methoden. Daarnaast stellen we de`LayoutTargetType` om de lay-outmodus te bepalen.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In dit voorbeeld hebben we het lay-outdoeltype van het diagram ingesteld op 'Binnen', wat betekent dat het wordt gepositioneerd en gedimensioneerd ten opzichte van het binnengebied van de dia.

## Stap 4: Sla de presentatie op

Laten we ten slotte de presentatie opslaan met de instellingen voor de diagramindeling.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor de lay-outmodus instellen in Java-dia's

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

 In deze zelfstudie hebben we geleerd hoe u de lay-outmodus voor een diagram in Java-dia's kunt instellen met behulp van Aspose.Slides voor Java. U kunt de positie en grootte van het diagram aanpassen aan uw specifieke vereisten door de waarden in het diagram aan te passen`setX`, `setY`, `setWidth`, `setHeight` , En`setLayoutTargetType`methoden. Dit geeft u controle over de plaatsing van diagrammen in uw dia's.

## Veelgestelde vragen

### Hoe wijzig ik de lay-outmodus voor een diagram in Aspose.Slides voor Java?

 Om de lay-outmodus voor een diagram in Aspose.Slides voor Java te wijzigen, kunt u de`setLayoutTargetType` methode op het plotgebied van de kaart. Je kunt het op beide instellen`LayoutTargetType.Inner` of`LayoutTargetType.Outer` afhankelijk van uw gewenste indeling.

### Kan ik de positie en grootte van het diagram binnen de dia aanpassen?

 Ja, u kunt de positie en grootte van het diagram binnen de dia aanpassen met behulp van de`setX`, `setY`, `setWidth` , En`setHeight` methoden in het plotgebied van de kaart. Pas deze waarden aan om de grafiek volgens uw vereisten te positioneren en te vergroten.

### Waar kan ik meer informatie vinden over Aspose.Slides voor Java?

 Meer informatie over Aspose.Slides voor Java vindt u in de[documentatie](https://reference.aspose.com/slides/java/). Het bevat gedetailleerde API-referenties en voorbeelden om u te helpen effectief met dia's en grafieken te werken in Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
