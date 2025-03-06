---
title: Nascondi informazioni dal grafico nelle diapositive Java
linktitle: Nascondi informazioni dal grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come nascondere gli elementi del grafico in Diapositive Java con Aspose.Slides per Java. Personalizza le presentazioni per maggiore chiarezza ed estetica con guida passo passo e codice sorgente.
weight: 13
url: /it/java/customization-and-formatting/hide-information-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione a nascondere le informazioni dal grafico nelle diapositive Java

In questo tutorial, esploreremo come nascondere vari elementi da un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Puoi utilizzare questo codice per personalizzare i tuoi grafici secondo necessità per le tue presentazioni.

## Passaggio 1: impostazione dell'ambiente

 Prima di iniziare, assicurati di aver aggiunto la libreria Aspose.Slides per Java al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 2: crea una nuova presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 3: aggiunta di un grafico alla diapositiva

Aggiungeremo un grafico a linee con indicatori a una diapositiva e quindi procederemo a nascondere i vari elementi del grafico.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Passaggio 4: nascondi il titolo del grafico

Puoi nascondere il titolo del grafico come segue:

```java
chart.setTitle(false);
```

## Passaggio 5: nascondere l'asse dei valori

Per nascondere l'asse dei valori (asse verticale), utilizzare il seguente codice:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Passaggio 6: nascondi l'asse delle categorie

Per nascondere l'asse delle categorie (asse orizzontale), utilizzare questo codice:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Passaggio 7: nascondi la legenda

Puoi nascondere la legenda del grafico in questo modo:

```java
chart.setLegend(false);
```

## Passaggio 8: nascondere le linee principali della griglia

Per nascondere le principali linee della griglia dell'asse orizzontale, puoi utilizzare il seguente codice:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Passaggio 9: rimuovere la serie

Se vuoi rimuovere tutte le serie dal grafico, puoi utilizzare un ciclo come questo:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Passaggio 10: personalizzare la serie di grafici

È possibile personalizzare le serie di grafici secondo necessità. In questo esempio, modifichiamo lo stile del marcatore, la posizione dell'etichetta dati, la dimensione del marcatore, il colore della linea e lo stile del trattino:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Passaggio 11: salva la presentazione

Infine, salva la presentazione in un file:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai nascosto con successo vari elementi da un grafico in Java Slides utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente i tuoi grafici e presentazioni secondo necessità per le tue esigenze specifiche.

## Codice sorgente completo per nascondere le informazioni dal grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Titolo del grafico nascosto
	chart.setTitle(false);
	///Asse dei valori nascosti
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Categoria Visibilità dell'asse
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Leggenda nascosta
	chart.setLegend(false);
	//Nascondere MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Impostazione del colore della linea della serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Conclusione

In questa guida passo passo, abbiamo esplorato come nascondere vari elementi da un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Questo può essere incredibilmente utile quando hai bisogno di personalizzare i tuoi grafici per le presentazioni e renderli visivamente più accattivanti o adattati alle tue esigenze specifiche.

## Domande frequenti

### Come posso personalizzare ulteriormente l'aspetto degli elementi del grafico?

Puoi personalizzare varie proprietà degli elementi del grafico come il colore della linea, il colore di riempimento, lo stile degli indicatori e altro ancora accedendo alle proprietà corrispondenti delle serie di grafici, degli indicatori, delle etichette e del formato.

### Posso nascondere punti dati specifici nel grafico?

Sì, puoi nascondere punti dati specifici manipolando i dati nelle serie di grafici. Puoi rimuovere punti dati o impostarne i valori su null per nasconderli.

### Come posso aggiungere ulteriori serie al grafico?

 Puoi aggiungere più serie al grafico utilizzando il comando`IChartData.getSeries().add` metodo e specificando i punti dati per la nuova serie.

### È possibile modificare il tipo di grafico in modo dinamico?

Sì, puoi modificare il tipo di grafico in modo dinamico creando un nuovo grafico del tipo desiderato e copiando i dati dal vecchio grafico a quello nuovo.

### Come posso modificare il titolo del grafico e le etichette degli assi a livello di codice?

Puoi impostare il titolo e le etichette del grafico e degli assi accedendo alle rispettive proprietà e impostando il testo e la formattazione desiderati.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
