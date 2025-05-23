---
"description": "Scopri come impostare cartelle di lavoro esterne e aggiornare i dati dei grafici in Java Slides utilizzando Aspose.Slides per Java. Migliora le tue competenze di automazione in PowerPoint."
"linktitle": "Imposta cartella di lavoro esterna con aggiornamento dei dati del grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta cartella di lavoro esterna con aggiornamento dei dati del grafico in Java Slides"
"url": "/it/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta cartella di lavoro esterna con aggiornamento dei dati del grafico in Java Slides


## Introduzione all'impostazione di una cartella di lavoro esterna con aggiornamento dei dati del grafico in Java Slides

In questa guida completa, ti guideremo attraverso il processo di impostazione di una cartella di lavoro esterna con dati di grafici aggiornati in Java Slides utilizzando l'API Aspose.Slides per Java. Questa potente libreria consente di manipolare le presentazioni di PowerPoint a livello di codice, semplificando l'automazione di attività come l'aggiornamento dei dati di grafici da una fonte esterna. Al termine di questo tutorial, avrai una chiara comprensione di come eseguire questa operazione con istruzioni dettagliate e codice Java correlato.

## Prerequisiti

Prima di passare all'implementazione, assicurati di avere i seguenti prerequisiti:

1. Aspose.Slides per Java: dovresti avere installata la libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

2. Ambiente di sviluppo Java: assicurati di avere un ambiente di sviluppo Java configurato sul tuo sistema.

## Passaggio 1: creare una nuova presentazione

Per iniziare, creiamo una nuova presentazione PowerPoint utilizzando Aspose.Slides per Java. Ecco il codice Java per farlo:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico

Ora aggiungiamo un grafico alla nostra presentazione. In questo esempio, creeremo un grafico a torta:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Passaggio 3: imposta cartella di lavoro esterna

Qui impostiamo la cartella di lavoro esterna come origine dati per il nostro grafico. È necessario fornire l'URL della cartella di lavoro esterna, anche se al momento non esiste:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://percorso/non/esiste", false);
```

## Passaggio 4: salva la presentazione

Infine, salva la presentazione con i dati del grafico aggiornati:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per impostare una cartella di lavoro esterna con aggiornamento dei dati del grafico in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://percorso/non/esiste", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

Congratulazioni! Hai imparato come impostare una cartella di lavoro esterna con dati grafici aggiornati in Java Slides utilizzando Aspose.Slides per Java. Questo può essere incredibilmente utile per aggiornare dinamicamente i grafici nelle tue presentazioni PowerPoint da fonti dati esterne.

## Domande frequenti

### Come posso aggiornare i dati della cartella di lavoro esterna per il grafico?

Per aggiornare i dati della cartella di lavoro esterna per il grafico, è sufficiente modificare i dati nella cartella di lavoro esterna all'URL specificato. Alla successiva apertura della presentazione, Aspose.Slides per Java recupererà i dati aggiornati dalla cartella di lavoro esterna e aggiornerà il grafico di conseguenza.

### Posso utilizzare un file locale come cartella di lavoro esterna?

Sì, puoi utilizzare un file locale come cartella di lavoro esterna specificando il percorso del file anziché un URL. Assicurati solo che il percorso del file sia corretto e accessibile dalla tua applicazione Java.

### Esistono limitazioni all'utilizzo di cartelle di lavoro esterne con Aspose.Slides per Java?

Sebbene l'utilizzo di cartelle di lavoro esterne sia una funzionalità potente, è importante tenere presente che la disponibilità dei dati della cartella di lavoro esterna dipende dalla sua accessibilità all'URL o al percorso del file fornito. Assicurarsi che l'origine dati esterna sia disponibile all'apertura della presentazione per evitare problemi di recupero dei dati.

### Posso personalizzare l'aspetto del grafico dopo aver impostato la cartella di lavoro esterna?

Sì, puoi personalizzare l'aspetto del grafico, inclusi titolo, etichette, colori e altro, anche dopo aver impostato la cartella di lavoro esterna. Aspose.Slides per Java offre ampie opzioni di formattazione dei grafici per soddisfare le tue esigenze.

### Dove posso trovare ulteriore documentazione e risorse per Aspose.Slides per Java?

Per documentazione dettagliata e risorse aggiuntive, visitare la documentazione di Aspose.Slides per Java all'indirizzo [Qui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}