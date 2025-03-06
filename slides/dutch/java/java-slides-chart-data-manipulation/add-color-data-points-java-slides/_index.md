---
title: Kleur toevoegen aan gegevenspunten in Java-dia's
linktitle: Kleur toevoegen aan gegevenspunten in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u kleur kunt toevoegen aan gegevenspunten in Java-dia's met behulp van Aspose.Slides voor Java.
weight: 10
url: /nl/java/chart-data-manipulation/add-color-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot het toevoegen van kleur aan gegevenspunten in Java-dia's

In deze zelfstudie laten we zien hoe u kleur kunt toevoegen aan gegevenspunten in Java-dia's met behulp van Aspose.Slides voor Java. Deze stapsgewijze handleiding bevat broncodevoorbeelden om u te helpen deze taak te verwezenlijken.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java-ontwikkelomgeving
- Aspose.Slides voor Java-bibliotheek

## Stap 1: Maak een nieuwe presentatie

Eerst maken we een nieuwe presentatie met Aspose.Slides voor Java. Deze presentatie zal dienen als container voor onze kaart.

```java
Presentation pres = new Presentation();
```

## Stap 2: Voeg een Sunburst-grafiek toe

Laten we nu een Sunburst-diagram aan de presentatie toevoegen. We specificeren het diagramtype, de positie en de grootte.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Stap 3: Toegang tot gegevenspunten

 Om gegevenspunten in het diagram te wijzigen, hebben we toegang nodig tot de`IChartDataPointCollection` voorwerp.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Stap 4: Gegevenspunten aanpassen

In deze stap passen we specifieke gegevenspunten aan. Hier veranderen we de kleur van datapunten en configureren we labelinstellingen.

```java
// Pas gegevenspunt 0 aan
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Gegevenspunt aanpassen 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie op met het aangepaste diagram.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Dat is het! U hebt met succes kleur toegevoegd aan specifieke gegevenspunten in een Java-dia met behulp van Aspose.Slides voor Java.

## Volledige broncode voor het toevoegen van kleur aan gegevenspunten in Java-dia's

```java
Presentation pres = new Presentation();
try
{
	// Het pad naar de documentenmap.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//TE DOEN
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u kleur kunt toevoegen aan gegevenspunten in Java-dia's met behulp van Aspose.Slides voor Java. U kunt uw grafieken en presentaties verder aanpassen aan uw specifieke vereisten.

## Veelgestelde vragen

### Hoe kan ik de kleur van andere gegevenspunten wijzigen?

Om de kleur van andere gegevenspunten te wijzigen, kunt u een vergelijkbare aanpak volgen als weergegeven in stap 4. Ga naar het gegevenspunt dat u wilt aanpassen en wijzig de kleur- en labelinstellingen ervan.

### Kan ik andere aspecten van het diagram aanpassen?

 Ja, u kunt verschillende aspecten van het diagram aanpassen, waaronder lettertypen, labels, titels en meer. Verwijs naar de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde aanpassingsmogelijkheden.

### Waar kan ik meer voorbeelden en documentatie vinden?

 Meer voorbeelden en gedetailleerde documentatie over het gebruik van Aspose.Slides voor Java vindt u op de website[Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/) website.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
