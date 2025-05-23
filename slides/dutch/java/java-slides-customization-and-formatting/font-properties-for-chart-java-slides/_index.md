---
"description": "Verbeter de eigenschappen van het grafieklettertype in Java-dia's met Aspose.Slides voor Java. Pas de lettergrootte, -stijl en -kleur aan voor indrukwekkende presentaties."
"linktitle": "Lettertype-eigenschappen voor diagrammen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Lettertype-eigenschappen voor diagrammen in Java-dia's"
"url": "/nl/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lettertype-eigenschappen voor diagrammen in Java-dia's


## Inleiding tot lettertype-eigenschappen voor grafieken in Java-dia's

Deze handleiding begeleidt u bij het instellen van lettertype-eigenschappen voor een grafiek in Java Slides met behulp van Aspose.Slides. U kunt de lettergrootte en de weergave van de grafiektekst aanpassen om de visuele aantrekkingskracht van uw presentaties te vergroten.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat Aspose.Slides voor Java API in uw project is geïntegreerd. Als u dit nog niet hebt gedaan, kunt u het downloaden via de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Stap 1: Een presentatie maken

Maak eerst een nieuwe presentatie met behulp van de volgende code:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Stap 2: Een grafiek toevoegen

Laten we nu een geclusterde kolomgrafiek aan uw presentatie toevoegen:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Hier voegen we een geclusterde kolomgrafiek toe aan de eerste dia op de coördinaten (100, 100) met een breedte van 500 eenheden en een hoogte van 400 eenheden.

## Stap 3: Lettertype-eigenschappen aanpassen

Vervolgens passen we de lettertype-eigenschappen van de grafiek aan. In dit voorbeeld stellen we de lettergrootte in op 20 voor alle tekst in de grafiek:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Met deze code wordt de lettergrootte voor alle tekst in de grafiek ingesteld op 20 punten.

## Stap 4: Gegevenslabels weergeven

U kunt ook gegevenslabels op de grafiek weergeven met behulp van de volgende code:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Met deze coderegel worden gegevenslabels voor de eerste reeks in het diagram ingeschakeld en worden de waarden in de kolommen van het diagram weergegeven.

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie op met de eigenschappen van uw aangepaste grafieklettertype:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Deze code slaat de presentatie op in de opgegeven directory met de bestandsnaam "FontPropertiesForChart.pptx."

## Volledige broncode voor lettertype-eigenschappen voor grafieken in Java-dia's

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

In deze tutorial heb je geleerd hoe je lettertype-eigenschappen voor een grafiek in Java Slides kunt aanpassen met Aspose.Slides voor Java. Je kunt deze technieken toepassen om de weergave van je grafieken en presentaties te verbeteren. Ontdek meer opties in de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Veelgestelde vragen

### Hoe kan ik de kleur van het lettertype veranderen?

Om de kleur van het lettertype voor de grafiektekst te wijzigen, gebruikt u `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, ter vervanging van `Color.RED` met de gewenste kleur.

### Kan ik het lettertype wijzigen (vet, cursief, enz.)?

Ja, u kunt het lettertype wijzigen. Gebruik `chart.getTextFormat().getPortionFormat().setFontBold(true);` om het lettertype vet te maken. U kunt ook `setFontItalic(true)` om het cursief te maken.

### Hoe pas ik de lettertype-eigenschappen aan voor specifieke grafiekelementen?

Als u de lettertype-eigenschappen voor specifieke grafiekelementen, zoals aslabels of legendatekst, wilt aanpassen, kunt u de desbetreffende elementen openen en de lettertype-eigenschappen instellen met behulp van vergelijkbare methoden als hierboven weergegeven.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}