---
"description": "Leer hoe u aangepaste legenda-opties instelt in Java Slides met Aspose.Slides voor Java. Pas de positie en grootte van de legenda aan in uw PowerPoint-grafieken."
"linktitle": "Legenda-aangepaste opties instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Legenda-aangepaste opties instellen in Java-dia's"
"url": "/nl/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda-aangepaste opties instellen in Java-dia's


## Inleiding tot het instellen van aangepaste opties voor legenda's in Java-dia's

In deze tutorial laten we zien hoe je de legenda-eigenschappen van een grafiek in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. Je kunt de positie, grootte en andere kenmerken van de legenda aanpassen aan je presentatiebehoeften.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:

- Aspose.Slides voor Java API geïnstalleerd.
- Java-ontwikkelomgeving instellen.

## Stap 1: Importeer de benodigde klassen:

```java
// Aspose.Slides importeren voor Java-klassen
import com.aspose.slides.*;
```

## Stap 2: Geef het pad naar uw documentenmap op:

```java
String dataDir = "Your Document Directory";
```

## Stap 3: Maak een exemplaar van de `Presentation` klas:

```java
Presentation presentation = new Presentation();
```

## Stap 4: Voeg een dia toe aan de presentatie:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Stap 5: Voeg een geclusterde kolomgrafiek toe aan de dia:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Stap 6. Legenda-eigenschappen instellen:

- Stel de X-positie van de legenda in (relatief ten opzichte van de grafiekbreedte):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Stel de Y-positie van de legenda in (ten opzichte van de hoogte van de grafiek):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Stel de breedte van de legenda in (relatief ten opzichte van de grafiekbreedte):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Stel de hoogte van de legenda in (relatief ten opzichte van de grafiekhoogte):

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

Dat is alles! Je hebt de legenda-eigenschappen van een grafiek in een PowerPoint-presentatie succesvol aangepast met Aspose.Slides voor Java.

## Volledige broncode voor aangepaste opties voor het instellen van legenda's in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
try
{
	// Verkrijg een referentie van de dia
	ISlide slide = presentation.getSlides().get_Item(0);
	// Voeg een geclusterde kolomgrafiek toe aan de dia
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

In deze tutorial hebben we geleerd hoe je de legenda-eigenschappen van een grafiek in een PowerPoint-presentatie kunt aanpassen met Aspose.Slides voor Java. Je kunt de positie, grootte en andere kenmerken van de legenda aanpassen om visueel aantrekkelijke en informatieve presentaties te maken.

## Veelgestelde vragen

## Hoe kan ik de positie van de legenda wijzigen?

Om de positie van de legenda te veranderen, gebruikt u de `setX` En `setY` Methoden van het legenda-object. De waarden worden gespecificeerd ten opzichte van de breedte en hoogte van de grafiek.

## Hoe kan ik de grootte van de legenda aanpassen?

U kunt de grootte van de legenda aanpassen met behulp van de `setWidth` En `setHeight` Methoden van het legenda-object. Deze waarden zijn ook relatief ten opzichte van de breedte en hoogte van de grafiek.

## Kan ik andere legenda-attributen aanpassen?

Ja, u kunt verschillende kenmerken van de legenda aanpassen, zoals lettertype, rand, achtergrondkleur en meer. Raadpleeg de documentatie van Aspose.Slides voor gedetailleerde informatie over het verder aanpassen van legenda's.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}