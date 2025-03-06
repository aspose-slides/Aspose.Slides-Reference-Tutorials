---
title: Calcola formule nelle diapositive Java
linktitle: Calcola formule nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come calcolare le formule in Diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente per presentazioni PowerPoint dinamiche.
weight: 10
url: /it/java/data-manipulation/calculate-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione al calcolo delle formule nelle diapositive Java utilizzando Aspose.Slides

In questa guida, dimostreremo come calcolare le formule in Java Slides utilizzando l'API Aspose.Slides per Java. Aspose.Slides è una potente libreria per lavorare con presentazioni PowerPoint e fornisce funzionalità per manipolare grafici ed eseguire calcoli di formule all'interno delle diapositive.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Ambiente di sviluppo Java
-  Aspose.Slides per la libreria Java (puoi scaricarla da[Qui](https://releases.aspose.com/slides/java/)
- Conoscenza base della programmazione Java

## Passaggio 1: crea una nuova presentazione

Innanzitutto, creiamo una nuova presentazione PowerPoint e aggiungiamovi una diapositiva. In questo esempio lavoreremo con una singola diapositiva.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi un grafico alla diapositiva

Ora aggiungiamo un istogramma in cluster alla diapositiva. Utilizzeremo questo grafico per dimostrare i calcoli delle formule.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Passaggio 3: impostare formule e valori

Successivamente, imposteremo formule e valori per le celle di dati del grafico utilizzando l'API Aspose.Slides. Calcoleremo le formule per queste celle.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Imposta la formula per la cella A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Imposta il valore per la cella A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Imposta la formula per la cella B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Imposta la formula per la cella C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Imposta nuovamente la formula per la cella A1
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Passaggio 4: salva la presentazione

Infine, salviamo la presentazione modificata con le formule calcolate.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Codice sorgente completo per calcolare le formule nelle diapositive Java

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questa guida, abbiamo imparato come calcolare le formule in Java Slides utilizzando Aspose.Slides per Java. Abbiamo creato una nuova presentazione, aggiunto un grafico, impostato formule e valori per le celle di dati del grafico e salvato la presentazione con le formule calcolate.

## Domande frequenti

### Come posso impostare le formule per le celle di dati del grafico?

 Puoi impostare le formule per le celle di dati del grafico utilizzando`setFormula` metodo di`IChartDataCell` in Aspose.Slides.

### Come posso impostare i valori per le celle dei dati del grafico?

 È possibile impostare i valori per le celle di dati del grafico utilizzando il comando`setValue` metodo di`IChartDataCell` in Aspose.Slides.

### Come si calcolano le formule in una cartella di lavoro?

 È possibile calcolare le formule in una cartella di lavoro utilizzando il file`calculateFormulas` metodo di`IChartDataWorkbook` in Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
