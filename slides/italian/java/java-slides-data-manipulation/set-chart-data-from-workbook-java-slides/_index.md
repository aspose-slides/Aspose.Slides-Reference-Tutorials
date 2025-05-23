---
"description": "Scopri come impostare i dati di un grafico da una cartella di lavoro Excel in Java Slides utilizzando Aspose.Slides. Guida dettagliata con esempi di codice per presentazioni dinamiche."
"linktitle": "Imposta i dati del grafico dalla cartella di lavoro in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta i dati del grafico dalla cartella di lavoro in Java Slides"
"url": "/it/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta i dati del grafico dalla cartella di lavoro in Java Slides


## Introduzione all'impostazione dei dati del grafico dalla cartella di lavoro in Java Slides

Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di lavorare con le presentazioni di PowerPoint a livello di codice. Offre funzionalità complete per la creazione, la manipolazione e la gestione delle diapositive di PowerPoint. Un'esigenza comune quando si lavora con le presentazioni è quella di impostare dinamicamente i dati dei grafici da un'origine dati esterna, come una cartella di lavoro di Excel. In questo tutorial, mostreremo come ottenere questo risultato utilizzando Java.

## Prerequisiti

Prima di addentrarci nell'implementazione, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- Libreria Aspose.Slides per Java aggiunta al tuo progetto.
- Una cartella di lavoro Excel con i dati che vuoi utilizzare per il grafico.

## Passaggio 1: creare una presentazione

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Iniziamo creando una nuova presentazione PowerPoint utilizzando Aspose.Slides per Java.

## Passaggio 2: aggiungere un grafico

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Successivamente, aggiungiamo un grafico a una delle diapositive della presentazione. In questo esempio, stiamo aggiungendo un grafico a torta, ma puoi scegliere il tipo di grafico più adatto alle tue esigenze.

## Passaggio 3: cancellare i dati del grafico

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Cancelliamo tutti i dati esistenti dal grafico per prepararlo ai nuovi dati provenienti dalla cartella di lavoro di Excel.

## Passaggio 4: caricare la cartella di lavoro di Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Carichiamo la cartella di lavoro di Excel che contiene i dati che vogliamo utilizzare per il grafico. Sostituisci `"book1.xlsx"` con il percorso del file Excel.

## Passaggio 5: scrivere il flusso della cartella di lavoro nei dati del grafico

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Convertiamo i dati della cartella di lavoro di Excel in un flusso e li scriviamo nei dati del grafico.

## Passaggio 6: imposta l'intervallo dei dati del grafico

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Specifichiamo l'intervallo di celle della cartella di lavoro di Excel da utilizzare come dati per il grafico. Adatta l'intervallo in base alle tue esigenze.

## Passaggio 7: personalizzare la serie di grafici

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Puoi personalizzare diverse proprietà della serie di grafici in base alle tue esigenze. In questo esempio, abilitiamo diversi colori per la serie di grafici.

## Passaggio 8: Salva la presentazione

```java
pres.save(outPath, SaveFormat.Pptx);
```

Infine, salviamo la presentazione con i dati del grafico aggiornati nel percorso di output specificato.

## Codice sorgente completo per impostare i dati del grafico dalla cartella di lavoro in Java Slides

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

In questo tutorial, abbiamo imparato come impostare i dati di un grafico da una cartella di lavoro di Excel in Java Slides utilizzando la libreria Aspose.Slides per Java. Seguendo la guida passo passo e utilizzando gli esempi di codice sorgente forniti, è possibile integrare facilmente i dati di un grafico dinamico nelle presentazioni PowerPoint.

## Domande frequenti

### Come posso personalizzare l'aspetto del grafico nella mia presentazione?

È possibile personalizzare l'aspetto del grafico modificando proprietà come colori, font, etichette e altro ancora. Consultare la documentazione di Aspose.Slides per Java per informazioni dettagliate sulle opzioni di personalizzazione dei grafici.

### Posso usare i dati di un file Excel diverso per il grafico?

Sì, puoi utilizzare i dati di qualsiasi file Excel specificando il percorso corretto del file quando carichi la cartella di lavoro nel codice.

### Quali altri tipi di grafici posso creare con Aspose.Slides per Java?

Aspose.Slides per Java supporta diversi tipi di grafici, tra cui grafici a barre, grafici a linee, grafici a dispersione e altro ancora. Puoi scegliere il tipo di grafico più adatto alle tue esigenze di rappresentazione dei dati.

### È possibile aggiornare dinamicamente i dati del grafico in una presentazione in esecuzione?

Sì, è possibile aggiornare dinamicamente i dati del grafico in una presentazione modificando la cartella di lavoro sottostante e quindi aggiornando i dati del grafico.

### Dove posso trovare altri esempi e risorse per lavorare con Aspose.Slides per Java?

Puoi esplorare ulteriori esempi e risorse su [Sito web di Aspose](https://www.aspose.com/)Inoltre, la documentazione di Aspose.Slides per Java fornisce una guida completa su come lavorare con la libreria.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}