---
title: Stel aangepaste legenda-opties in Java-dia's in
linktitle: Stel aangepaste legenda-opties in Java-dia's in
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u aangepaste legenda-opties instelt in Java Slides met behulp van Aspose.Slides voor Java. Pas de positie en grootte van de legenda in uw PowerPoint-grafieken aan.
type: docs
weight: 14
url: /nl/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

## Inleiding tot het instellen van aangepaste opties voor legenda's in Java-dia's

In deze zelfstudie laten we zien hoe u de legenda-eigenschappen van een diagram in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. U kunt de positie, grootte en andere kenmerken van de legenda aanpassen aan uw presentatiebehoeften.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Aspose.Slides voor Java API geïnstalleerd.
- Java-ontwikkelomgeving opgezet.

## Stap 1: Importeer de benodigde klassen:

```java
// Importeer Aspose.Slides voor Java-klassen
import com.aspose.slides.*;
```

## Stap 2: Geef het pad naar uw documentmap op:

```java
String dataDir = "Your Document Directory";
```

##  Stap 3: Maak een exemplaar van het`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Stap 4: Voeg een dia toe aan de presentatie:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Stap 5: Voeg een geclusterd kolomdiagram toe aan de dia:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Stap 6. Legenda-eigenschappen instellen:

- Stel de X-positie van de legenda in (ten opzichte van de kaartbreedte):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Stel de Y-positie van de legenda in (ten opzichte van de kaarthoogte):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Stel de breedte van de legenda in (ten opzichte van de grafiekbreedte):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Stel de hoogte van de legenda in (ten opzichte van de diagramhoogte):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Stap 7: Sla de presentatie op schijf op:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Dat is het! U hebt met succes de legenda-eigenschappen van een diagram in een PowerPoint-presentatie aangepast met Aspose.Slides voor Java.

## Volledige broncode voor aangepaste opties voor het instellen van legenda's in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
try
{
	// Referentie van de dia opvragen
	ISlide slide = presentation.getSlides().get_Item(0);
	// Voeg een geclusterd kolomdiagram toe aan de dia
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Legenda-eigenschappen instellen
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Presentatie naar schijf schrijven
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Conclusie

In deze zelfstudie hebben we geleerd hoe u de legenda-eigenschappen van een diagram in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. U kunt de positie, grootte en andere kenmerken van de legenda wijzigen om visueel aantrekkelijke en informatieve presentaties te creëren.

## Veelgestelde vragen

## Hoe kan ik de positie van de legenda wijzigen?

 Om de positie van de legenda te wijzigen, gebruikt u de`setX` En`setY` methoden van het legendaobject. De waarden worden opgegeven ten opzichte van de breedte en hoogte van het diagram.

## Hoe kan ik de grootte van de legenda aanpassen?

 U kunt de grootte van de legenda aanpassen met behulp van de`setWidth` En`setHeight` methoden van het legendaobject. Deze waarden zijn ook relatief ten opzichte van de breedte en hoogte van het diagram.

## Kan ik andere legenda-attributen aanpassen?

Ja, u kunt verschillende kenmerken van de legenda aanpassen, zoals lettertype, rand, achtergrondkleur en meer. Verken de Aspose.Slides-documentatie voor gedetailleerde informatie over het verder aanpassen van legenda's.