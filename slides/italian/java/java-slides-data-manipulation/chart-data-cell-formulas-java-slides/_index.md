---
"description": "Scopri come impostare le formule delle celle dati dei grafici nelle presentazioni PowerPoint in Java utilizzando Aspose.Slides per Java. Crea grafici dinamici con le formule."
"linktitle": "Formule delle celle dei dati del grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Formule delle celle dei dati del grafico in Java Slides"
"url": "/it/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formule delle celle dei dati del grafico in Java Slides


## Introduzione alle formule delle celle dei dati dei grafici in Aspose.Slides per Java

In questo tutorial, esploreremo come lavorare con le formule delle celle dati dei grafici utilizzando Aspose.Slides per Java. Con Aspose.Slides, è possibile creare e manipolare grafici nelle presentazioni di PowerPoint, inclusa l'impostazione di formule per le celle dati.

## Prerequisiti

Prima di iniziare, assicurati di aver installato la libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: creare una presentazione PowerPoint

Per prima cosa, creiamo una nuova presentazione PowerPoint e aggiungiamoci un grafico.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Aggiungere un grafico alla prima diapositiva
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Ottieni la cartella di lavoro per i dati del grafico
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Continua con le operazioni sulle celle dati
    // ...
    
    // Salva la presentazione
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Passaggio 2: impostare le formule per le celle dati

Ora impostiamo le formule per celle di dati specifiche nel grafico. In questo esempio, imposteremo le formule per due celle diverse.

### Cella 1: Utilizzo della notazione A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Nel codice sopra, impostiamo una formula per la cella B2 usando la notazione A1. La formula calcola la somma delle celle da F2 a H5 e aggiunge 1 al risultato.

### Cella 2: Utilizzo della notazione R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Qui, impostiamo una formula per la cella C2 utilizzando la notazione R1C1. La formula calcola il valore massimo nell'intervallo da R2C6 a R5C8 e poi lo divide per 3.

## Passaggio 3: calcolare le formule

Dopo aver impostato le formule, è fondamentale calcolarle utilizzando il seguente codice:

```java
workbook.calculateFormulas();
```

Questo passaggio garantisce che il grafico rifletta i valori aggiornati in base alle formule.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione modificata in un file.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Codice sorgente completo per le formule delle celle dei dati del grafico in Java Slides

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial abbiamo esplorato come utilizzare le formule delle celle dati dei grafici in Aspose.Slides per Java. Abbiamo trattato la creazione di una presentazione PowerPoint, l'aggiunta di un grafico, l'impostazione delle formule per le celle dati, il calcolo delle formule e il salvataggio della presentazione. Ora puoi sfruttare queste funzionalità per creare grafici dinamici e basati sui dati nelle tue presentazioni.

## Domande frequenti

### Come faccio ad aggiungere un grafico a una diapositiva specifica?

Per aggiungere un grafico a una diapositiva specifica, puoi utilizzare `getSlides().get_Item(slideIndex)` metodo per accedere alla diapositiva desiderata, quindi utilizzare il `addChart` metodo per aggiungere il grafico.

### Posso utilizzare diversi tipi di formule nelle celle di dati?

Sì, nelle formule delle celle dati è possibile utilizzare vari tipi di formule, tra cui operazioni matematiche, funzioni e riferimenti ad altre celle.

### Come faccio a cambiare il tipo di grafico?

È possibile modificare il tipo di grafico utilizzando `setChartType` metodo sul `IChart` oggetto e specificando il desiderato `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}