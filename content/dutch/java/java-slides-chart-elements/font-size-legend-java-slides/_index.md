---
title: Legenda voor lettergrootte in Java-dia's
linktitle: Legenda voor lettergrootte in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Verbeter PowerPoint-presentaties met Aspose.Slides voor Java. Leer hoe u de lettergrootte van legenda's kunt aanpassen en meer in onze stapsgewijze handleiding.
type: docs
weight: 13
url: /nl/java/chart-elements/font-size-legend-java-slides/
---

## Inleiding tot de legenda van de lettergrootte in Java-dia's

In deze zelfstudie leert u hoe u de lettergrootte van de legenda in een PowerPoint-dia kunt aanpassen met Aspose.Slides voor Java. We zullen stapsgewijze instructies en broncode leveren om deze taak te volbrengen.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/slides/java/).

## Stap 1: Initialiseer de presentatie

Importeer eerst de benodigde klassen en initialiseer uw PowerPoint-presentatie.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Vervangen`"Your Document Directory"` met het daadwerkelijke pad naar uw PowerPoint-bestand.

## Stap 2: Voeg een diagram toe

Vervolgens voegen we een diagram aan de dia toe en stellen we de lettergrootte van de legenda in.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 In deze code maken we een geclusterd kolomdiagram op de eerste dia en stellen we de lettergrootte van de legendatekst in op 20 punten. U kunt de`setFontHeight`waarde om de lettergrootte indien nodig te wijzigen.

## Stap 3: Aswaarden aanpassen

Laten we nu de verticale aswaarden van het diagram aanpassen.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Hier stellen we de minimum- en maximumwaarden voor de verticale as in. U kunt de waarden aanpassen aan uw gegevensvereisten.

## Stap 4: Sla de presentatie op

Sla ten slotte de gewijzigde presentatie op in een nieuw bestand.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Deze code slaat de gewijzigde presentatie op als "output.pptx" in de opgegeven map.

## Volledige broncode voor de legenda van de lettergrootte in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

U hebt met succes de lettergrootte van de legenda in een Java PowerPoint-dia aangepast met Aspose.Slides voor Java. U kunt de mogelijkheden van Aspose.Slides verder verkennen om interactieve en visueel aantrekkelijke presentaties te maken.

## Veelgestelde vragen

### Hoe wijzig ik de lettergrootte van de legendatekst in een diagram?

Om de lettergrootte van de legendatekst in een diagram te wijzigen, kunt u de volgende code gebruiken:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 In deze code maken we een diagram en stellen we de lettergrootte van de legendatekst in op 20 punten. U kunt de`setFontHeight`waarde om de lettergrootte te wijzigen.

### Kan ik andere eigenschappen van de legenda in een diagram aanpassen?

Ja, u kunt verschillende eigenschappen van de legenda in een diagram aanpassen met Aspose.Slides. Enkele van de algemene eigenschappen die u kunt aanpassen, zijn onder meer tekstopmaak, positie, zichtbaarheid en meer. Om bijvoorbeeld de positie van de legenda te wijzigen, kunt u het volgende gebruiken:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Deze code zorgt ervoor dat de legenda onder aan het diagram verschijnt. Verken de Aspose.Slides-documentatie voor meer aanpassingsopties.

### Hoe stel ik minimum- en maximumwaarden in voor de verticale as in een diagram?

Om minimum- en maximumwaarden voor de verticale as in een diagram in te stellen, kunt u de volgende code gebruiken:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Hier schakelen we het automatisch schalen van de assen uit en specificeren we de minimum- en maximumwaarden voor de verticale as. Pas de waarden indien nodig aan voor uw diagramgegevens.

### Waar kan ik meer informatie en documentatie voor Aspose.Slides vinden?

Uitgebreide documentatie en API-referenties voor Aspose.Slides voor Java vindt u op de documentatiewebsite van Aspose. Bezoek[hier](https://reference.aspose.com/slides/java/) voor gedetailleerde informatie over het gebruik van de bibliotheek.