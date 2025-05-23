---
"description": "Scopri come recuperare le dimensioni dell'area del grafico in Java Slides utilizzando Aspose.Slides per Java. Migliora le tue competenze di automazione di PowerPoint."
"linktitle": "Ottieni larghezza e altezza dall'area del grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Ottieni larghezza e altezza dall'area del grafico in Java Slides"
"url": "/it/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni larghezza e altezza dall'area del grafico in Java Slides


## Introduzione

grafici sono un modo efficace per visualizzare i dati nelle presentazioni di PowerPoint. A volte, potrebbe essere necessario conoscere le dimensioni dell'area del grafico per vari motivi, ad esempio per ridimensionare o riposizionare elementi al suo interno. Questa guida illustrerà come ottenere la larghezza e l'altezza dell'area del grafico utilizzando Java e Aspose.Slides per Java.

## Prerequisiti

Prima di immergerci nel codice, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria dal sito web di Aspose. [Qui](https://releases.aspose.com/slides/java/).

## Fase 1: Impostazione dell'ambiente

Assicurati di aver aggiunto la libreria Aspose.Slides per Java al tuo progetto Java. Puoi farlo includendo la libreria nelle dipendenze del progetto o aggiungendo manualmente il file JAR.

## Passaggio 2: creazione di una presentazione PowerPoint

Iniziamo creando una presentazione PowerPoint e aggiungendovi una diapositiva. Questa servirà da contenitore per il nostro grafico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Sostituire `"Your Document Directory"` con il percorso alla directory dei documenti.

## Passaggio 3: aggiunta di un grafico

Ora aggiungiamo un grafico a colonne raggruppate alla diapositiva. Convalideremo anche il layout del grafico.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Questo codice crea un grafico a colonne raggruppate nella posizione (100, 100) con dimensioni (500, 350).

## Fase 4: Ottenere le dimensioni dell'area del grafico

Per recuperare la larghezza e l'altezza dell'area del grafico, possiamo utilizzare il seguente codice:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Ora, le variabili `x`, `y`, `w`, E `h` contengono i rispettivi valori per la coordinata X, la coordinata Y, la larghezza e l'altezza dell'area del grafico.

## Passaggio 5: salvataggio della presentazione

Infine, salva la presentazione con il grafico.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Assicurati di sostituire `"Chart_out.pptx"` con il nome del file di output desiderato.

## Codice sorgente completo per ottenere larghezza e altezza dall'area del grafico in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Salva la presentazione con il grafico
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo articolo, abbiamo spiegato come ottenere la larghezza e l'altezza dell'area di un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Queste informazioni possono essere utili quando è necessario modificare dinamicamente il layout dei grafici nelle presentazioni di PowerPoint.

## Domande frequenti

### Come posso modificare il tipo di grafico in modo che non sia a colonne raggruppate?

È possibile modificare il tipo di grafico sostituendolo `ChartType.ClusteredColumn` con l'enumerazione del tipo di grafico desiderato, come ad esempio `ChartType.Line` O `ChartType.Pie`.

### Posso modificare altre proprietà del grafico?

Sì, puoi modificare diverse proprietà del grafico, come dati, etichette e formattazione, utilizzando l'API Aspose.Slides per Java. Consulta la documentazione per maggiori dettagli.

### Aspose.Slides per Java è adatto all'automazione professionale di PowerPoint?

Sì, Aspose.Slides per Java è una potente libreria per automatizzare le attività di PowerPoint nelle applicazioni Java. Offre funzionalità complete per lavorare con presentazioni, diapositive, forme, grafici e altro ancora.

### Come posso saperne di più su Aspose.Slides per Java?

Puoi trovare ampia documentazione ed esempi nella pagina di documentazione di Aspose.Slides per Java [Qui](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}