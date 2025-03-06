---
title: Ottieni la posizione effettiva dell'etichetta dei dati del grafico nelle diapositive Java
linktitle: Ottieni la posizione effettiva dell'etichetta dei dati del grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come ottenere la posizione effettiva delle etichette dei dati del grafico in Diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con il codice sorgente.
weight: 18
url: /it/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione per ottenere la posizione effettiva dell'etichetta dei dati del grafico nelle diapositive Java

In questo tutorial imparerai come recuperare la posizione effettiva delle etichette dei dati del grafico utilizzando Aspose.Slides per Java. Creeremo un programma Java che genera una presentazione PowerPoint con un grafico, personalizza le etichette dei dati e quindi aggiunge forme che rappresentano le posizioni di queste etichette dei dati.

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java impostata nel tuo progetto Java.

## Passaggio 1: crea una presentazione PowerPoint

Innanzitutto, creiamo una nuova presentazione PowerPoint e aggiungiamo un grafico. Personalizzeremo le etichette dei dati del grafico più avanti nel tutorial.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Passaggio 2: personalizzare le etichette dati
Ora personalizziamo le etichette dei dati per le serie di grafici. Imposteremo la loro posizione e mostreremo i valori.

```java
try {
    // ... (codice precedente)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (codice rimanente)
} finally {
    if (pres != null) pres.dispose();
}
```

## Passaggio 3: ottenere la posizione effettiva delle etichette dati
In questo passaggio, ripeteremo i punti dati della serie di grafici e recupereremo la posizione effettiva delle etichette dati che hanno un valore maggiore di 4. Aggiungeremo quindi dei puntini di sospensione per rappresentare queste posizioni.

```java
try {
    // ... (codice precedente)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (codice rimanente)
} finally {
    if (pres != null) pres.dispose();
}
```

## Passaggio 4: salva la presentazione
Infine, salva la presentazione generata in un file.

```java
try {
    // ... (codice precedente)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Codice sorgente completo per ottenere la posizione effettiva dell'etichetta dei dati del grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//FARE
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come recuperare la posizione effettiva delle etichette dei dati del grafico in Java Slides utilizzando Aspose.Slides per Java. Ora puoi utilizzare questa conoscenza per migliorare le tue presentazioni PowerPoint con etichette dati personalizzate e rappresentazioni visive delle loro posizioni.

## Domande frequenti

### Come posso personalizzare le etichette dei dati in un grafico?

 Per personalizzare le etichette dati in un grafico, puoi utilizzare`setDefaultDataLabelFormat` metodo sulla serie di grafici e impostare proprietà come posizione e visibilità. Per esempio:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Come posso aggiungere forme per rappresentare le posizioni delle etichette dati?

 È possibile scorrere i punti dati di una serie di grafici e utilizzare il file`getActualX`, `getActualY`, `getActualWidth` , E`getActualHeight`metodi dell'etichetta dati per ottenere la sua posizione. Quindi, puoi aggiungere forme utilizzando il`addAutoShape` metodo. Ecco un esempio:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Come posso salvare la presentazione generata?

 È possibile salvare la presentazione generata utilizzando il file`save` metodo. Fornire il percorso del file desiderato e il file`SaveFormat` come parametri. Per esempio:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
