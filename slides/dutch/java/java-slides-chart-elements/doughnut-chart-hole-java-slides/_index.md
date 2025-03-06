---
title: Ringdiagramgat in Java-dia's
linktitle: Ringdiagramgat in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Maak ringdiagrammen met aangepaste gatgroottes in Java-dia's met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode voor het aanpassen van diagrammen.
weight: 11
url: /nl/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ringdiagramgat in Java-dia's


## Inleiding tot ringdiagram met een gat in Java-dia's

In deze zelfstudie begeleiden we u bij het maken van een ringdiagram met een gat met behulp van Aspose.Slides voor Java. Deze stapsgewijze handleiding leidt u door het proces met broncodevoorbeelden.

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. Je kunt het downloaden van de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

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

// Maak een exemplaar van de presentatieklasse
Presentation presentation = new Presentation();
```

## Stap 3: Maak het ringdiagram

```java
try {
    // Maak een ringdiagram op de eerste dia
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Stel de grootte van het gat in het ringdiagram in (in percentage)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Sla de presentatie op schijf op
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Gooi het presentatieobject weg
    if (presentation != null) presentation.dispose();
}
```

## Stap 4: Voer de code uit

 Voer de Java-code uit in uw IDE- of teksteditor om een ringdiagram met een opgegeven gatgrootte te maken. Zorg ervoor dat u vervangt`"Your Document Directory"` met het daadwerkelijke pad waar u de presentatie wilt opslaan.

## Volledige broncode voor ringdiagramgat in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
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

 In deze zelfstudie hebt u geleerd hoe u een ringdiagram met een gat kunt maken met Aspose.Slides voor Java. U kunt de grootte van het gat aanpassen door de`setDoughnutHoleSize` methodeparameter.

## Veelgestelde vragen

### Hoe kan ik de kleur van de diagramsegmenten wijzigen?

 Om de kleur van de diagramsegmenten te wijzigen, kunt u de`setDataPointsInLegend` methode op de`IChart` object en stel de gewenste kleur in voor elk gegevenspunt.

### Kan ik labels toevoegen aan de ringdiagramsegmenten?

 Ja, u kunt labels aan de ringdiagramsegmenten toevoegen met behulp van de`setDataPointsLabelValue` methode op de`IChart` voorwerp.

### Is het mogelijk om een titel aan het diagram toe te voegen?

 Zeker! U kunt een titel aan het diagram toevoegen met behulp van de`setTitle` methode op de`IChart` object en het verstrekken van de gewenste titeltekst.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
