---
"description": "Leer hoe u kleur toevoegt aan datapunten in Java-dia's met Aspose.Slides voor Java."
"linktitle": "Voeg kleur toe aan datapunten in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Voeg kleur toe aan datapunten in Java-dia's"
"url": "/nl/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Voeg kleur toe aan datapunten in Java-dia's


## Inleiding tot het toevoegen van kleur aan datapunten in Java-dia's

In deze tutorial laten we zien hoe je kleur toevoegt aan datapunten in Java-dia's met Aspose.Slides voor Java. Deze stapsgewijze handleiding bevat broncodevoorbeelden om je hierbij te helpen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

- Java-ontwikkelomgeving
- Aspose.Slides voor Java-bibliotheek

## Stap 1: Een nieuwe presentatie maken

Eerst maken we een nieuwe presentatie met Aspose.Slides voor Java. Deze presentatie dient als container voor onze grafiek.

```java
Presentation pres = new Presentation();
```

## Stap 2: Voeg een Sunburst-grafiek toe

Laten we nu een Sunburst-grafiek aan de presentatie toevoegen. We specificeren het grafiektype, de positie en de grootte.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Stap 3: Toegang tot datapunten

Om de datapunten in de grafiek te wijzigen, moeten we toegang hebben tot de `IChartDataPointCollection` voorwerp.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Stap 4: Datapunten aanpassen

In deze stap passen we specifieke datapunten aan. We wijzigen de kleur van de datapunten en configureren de labelinstellingen.

```java
// Gegevenspunt 0 aanpassen
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Gegevenspunt 9 aanpassen
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Stap 5: Sla de presentatie op

Sla ten slotte de presentatie met de aangepaste grafiek op.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Dat is alles! Je hebt met succes kleur toegevoegd aan specifieke datapunten in een Java-dia met Aspose.Slides voor Java.

## Volledige broncode voor het toevoegen van kleur aan datapunten in Java-dia's

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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//TODO
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial heb je geleerd hoe je kleur toevoegt aan datapunten in Java-dia's met Aspose.Slides voor Java. Je kunt je grafieken en presentaties verder aanpassen aan je specifieke wensen.

## Veelgestelde vragen

### Hoe kan ik de kleur van andere datapunten wijzigen?

Als u de kleur van andere gegevenspunten wilt wijzigen, kunt u een soortgelijke aanpak volgen als in stap 4. Ga naar het gegevenspunt dat u wilt aanpassen en wijzig de kleur- en labelinstellingen.

### Kan ik andere aspecten van de grafiek aanpassen?

Ja, u kunt verschillende aspecten van de grafiek aanpassen, zoals lettertypen, labels, titels en meer. Raadpleeg de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde aanpassingsopties.

### Waar kan ik meer voorbeelden en documentatie vinden?

Meer voorbeelden en gedetailleerde documentatie over het gebruik van Aspose.Slides voor Java vindt u op de [Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/) website.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}