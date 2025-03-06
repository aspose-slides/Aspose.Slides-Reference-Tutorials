---
title: Lettertype-eigenschappen voor diagrammen in Java-dia's
linktitle: Lettertype-eigenschappen voor diagrammen in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Verbeter de eigenschappen van diagramlettertypen in Java-dia's met Aspose.Slides voor Java. Pas de lettergrootte, stijl en kleur aan voor indrukwekkende presentaties.
weight: 11
url: /nl/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lettertype-eigenschappen voor diagrammen in Java-dia's


## Inleiding tot lettertype-eigenschappen voor diagrammen in Java-dia's

Deze handleiding begeleidt u bij het instellen van lettertype-eigenschappen voor een diagram in Java Slides met behulp van Aspose.Slides. U kunt de lettergrootte en het uiterlijk van de diagramtekst aanpassen om de visuele aantrekkingskracht van uw presentaties te vergroten.

## Vereisten

 Zorg ervoor dat Aspose.Slides voor Java API in uw project is geïntegreerd voordat u begint. Als u dat nog niet heeft gedaan, kunt u deze downloaden via de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Stap 1: Maak een presentatie

Maak eerst een nieuwe presentatie met behulp van de volgende code:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Voeg een diagram toe

Laten we nu een geclusterd kolomdiagram aan uw presentatie toevoegen:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Hier voegen we een geclusterd kolomdiagram toe aan de eerste dia op coördinaten (100, 100) met een breedte van 500 eenheden en een hoogte van 400 eenheden.

## Stap 3: Pas lettertype-eigenschappen aan

Vervolgens passen we de lettertype-eigenschappen van het diagram aan. In dit voorbeeld stellen we de lettergrootte in op 20 voor alle diagramtekst:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Deze code stelt de lettergrootte in op 20 punten voor alle tekst in het diagram.

## Stap 4: Gegevenslabels weergeven

U kunt ook gegevenslabels in het diagram weergeven met behulp van de volgende code:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Met deze coderegel zijn gegevenslabels mogelijk voor de eerste reeks in het diagram, waarbij de waarden in de diagramkolommen worden weergegeven.

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie op met uw aangepaste diagramlettertype-eigenschappen:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Met deze code wordt de presentatie opgeslagen in de opgegeven map met de bestandsnaam 'FontPropertiesForChart.pptx'.

## Volledige broncode voor lettertype-eigenschappen voor diagrammen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de lettertype-eigenschappen voor een diagram in Java Slides kunt aanpassen met Aspose.Slides voor Java. U kunt deze technieken toepassen om de weergave van uw diagrammen en presentaties te verbeteren. Ontdek meer opties in de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Veelgestelde vragen

### Hoe kan ik de kleur van het lettertype wijzigen?

 Gebruik om de lettertypekleur voor diagramtekst te wijzigen`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , vervangen`Color.RED` met de gewenste kleur.

### Kan ik de lettertypestijl wijzigen (vet, cursief, etc.)?

 Ja, u kunt de lettertypestijl wijzigen. Gebruik`chart.getTextFormat().getPortionFormat().setFontBold(true);` om het lettertype vetgedrukt te maken. Op dezelfde manier kunt u gebruiken`setFontItalic(true)` om het cursief te maken.

### Hoe pas ik de lettertype-eigenschappen aan voor specifieke diagramelementen?

Als u lettertype-eigenschappen wilt aanpassen voor specifieke diagramelementen, zoals aslabels of legendatekst, kunt u toegang krijgen tot die elementen en hun lettertype-eigenschappen instellen met soortgelijke methoden als hierboven weergegeven.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
