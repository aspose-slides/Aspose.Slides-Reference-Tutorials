---
title: Imposta i dati del grafico dalla cartella di lavoro nelle diapositive Java
linktitle: Imposta i dati del grafico dalla cartella di lavoro nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare i dati del grafico da una cartella di lavoro di Excel in Diapositive Java utilizzando Aspose.Slides. Guida passo passo con esempi di codice per presentazioni dinamiche.
type: docs
weight: 15
url: /it/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Introduzione all'impostazione dei dati del grafico dalla cartella di lavoro nelle diapositive Java

Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di lavorare con presentazioni PowerPoint a livello di codice. Fornisce funzionalità estese per la creazione, la manipolazione e la gestione delle diapositive di PowerPoint. Un requisito comune quando si lavora con le presentazioni è impostare dinamicamente i dati del grafico da un'origine dati esterna, ad esempio una cartella di lavoro di Excel. In questo tutorial, dimostreremo come ottenere questo risultato utilizzando Java.

## Prerequisiti

Prima di approfondire l'implementazione, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
- Libreria Aspose.Slides per Java aggiunta al tuo progetto.
- Una cartella di lavoro di Excel con i dati che desideri utilizzare per il grafico.

## Passaggio 1: crea una presentazione

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Iniziamo creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides per Java.

## Passaggio 2: aggiungi un grafico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Successivamente, aggiungiamo un grafico a una delle diapositive della presentazione. In questo esempio stiamo aggiungendo un grafico a torta, ma puoi scegliere il tipo di grafico più adatto alle tue esigenze.

## Passaggio 3: cancella i dati del grafico

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Cancelliamo tutti i dati esistenti dal grafico per prepararlo per i nuovi dati dalla cartella di lavoro di Excel.

## Passaggio 4: caricare la cartella di lavoro di Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Carichiamo la cartella di lavoro Excel che contiene i dati che vogliamo utilizzare per il grafico. Sostituire`"book1.xlsx"` con il percorso del file Excel.

## Passaggio 5: scrivere il flusso della cartella di lavoro nei dati del grafico

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Convertiamo i dati della cartella di lavoro di Excel in un flusso e li scriviamo nei dati del grafico.

## Passaggio 6: imposta l'intervallo dati del grafico

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Specifichiamo l'intervallo di celle della cartella di lavoro di Excel che devono essere utilizzate come dati per il grafico. Regola l'intervallo secondo necessità per i tuoi dati.

## Passaggio 7: personalizzare la serie di grafici

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

È possibile personalizzare varie proprietà delle serie di grafici in base alle proprie esigenze. In questo esempio, abilitiamo colori diversi per le serie di grafici.

## Passaggio 8: salva la presentazione

```java
pres.save(outPath, SaveFormat.Pptx);
```

Infine, salviamo la presentazione con i dati del grafico aggiornati nel percorso di output specificato.

## Codice sorgente completo per impostare i dati del grafico dalla cartella di lavoro nelle diapositive Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato come impostare i dati del grafico da una cartella di lavoro di Excel in Java Slides utilizzando la libreria Aspose.Slides per Java. Seguendo la guida passo passo e utilizzando gli esempi di codice sorgente forniti, puoi integrare facilmente i dati dei grafici dinamici nelle tue presentazioni PowerPoint.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico nella mia presentazione?

Puoi personalizzare l'aspetto del grafico modificando proprietà come colori, caratteri, etichette e altro. Fare riferimento alla documentazione Aspose.Slides per Java per informazioni dettagliate sulle opzioni di personalizzazione del grafico.

### Posso utilizzare i dati di un file Excel diverso per il grafico?

Sì, puoi utilizzare i dati di qualsiasi file Excel specificando il percorso file corretto durante il caricamento della cartella di lavoro nel codice.

### Quali altri tipi di grafici posso creare con Aspose.Slides per Java?

Aspose.Slides per Java supporta vari tipi di grafici, inclusi grafici a barre, grafici a linee, grafici a dispersione e altro. Puoi scegliere il tipo di grafico che meglio si adatta alle tue esigenze di rappresentazione dei dati.

### È possibile aggiornare dinamicamente i dati del grafico in una presentazione in corso?

Sì, puoi aggiornare dinamicamente i dati del grafico in una presentazione modificando la cartella di lavoro sottostante e quindi aggiornando i dati del grafico.

### Dove posso trovare altri esempi e risorse per lavorare con Aspose.Slides per Java?

 Puoi esplorare ulteriori esempi e risorse su[Sito web Aspose](https://www.aspose.com/). Inoltre, la documentazione Aspose.Slides per Java fornisce indicazioni complete su come lavorare con la libreria.