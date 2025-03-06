---
title: Ottieni larghezza e altezza dall'area del grafico nelle diapositive Java
linktitle: Ottieni larghezza e altezza dall'area del grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come recuperare le dimensioni dell'area del grafico in Diapositive Java utilizzando Aspose.Slides per Java. Migliora le tue capacità di automazione di PowerPoint.
weight: 21
url: /it/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## introduzione

I grafici rappresentano un modo efficace per visualizzare i dati nelle presentazioni di PowerPoint. A volte potrebbe essere necessario conoscere le dimensioni dell'area del tracciato di un grafico per vari motivi, ad esempio il ridimensionamento o il riposizionamento degli elementi all'interno del grafico. Questa guida mostrerà come ottenere la larghezza e l'altezza dell'area del tracciato utilizzando Java e Aspose.Slides per Java.

## Prerequisiti

 Prima di immergerci nel codice, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria dal sito Web Aspose[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: impostazione dell'ambiente

Assicurati di avere la libreria Aspose.Slides per Java aggiunta al tuo progetto Java. Puoi farlo includendo la libreria nelle dipendenze del tuo progetto o aggiungendo manualmente il file JAR.

## Passaggio 2: creazione di una presentazione PowerPoint

Iniziamo creando una presentazione PowerPoint e aggiungendovi una diapositiva. Questo servirà da contenitore per il nostro grafico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Sostituire`"Your Document Directory"` con il percorso della directory dei documenti.

## Passaggio 3: aggiunta di un grafico

Ora aggiungiamo un istogramma in cluster alla diapositiva. Convalideremo anche il layout del grafico.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Questo codice crea un istogramma in cluster nella posizione (100, 100) con dimensioni (500, 350).

## Passaggio 4: ottenere le dimensioni dell'area del tracciato

Per recuperare la larghezza e l'altezza dell'area del tracciato del grafico, possiamo utilizzare il seguente codice:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Ora, le variabili`x`, `y`, `w` , E`h` contengono i rispettivi valori per la coordinata X, la coordinata Y, la larghezza e l'altezza dell'area del tracciato.

## Passaggio 5: salvataggio della presentazione

Infine, salva la presentazione con il grafico.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Assicurati di sostituire`"Chart_out.pptx"` con il nome del file di output desiderato.

## Codice sorgente completo per ottenere larghezza e altezza dall'area del grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

In questo articolo, abbiamo spiegato come ottenere la larghezza e l'altezza dell'area del tracciato di un grafico in Java Slides utilizzando l'API Aspose.Slides per Java. Queste informazioni possono essere utili quando è necessario regolare dinamicamente il layout dei grafici all'interno delle presentazioni PowerPoint.

## Domande frequenti

### Come posso modificare il tipo di grafico in qualcosa di diverso dalle colonne raggruppate?

 È possibile modificare il tipo di grafico sostituendo`ChartType.ClusteredColumn` con l'enumerazione del tipo di grafico desiderato, ad esempio`ChartType.Line` O`ChartType.Pie`.

### Posso modificare altre proprietà del grafico?

Sì, puoi modificare varie proprietà del grafico, come dati, etichette e formattazione, utilizzando l'API Aspose.Slides per Java. Fare riferimento alla documentazione per maggiori dettagli.

### Aspose.Slides per Java è adatto per l'automazione professionale di PowerPoint?

Sì, Aspose.Slides per Java è una potente libreria per automatizzare le attività di PowerPoint nelle applicazioni Java. Fornisce funzionalità complete per lavorare con presentazioni, diapositive, forme, grafici e altro ancora.

### Come posso saperne di più su Aspose.Slides per Java?

 È possibile trovare documentazione approfondita ed esempi nella pagina della documentazione Aspose.Slides per Java[Qui](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
