---
"description": "Leer hoe u verschillende trendlijnen toevoegt aan Java Slides met Aspose.Slides voor Java. Stapsgewijze handleiding met codevoorbeelden voor effectieve datavisualisatie."
"linktitle": "Trendlijnen in Java-dia's weergeven"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Trendlijnen in Java-dia's weergeven"
"url": "/nl/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Trendlijnen in Java-dia's weergeven


## Inleiding tot trendlijnen in grafieken in Java-dia's: een stapsgewijze handleiding

In deze uitgebreide handleiding leggen we uit hoe je trendlijnen in grafieken kunt maken in Java Slides met Aspose.Slides voor Java. Trendlijnen in grafieken kunnen een waardevolle aanvulling zijn op je presentaties en helpen bij het effectief visualiseren en analyseren van datatrends. We leiden je door het proces met duidelijke uitleg en codevoorbeelden.

## Vereisten

Voordat we beginnen met het maken van trendlijnen in grafieken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java-ontwikkelomgeving
- Aspose.Slides voor Java-bibliotheek
- Een code-editor naar keuze

## Stap 1: Aan de slag

Laten we beginnen met het instellen van de benodigde omgeving en het maken van een nieuwe presentatie:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Lege presentatie maken
Presentation pres = new Presentation();
```

We hebben onze presentatie geïnitialiseerd en zijn nu klaar om een geclusterde kolomgrafiek toe te voegen:

```java
// Een geclusterde kolomgrafiek maken
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Stap 2: exponentiële trendlijn toevoegen

Laten we beginnen met het toevoegen van een exponentiële trendlijn aan onze grafiekreeks:

```java
// Exponentiële trendlijn toevoegen voor grafiekserie 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Stap 3: Lineaire trendlijn toevoegen

Vervolgens voegen we een lineaire trendlijn toe aan onze grafiekreeks:

```java
// Lineaire trendlijn toevoegen voor grafiekserie 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Stap 4: Logaritmische trendlijn toevoegen

Laten we nu een logaritmische trendlijn toevoegen aan een andere grafiekreeks:

```java
// Logaritmische trendlijn toevoegen voor grafiekserie 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Stap 5: Een voortschrijdende gemiddelde trendlijn toevoegen

We kunnen ook een trendlijn met een voortschrijdend gemiddelde toevoegen:

```java
// Trendlijn met voortschrijdend gemiddelde toevoegen voor grafiekserie 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Stap 6: Polynomiale trendlijn toevoegen

Een polynomiale trendlijn toevoegen:

```java
// Polynomiale trendlijn toevoegen voor grafiekserie 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Stap 7: Power Trend Line toevoegen

Laten we ten slotte een krachttrendlijn toevoegen:

```java
// Powertrendlijn toevoegen voor grafiekserie 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Stap 8: De presentatie opslaan

Nu we diverse trendlijnen aan onze grafiek hebben toegevoegd, slaan we de presentatie op:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gefeliciteerd! U hebt met succes een presentatie gemaakt met verschillende typen trendlijnen in Java Slides met behulp van Aspose.Slides voor Java.

## Volledige broncode voor grafiektrendlijnen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Lege presentatie maken
Presentation pres = new Presentation();
// Een geclusterde kolomgrafiek maken
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Potentiële trendlijn toevoegen voor grafiekserie 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Lineaire trendlijn toevoegen voor grafiekserie 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Logaritmische trendlijn toevoegen voor grafiekserie 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Trendlijn MovingAverage toevoegen voor grafiekserie 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Polynomiale trendlijn toevoegen voor grafiekserie 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Power-trendlijn toevoegen voor grafiekserie 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Presentatie opslaan
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusie

In deze tutorial hebben we geleerd hoe je verschillende soorten trendlijnen kunt toevoegen aan grafieken in Java Slides met behulp van de Aspose.Slides for Java-bibliotheek. Of je nu bezig bent met data-analyse of informatieve presentaties maakt, de mogelijkheid om trends te visualiseren kan een krachtig hulpmiddel zijn.

## Veelgestelde vragen

### Hoe verander ik de kleur van een trendlijn in Aspose.Slides voor Java?

Om de kleur van een trendlijn te veranderen, kunt u de `getSolidFillColor().setColor(Color)` methode, zoals getoond in het voorbeeld voor het toevoegen van een lineaire trendlijn.

### Kan ik meerdere trendlijnen aan één grafiekreeks toevoegen?

Ja, u kunt meerdere trendlijnen toevoegen aan één grafiekreeks. Roep hiervoor de `getTrendLines().add()` methode voor elke trendlijn die u wilt toevoegen.

### Hoe verwijder ik een trendlijn uit een grafiek in Aspose.Slides voor Java?

Om een trendlijn uit een grafiek te verwijderen, kunt u de `removeAt(int index)` methode, waarbij u de index opgeeft van de trendlijn die u wilt verwijderen.

### Is het mogelijk om de weergave van de trendlijnvergelijking aan te passen?

Ja, u kunt de weergave van de trendlijnvergelijking aanpassen met behulp van de `setDisplayEquation(boolean)` methode, zoals gedemonstreerd in het voorbeeld.

### Hoe kan ik meer bronnen en voorbeelden voor Aspose.Slides voor Java krijgen?

U kunt toegang krijgen tot aanvullende bronnen, documentatie en voorbeelden voor Aspose.Slides voor Java op de [Aspose-website](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}