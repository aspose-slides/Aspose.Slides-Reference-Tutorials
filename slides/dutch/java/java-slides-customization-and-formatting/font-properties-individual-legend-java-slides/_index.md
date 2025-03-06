---
title: Lettertype-eigenschappen voor individuele legenda in Java-dia's
linktitle: Lettertype-eigenschappen voor individuele legenda in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Verbeter PowerPoint-presentaties met aangepaste lettertypestijlen, -groottes en -kleuren voor individuele legenda's in Java Slides met Aspose.Slides voor Java.
weight: 12
url: /nl/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lettertype-eigenschappen voor individuele legenda in Java-dia's


## Inleiding tot lettertype-eigenschappen voor individuele legenda in Java-dia's

In deze zelfstudie onderzoeken we hoe u lettertype-eigenschappen kunt instellen voor een individuele legenda in Java Slides met behulp van Aspose.Slides voor Java. Door de lettertype-eigenschappen aan te passen, kunt u uw legenda's visueel aantrekkelijker en informatiever maken in uw PowerPoint-presentaties.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïntegreerd. Je kunt het downloaden van de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Stap 1: Initialiseer de presentatie en voeg een diagram toe

Laten we eerst beginnen met het initialiseren van een PowerPoint-presentatie en het toevoegen van een diagram eraan. In dit voorbeeld gebruiken we een geclusterd kolomdiagram als illustratie.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // De rest van de code komt hier te staan
} finally {
    if (pres != null) pres.dispose();
}
```

 Vervangen`"Your Document Directory"` met de daadwerkelijke map waarin uw PowerPoint-document zich bevindt.

## Stap 2: Pas lettertype-eigenschappen voor legenda aan

Laten we nu de lettertype-eigenschappen aanpassen voor een afzonderlijk legenda-item in het diagram. In dit voorbeeld targeten we de tweede legenda-invoer (index 1), maar u kunt de index aanpassen aan uw specifieke vereisten.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Dit is wat elke regel code doet:

- `get_Item(1)` haalt de tweede legenda-invoer op (index 1). U kunt de index wijzigen om een ander legenda-item te targeten.
- `setFontBold(NullableBool.True)` stelt het lettertype in op vet.
- `setFontHeight(20)` stelt de lettergrootte in op 20 punten.
- `setFontItalic(NullableBool.True)` stelt het lettertype in op cursief.
- `setFillType(FillType.Solid)` geeft aan dat de tekst van het legenda-item een effen vulling moet hebben.
- `getSolidFillColor().setColor(Color.BLUE)` stelt de vulkleur in op blauw. Je kunt vervangen`Color.BLUE` met uw gewenste kleur.

## Stap 3: Sla de aangepaste presentatie op

Sla ten slotte de gewijzigde presentatie op in een nieuw bestand om uw wijzigingen te behouden.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Vervangen`"output.pptx"` met de gewenste uitvoerbestandsnaam.

Dat is het! U hebt met succes de lettertype-eigenschappen voor een afzonderlijk legenda-item in een Java Slides-presentatie aangepast met Aspose.Slides voor Java.

## Volledige broncode voor lettertype-eigenschappen voor individuele legenda in Java-dia's

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de lettertype-eigenschappen voor een individuele legenda in Java Slides kunt aanpassen met Aspose.Slides voor Java. Door lettertypestijlen, -groottes en -kleuren aan te passen, kunt u de visuele aantrekkingskracht en helderheid van uw PowerPoint-presentaties verbeteren.

## Veelgestelde vragen

### Hoe kan ik de kleur van het lettertype wijzigen?

 Gebruik om de kleur van het lettertype te wijzigen`tf.getPortionFormat().getFontColor().setColor(yourColor)` in plaats van de vulkleur te wijzigen. Vervangen`yourColor` met de gewenste letterkleur.

### Hoe wijzig ik andere legenda-eigenschappen?

U kunt diverse andere eigenschappen van de legenda wijzigen, zoals positie, grootte en formaat. Raadpleeg de Aspose.Slides voor Java-documentatie voor gedetailleerde informatie over het werken met legenda's.

### Kan ik deze wijzigingen toepassen op meerdere legenda-items?

 Ja, u kunt legenda-items doorlopen en deze wijzigingen op meerdere items toepassen door de index aan te passen`get_Item(index)` en het herhalen van de aanpassingscode.

Vergeet niet het presentatieobject weg te gooien als u klaar bent met het vrijgeven van bronnen:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
