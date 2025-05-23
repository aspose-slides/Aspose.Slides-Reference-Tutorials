---
"description": "Verbeter PowerPoint-presentaties met aangepaste lettertypen, -grootten en -kleuren voor afzonderlijke legenda's in Java Slides met Aspose.Slides voor Java."
"linktitle": "Lettertype-eigenschappen voor individuele legenda's in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Lettertype-eigenschappen voor individuele legenda's in Java-dia's"
"url": "/nl/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lettertype-eigenschappen voor individuele legenda's in Java-dia's


## Inleiding tot lettertype-eigenschappen voor individuele legenda's in Java-dia's

In deze tutorial laten we zien hoe je lettertype-eigenschappen instelt voor een individuele legenda in Java Slides met behulp van Aspose.Slides voor Java. Door de lettertype-eigenschappen aan te passen, kun je je legenda's visueel aantrekkelijker en informatiever maken in je PowerPoint-presentaties.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek in uw project is geïntegreerd. U kunt deze downloaden van de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Stap 1: Presentatie initialiseren en grafiek toevoegen

Laten we beginnen met het initialiseren van een PowerPoint-presentatie en het toevoegen van een grafiek. In dit voorbeeld gebruiken we een geclusterde kolomgrafiek ter illustratie.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // De rest van de code komt hier
} finally {
    if (pres != null) pres.dispose();
}
```

Vervangen `"Your Document Directory"` met de werkelijke map waarin uw PowerPoint-document zich bevindt.

## Stap 2: Pas de lettertype-eigenschappen voor de legenda aan

Laten we nu de lettertype-eigenschappen voor een afzonderlijk legenda-item in de grafiek aanpassen. In dit voorbeeld richten we ons op het tweede legenda-item (index 1), maar u kunt de index naar eigen wens aanpassen.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Dit is wat elke regel code doet:

- `get_Item(1)` Haalt het tweede legenda-item op (index 1). U kunt de index wijzigen om naar een ander legenda-item te verwijzen.
- `setFontBold(NullableBool.True)` maakt het lettertype vet.
- `setFontHeight(20)` stelt de lettergrootte in op 20 punten.
- `setFontItalic(NullableBool.True)` maakt het lettertype cursief.
- `setFillType(FillType.Solid)` geeft aan dat de tekst in de legenda een effen vulling moet hebben.
- `getSolidFillColor().setColor(Color.BLUE)` stelt de vulkleur in op blauw. U kunt vervangen `Color.BLUE` met de door u gewenste kleur.

## Stap 3: De gewijzigde presentatie opslaan

Sla ten slotte de gewijzigde presentatie op in een nieuw bestand om uw wijzigingen te behouden.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Vervangen `"output.pptx"` met de door u gewenste uitvoerbestandsnaam.

Dat is alles! U hebt de lettertype-eigenschappen voor een afzonderlijk legenda-item in een Java Slides-presentatie succesvol aangepast met Aspose.Slides voor Java.

## Volledige broncode voor lettertype-eigenschappen voor individuele legenda's in Java-dia's

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

In deze tutorial hebben we geleerd hoe je de lettertype-eigenschappen voor een individuele legenda in Java Slides kunt aanpassen met Aspose.Slides voor Java. Door lettertypen, -groottes en -kleuren aan te passen, kun je de visuele aantrekkingskracht en helderheid van je PowerPoint-presentaties verbeteren.

## Veelgestelde vragen

### Hoe kan ik de kleur van het lettertype veranderen?

Om de kleur van het lettertype te veranderen, gebruik je `tf.getPortionFormat().getFontColor().setColor(yourColor)` in plaats van de vulkleur te veranderen. Vervangen `yourColor` met de gewenste letterkleur.

### Hoe wijzig ik andere legenda-eigenschappen?

kunt diverse andere eigenschappen van de legenda wijzigen, zoals positie, grootte en opmaak. Raadpleeg de documentatie van Aspose.Slides voor Java voor gedetailleerde informatie over het werken met legenda's.

### Kan ik deze wijzigingen toepassen op meerdere legenda-vermeldingen?

Ja, u kunt door de legenda-items heen lussen en deze wijzigingen op meerdere items toepassen door de index in `get_Item(index)` en de aanpassingscode herhalen.

Vergeet niet om het presentatieobject te verwijderen wanneer u klaar bent met het vrijgeven van bronnen:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}