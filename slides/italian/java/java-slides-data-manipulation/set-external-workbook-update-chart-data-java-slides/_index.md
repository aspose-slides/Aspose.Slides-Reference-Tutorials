---
title: Imposta la cartella di lavoro esterna con l'aggiornamento dei dati del grafico nelle diapositive Java
linktitle: Imposta la cartella di lavoro esterna con l'aggiornamento dei dati del grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare cartelle di lavoro esterne e aggiornare i dati del grafico in Diapositive Java utilizzando Aspose.Slides per Java. Migliora le tue capacità di automazione di PowerPoint.
type: docs
weight: 20
url: /it/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## Introduzione all'impostazione della cartella di lavoro esterna con l'aggiornamento dei dati del grafico nelle diapositive Java

In questa guida completa, ti guideremo attraverso il processo di impostazione di una cartella di lavoro esterna con i dati del grafico aggiornati in Java Slides utilizzando l'API Aspose.Slides per Java. Questa potente libreria ti consente di manipolare le presentazioni di PowerPoint a livello di codice, semplificando l'automazione di attività come l'aggiornamento dei dati del grafico da una fonte esterna. Alla fine di questo tutorial, avrai una chiara comprensione di come eseguire questa attività con istruzioni dettagliate e il codice Java di accompagnamento.

## Prerequisiti

Prima di approfondire l'implementazione, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Slides per Java: dovresti avere la libreria Aspose.Slides per Java installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

2. Ambiente di sviluppo Java: assicurati di avere un ambiente di sviluppo Java configurato sul tuo sistema.

## Passaggio 1: crea una nuova presentazione

Per iniziare, creiamo una nuova presentazione di PowerPoint utilizzando Aspose.Slides per Java. Ecco il codice Java per farlo:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico

Ora aggiungiamo un grafico alla nostra presentazione. Creeremo un grafico a torta in questo esempio:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Passaggio 3: imposta la cartella di lavoro esterna

Qui è dove impostiamo la cartella di lavoro esterna come origine dati per il nostro grafico. Devi fornire l'URL della cartella di lavoro esterna, anche se per ora non esiste:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://percorso/non/esiste", false);
```

## Passaggio 4: salva la presentazione

Infine, salva la presentazione con i dati del grafico aggiornati:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per impostare una cartella di lavoro esterna con i dati del grafico di aggiornamento nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

Congratulazioni! Hai imparato come impostare una cartella di lavoro esterna con i dati del grafico aggiornati in Java Slides utilizzando Aspose.Slides per Java. Questo può essere incredibilmente utile per aggiornare dinamicamente i grafici nelle presentazioni PowerPoint da origini dati esterne.

## Domande frequenti

### Come posso aggiornare i dati della cartella di lavoro esterna per il grafico?

Per aggiornare i dati della cartella di lavoro esterna per il grafico, è sufficiente modificare i dati nella cartella di lavoro esterna all'URL specificato. La prossima volta che apri la presentazione, Aspose.Slides per Java recupererà i dati aggiornati dalla cartella di lavoro esterna e aggiornerà il grafico di conseguenza.

### Posso utilizzare un file locale come cartella di lavoro esterna?

Sì, puoi utilizzare un file locale come cartella di lavoro esterna fornendo il percorso del file anziché un URL. Assicurati solo che il percorso del file sia corretto e accessibile dalla tua applicazione Java.

### Esistono limitazioni all'utilizzo di cartelle di lavoro esterne con Aspose.Slides per Java?

Sebbene l'utilizzo di cartelle di lavoro esterne sia una funzionalità potente, tieni presente che la disponibilità dei dati della cartella di lavoro esterna dipende dalla sua accessibilità all'URL o al percorso del file fornito. Assicurati che l'origine dati esterna sia disponibile quando apri la presentazione per evitare problemi di recupero dei dati.

### Posso personalizzare l'aspetto del grafico dopo aver impostato la cartella di lavoro esterna?

Sì, puoi personalizzare l'aspetto del grafico, inclusi titolo, etichette, colori e altro, anche dopo aver impostato la cartella di lavoro esterna. Aspose.Slides per Java offre ampie opzioni di formattazione dei grafici per soddisfare le tue esigenze.

### Dove posso trovare ulteriore documentazione e risorse per Aspose.Slides per Java?

 Per documentazione dettagliata e risorse aggiuntive, visitare la documentazione di Aspose.Slides per Java all'indirizzo[Qui](https://reference.aspose.com/slides/java/).