---
"description": "Leer hoe u foutbalken toevoegt aan PowerPoint-grafieken in Java met Aspose.Slides. Stapsgewijze handleiding met broncode voor het aanpassen van foutbalken."
"linktitle": "Foutbalken toevoegen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Foutbalken toevoegen in Java-dia's"
"url": "/nl/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Foutbalken toevoegen in Java-dia's


## Inleiding tot het toevoegen van foutbalken in Java-dia's met Aspose.Slides

In deze tutorial laten we zien hoe je foutbalken toevoegt aan een grafiek in een PowerPoint-dia met behulp van Aspose.Slides voor Java. Foutbalken bieden waardevolle informatie over de variabiliteit of onzekerheid van datapunten in een grafiek. We maken een bellendiagram en voegen er foutbalken aan toe. Laten we beginnen!

## Vereisten

Voordat u begint, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden van de [Aspose-website](https://downloads.aspose.com/slides/java).

## Stap 1: Maak een lege presentatie

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
```

In deze stap maken we een lege presentatie waaraan we onze grafiek met foutbalken toevoegen.

## Stap 2: Maak een bubbeldiagram

```java
// Een bubbeldiagram maken
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Hier maken we een bellendiagram en specificeren we de positie en afmetingen ervan op de dia.

## Stap 3: Foutbalken toevoegen en opmaak instellen

```java
// Foutbalken toevoegen en de opmaak ervan instellen
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

In deze stap voegen we foutbalken toe aan de grafiek en stellen we de opmaak ervan in. U kunt de foutbalken aanpassen door waarden, typen en andere eigenschappen te wijzigen.

- `errBarX` geeft foutbalken weer langs de X-as.
- `errBarY` geeft foutbalken weer langs de Y-as.
- We maken zowel X- als Y-foutbalken zichtbaar.
- `setValueType` specificeert het waardetype voor foutbalken (bijvoorbeeld Vast of Percentage).
- `setValue` stelt de waarde voor foutbalken in.
- `setType` definieert het type foutbalken (bijv. Plus of Min).
- We stellen de breedte van de foutbalklijnen in met behulp van `getFormat().getLine().setWidth(2)`.
- `setEndCap` Hiermee wordt aangegeven of eindkappen op de foutbalken moeten worden weergegeven.

## Stap 4: Sla de presentatie op

```java
// Presentatie opslaan
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie met de toegevoegde foutbalken op de opgegeven locatie op.

Dat is alles! Je hebt met succes foutbalken toegevoegd aan een grafiek in een PowerPoint-dia met Aspose.Slides voor Java.

## Volledige broncode voor het toevoegen van foutbalken in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Lege presentatie maken
Presentation presentation = new Presentation();
try
{
	// Een bubbeldiagram maken
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Foutbalken toevoegen en de opmaak ervan instellen
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Presentatie opslaan
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze tutorial hebben we onderzocht hoe je je PowerPoint-presentaties kunt verbeteren door foutbalken aan grafieken toe te voegen met Aspose.Slides voor Java. Foutbalken bieden waardevolle inzichten in de variabiliteit en onzekerheden van gegevens, waardoor je presentaties informatiever en visueel aantrekkelijker worden.

## Veelgestelde vragen

### Hoe kan ik het uiterlijk van de foutbalken verder aanpassen?

U kunt foutbalken aanpassen door hun eigenschappen te wijzigen, zoals lijnstijl, kleur en breedte, zoals gedemonstreerd in stap 3.

### Kan ik foutbalken toevoegen aan verschillende grafiektypen?

Ja, u kunt foutbalken toevoegen aan verschillende grafiektypen die Aspose.Slides voor Java ondersteunt. Maak eenvoudig het gewenste grafiektype aan en volg dezelfde stappen voor het aanpassen van de foutbalk.

### Hoe kan ik de positie en grootte van de grafiek op de dia aanpassen?

U kunt de positie en afmetingen van de grafiek bepalen door de parameters in de `addChart` methode, zoals getoond in Stap 2.

### Waar kan ik meer informatie vinden over Aspose.Slides voor Java?

U kunt verwijzen naar de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde informatie over het gebruik van de bibliotheek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}