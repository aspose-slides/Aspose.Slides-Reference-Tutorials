---
"description": "Scopri come nascondere gli elementi dei grafici in Java Slides con Aspose.Slides per Java. Personalizza le presentazioni per renderle più chiare ed esteticamente gradevoli con istruzioni dettagliate e codice sorgente."
"linktitle": "Nascondi informazioni dal grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Nascondi informazioni dal grafico in Java Slides"
"url": "/it/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nascondi informazioni dal grafico in Java Slides


## Introduzione a come nascondere le informazioni dal grafico in Java Slides

In questo tutorial, esploreremo come nascondere diversi elementi da un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Puoi utilizzare questo codice per personalizzare i grafici in base alle tue esigenze per le tue presentazioni.

## Fase 1: Impostazione dell'ambiente

Prima di iniziare, assicurati di aver aggiunto la libreria Aspose.Slides per Java al tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 2: creare una nuova presentazione

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 3: aggiunta di un grafico alla diapositiva

Aggiungeremo un grafico a linee con dei marcatori a una diapositiva e poi procederemo a nascondere vari elementi del grafico.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Passaggio 4: nascondere il titolo del grafico

È possibile nascondere il titolo del grafico come segue:

```java
chart.setTitle(false);
```

## Passaggio 5: Nascondi l'asse dei valori

Per nascondere l'asse dei valori (asse verticale), utilizzare il seguente codice:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Passaggio 6: nascondere l'asse delle categorie

Per nascondere l'asse delle categorie (asse orizzontale), utilizzare questo codice:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Passaggio 7: Nascondi la legenda

Puoi nascondere la legenda del grafico in questo modo:

```java
chart.setLegend(false);
```

## Passaggio 8: nascondere le linee principali della griglia

Per nascondere le linee principali della griglia dell'asse orizzontale, puoi utilizzare il seguente codice:

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

È possibile personalizzare la serie di grafici in base alle proprie esigenze. In questo esempio, modifichiamo lo stile del marcatore, la posizione dell'etichetta dati, la dimensione del marcatore, il colore della linea e lo stile del trattino:

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

## Passaggio 11: Salva la presentazione

Infine, salva la presentazione in un file:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai nascosto con successo vari elementi da un grafico in Java Slides utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente grafici e presentazioni in base alle tue esigenze specifiche.

## Codice sorgente completo per nascondere le informazioni dal grafico nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Nascondere il titolo del grafico
	chart.setTitle(false);
	///Nascondere l'asse dei valori
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Visibilità dell'asse delle categorie
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
	//Impostazione del colore della linea di serie
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

In questa guida passo passo, abbiamo spiegato come nascondere vari elementi da un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Questo può essere incredibilmente utile quando si desidera personalizzare i grafici per le presentazioni, renderli più accattivanti o adattarli alle proprie esigenze specifiche.

## Domande frequenti

### Come posso personalizzare ulteriormente l'aspetto degli elementi del grafico?

È possibile personalizzare varie proprietà degli elementi del grafico, come il colore della linea, il colore di riempimento, lo stile del marcatore e altro ancora, accedendo alle proprietà corrispondenti della serie del grafico, dei marcatori, delle etichette e del formato.

### Posso nascondere punti dati specifici nel grafico?

Sì, puoi nascondere punti dati specifici manipolando i dati nella serie del grafico. Puoi rimuovere punti dati o impostarne i valori su null per nasconderli.

### Come posso aggiungere altre serie al grafico?

È possibile aggiungere altre serie al grafico utilizzando `IChartData.getSeries().add` metodo e specificando i punti dati per la nuova serie.

### È possibile modificare dinamicamente il tipo di grafico?

Sì, puoi modificare dinamicamente il tipo di grafico creando un nuovo grafico del tipo desiderato e copiando i dati dal vecchio grafico a quello nuovo.

### Come posso modificare a livello di programmazione il titolo e le etichette degli assi del grafico?

È possibile impostare il titolo e le etichette del grafico e degli assi accedendo alle rispettive proprietà e impostando il testo e la formattazione desiderati.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}