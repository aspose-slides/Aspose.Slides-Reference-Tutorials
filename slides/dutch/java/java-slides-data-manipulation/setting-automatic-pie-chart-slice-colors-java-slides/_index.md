---
"description": "Leer hoe u dynamische cirkeldiagrammen met automatische segmentkleuren maakt in Java PowerPoint-presentaties met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "Automatische kleuren voor cirkeldiagrammen instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Automatische kleuren voor cirkeldiagrammen instellen in Java-dia's"
"url": "/nl/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatische kleuren voor cirkeldiagrammen instellen in Java-dia's


## Inleiding tot het instellen van automatische kleuren voor cirkeldiagrammen in Java-dia's

In deze tutorial laten we zien hoe je een cirkeldiagram maakt in een PowerPoint-presentatie met Aspose.Slides voor Java en hoe je automatische cirkelkleuren instelt voor het diagram. We geven stapsgewijze instructies en broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden van de Aspose-website: [Download Aspose.Slides voor Java](https://releases.aspose.com/slides/java/).

## Stap 1: Importeer vereiste pakketten

Eerst moet u de benodigde pakketten importeren uit Aspose.Slides voor Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Stap 2: Maak een PowerPoint-presentatie

Instantieer de `Presentation` klas om een nieuwe PowerPoint-presentatie te maken:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Stap 3: Een dia toevoegen

Ga naar de eerste dia van de presentatie en voeg er een grafiek aan toe met standaardgegevens:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Stap 4: Stel de grafiektitel in

Geef een titel op voor de grafiek:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Stap 5: Grafiekgegevens configureren

Stel de grafiek in om de waarden voor de eerste reeks weer te geven en configureer de grafiekgegevens:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Stap 6: Categorieën en series toevoegen

Nieuwe categorieën en reeksen toevoegen aan de grafiek:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Stap 7: Vul reeksgegevens in

Vul de reeksgegevens voor het cirkeldiagram in:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Stap 8: Verschillende segmentkleuren inschakelen

Schakel verschillende segmentkleuren in voor het cirkeldiagram:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Stap 9: Sla de presentatie op

Sla de presentatie ten slotte op in een PowerPoint-bestand:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor het instellen van automatische cirkeldiagram-segmentkleuren in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer presentatieklasse die PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
try
{
	// Toegang tot eerste dia
	ISlide slides = presentation.getSlides().get_Item(0);
	// Grafiek toevoegen met standaardgegevens
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Titel van de instellingsgrafiek
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Stel de eerste reeks in op Waarden weergeven
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// De index van het grafiekgegevensblad instellen
	int defaultWorksheetIndex = 0;
	// Het werkblad met grafiekgegevens ophalen
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Standaard gegenereerde series en categorieën verwijderen
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Nieuwe categorieën toevoegen
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Nieuwe series toevoegen
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Nu worden reeksgegevens ingevuld
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

U hebt met succes een cirkeldiagram gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java en het geconfigureerd voor automatische segmentkleuren. Deze stapsgewijze handleiding biedt u de benodigde broncode om dit te realiseren. U kunt het diagram en de presentatie naar wens verder aanpassen.

## Veelgestelde vragen

### Hoe kan ik de kleuren van afzonderlijke segmenten in het cirkeldiagram aanpassen?

Om de kleuren van de afzonderlijke segmenten in het cirkeldiagram aan te passen, kunt u de `getAutomaticSeriesColors` Methode om het standaardkleurenschema op te halen en de kleuren vervolgens naar behoefte aan te passen. Hier is een voorbeeld:

```java
// Het standaardkleurenschema ophalen
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Pas de kleuren indien nodig aan
colors.get_Item(0).setColor(Color.RED); // Stel de kleur van het eerste plakje in op rood
colors.get_Item(1).setColor(Color.BLUE); // Stel de kleur van het tweede segment in op blauw
// Voeg indien nodig meer kleurwijzigingen toe
```

### Hoe kan ik een legenda toevoegen aan het cirkeldiagram?

Om een legenda aan het cirkeldiagram toe te voegen, kunt u de `getLegend` methode en configureer deze als volgt:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // De positie van de legenda instellen
legend.setOverlay(true); // Toon de legenda boven de grafiek
```

### Kan ik het lettertype en de stijl van de titel wijzigen?

Ja, je kunt het lettertype en de stijl van de titel wijzigen. Gebruik de volgende code om het lettertype en de stijl van de titel in te stellen:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Lettergrootte instellen
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Maak de titel vetgedrukt
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Maak de titel cursief
```

U kunt de lettergrootte, vetgedruktheid en cursieve stijl naar wens aanpassen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}