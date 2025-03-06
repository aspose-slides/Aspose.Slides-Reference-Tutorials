---
title: Foro del grafico a ciambella nelle diapositive Java
linktitle: Foro del grafico a ciambella nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea grafici a ciambella con dimensioni dei fori personalizzate nelle diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per la personalizzazione del grafico.
weight: 11
url: /it/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione al grafico a ciambella con un foro nelle diapositive Java

In questo tutorial, ti guideremo attraverso la creazione di un grafico a ciambella con un buco utilizzando Aspose.Slides per Java. Questa guida passo passo ti guiderà attraverso il processo con esempi di codice sorgente.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. Puoi scaricarlo da[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: importa le librerie richieste

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Passaggio 2: inizializzare la presentazione

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```

## Passaggio 3: crea il grafico a ciambella

```java
try {
    // Crea un grafico ad anello nella prima diapositiva
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Imposta la dimensione del foro nel grafico a ciambella (in percentuale)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Salva la presentazione su disco
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Smaltire l'oggetto della presentazione
    if (presentation != null) presentation.dispose();
}
```

## Passaggio 4: esegui il codice

 Esegui il codice Java nel tuo IDE o nell'editor di testo per creare un grafico a ciambella con una dimensione del foro specificata. Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.

## Codice sorgente completo per il foro del grafico a ciambella nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Scrivi la presentazione su disco
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

 In questo tutorial, hai imparato come creare un grafico a ciambella con un buco utilizzando Aspose.Slides per Java. È possibile personalizzare la dimensione del foro regolando il`setDoughnutHoleSize` parametro del metodo.

## Domande frequenti

### Come posso cambiare il colore dei segmenti del grafico?

 Per cambiare il colore dei segmenti del grafico, puoi utilizzare il`setDataPointsInLegend` metodo sul`IChart` oggetto e impostare il colore desiderato per ciascun punto dati.

### Posso aggiungere etichette ai segmenti del grafico ad anello?

 Sì, puoi aggiungere etichette ai segmenti del grafico ad anello utilizzando il file`setDataPointsLabelValue` metodo sul`IChart` oggetto.

### È possibile aggiungere un titolo al grafico?

 Certamente! Puoi aggiungere un titolo al grafico utilizzando il file`setTitle` metodo sul`IChart` oggetto e fornendo il testo del titolo desiderato.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
