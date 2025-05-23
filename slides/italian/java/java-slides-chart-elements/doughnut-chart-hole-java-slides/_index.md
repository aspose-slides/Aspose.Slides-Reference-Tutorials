---
"description": "Crea grafici ad anello con dimensioni dei fori personalizzate in Java Slides utilizzando Aspose.Slides per Java. Guida dettagliata con codice sorgente per la personalizzazione dei grafici."
"linktitle": "Grafico a ciambella con foro in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Grafico a ciambella con foro in Java Slides"
"url": "/it/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafico a ciambella con foro in Java Slides


## Introduzione al grafico a ciambella con foro in Java Slides

In questo tutorial, ti guideremo nella creazione di un grafico a ciambella con un foro utilizzando Aspose.Slides per Java. Questa guida passo passo ti guiderà passo passo attraverso il processo, con esempi di codice sorgente.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricarla da [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: importare le librerie richieste

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Passaggio 2: inizializzare la presentazione

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
```

## Passaggio 3: creare il grafico a ciambella

```java
try {
    // Crea un grafico a ciambella nella prima diapositiva
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Imposta la dimensione del foro nel grafico a ciambella (in percentuale)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Salva la presentazione su disco
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Eliminare l'oggetto di presentazione
    if (presentation != null) presentation.dispose();
}
```

## Passaggio 4: eseguire il codice

Esegui il codice Java nel tuo IDE o nell'editor di testo per creare un grafico a ciambella con una dimensione del foro specificata. Assicurati di sostituire `"Your Document Directory"` con il percorso effettivo in cui desideri salvare la presentazione.

## Codice sorgente completo per il grafico a ciambella in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
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

In questo tutorial, hai imparato a creare un grafico a ciambella con un foro utilizzando Aspose.Slides per Java. Puoi personalizzare la dimensione del foro regolando `setDoughnutHoleSize` parametro del metodo.

## Domande frequenti

### Come posso cambiare il colore dei segmenti del grafico?

Per cambiare il colore dei segmenti del grafico, puoi utilizzare `setDataPointsInLegend` metodo sul `IChart` oggetto e imposta il colore desiderato per ciascun punto dati.

### Posso aggiungere etichette ai segmenti del grafico a ciambella?

Sì, puoi aggiungere etichette ai segmenti del grafico a ciambella utilizzando `setDataPointsLabelValue` metodo sul `IChart` oggetto.

### È possibile aggiungere un titolo al grafico?

Certamente! Puoi aggiungere un titolo al grafico utilizzando `setTitle` metodo sul `IChart` oggetto e fornendo il testo del titolo desiderato.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}