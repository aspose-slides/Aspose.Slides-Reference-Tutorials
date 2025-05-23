---
"description": "Maak ringdiagrammen met aangepaste gatgroottes in Java Slides met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor het aanpassen van de grafiek."
"linktitle": "Gat in de donutgrafiek in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Gat in de donutgrafiek in Java-dia's"
"url": "/nl/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gat in de donutgrafiek in Java-dia's


## Inleiding tot donutdiagram met gat in Java-dia's

In deze tutorial laten we je zien hoe je een ringdiagram met een gat maakt met Aspose.Slides voor Java. Deze stapsgewijze handleiding leidt je door het proces met broncodevoorbeelden.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt deze downloaden van de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

## Stap 1: Importeer de vereiste bibliotheken

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Stap 2: Initialiseer de presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
```

## Stap 3: Maak de donutgrafiek

```java
try {
    // Maak een donutdiagram op de eerste dia
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Stel de grootte van het gat in het ringdiagram in (in procenten)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Sla de presentatie op schijf op
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Gooi het presentatieobject weg
    if (presentation != null) presentation.dispose();
}
```

## Stap 4: Voer de code uit

Voer de Java-code uit in je IDE of teksteditor om een ringdiagram te maken met een opgegeven gatgrootte. Zorg ervoor dat je `"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.

## Volledige broncode voor het gat in een donutdiagram in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Presentatie naar schijf schrijven
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze tutorial heb je geleerd hoe je een ringdiagram met een gat maakt met Aspose.Slides voor Java. Je kunt de grootte van het gat aanpassen door de `setDoughnutHoleSize` methodeparameter.

## Veelgestelde vragen

### Hoe kan ik de kleur van de grafieksegmenten wijzigen?

Om de kleur van de diagramsegmenten te wijzigen, kunt u de `setDataPointsInLegend` methode op de `IChart` object en stel de gewenste kleur in voor elk gegevenspunt.

### Kan ik labels toevoegen aan de segmenten van het ringdiagram?

Ja, u kunt labels toevoegen aan de segmenten van het ringdiagram met behulp van de `setDataPointsLabelValue` methode op de `IChart` voorwerp.

### Is het mogelijk om een titel aan de grafiek toe te voegen?

Zeker! Je kunt een titel aan de grafiek toevoegen met behulp van de `setTitle` methode op de `IChart` object en geef de gewenste titeltekst op.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}