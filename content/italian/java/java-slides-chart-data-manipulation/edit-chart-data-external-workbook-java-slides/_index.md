---
title: Modifica i dati del grafico nella cartella di lavoro esterna in Diapositive Java
linktitle: Modifica i dati del grafico nella cartella di lavoro esterna in Diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come modificare i dati del grafico in una cartella di lavoro esterna utilizzando Aspose.Slides per Java. Guida passo passo con il codice sorgente.
type: docs
weight: 17
url: /it/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Introduzione alla modifica dei dati del grafico nella cartella di lavoro esterna nelle diapositive Java

In questa guida, dimostreremo come modificare i dati del grafico in una cartella di lavoro esterna utilizzando Aspose.Slides per Java. Imparerai come modificare i dati del grafico all'interno di una presentazione di PowerPoint a livello di programmazione. Assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto.

## Prerequisiti

- Aspose.Slides per Java
- Ambiente di sviluppo Java

## Passaggio 1: caricare la presentazione

 Per prima cosa dobbiamo caricare la presentazione PowerPoint che contiene il grafico di cui vogliamo modificare i dati. Sostituire`"Your Document Directory"` con il percorso effettivo del file di presentazione.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Passaggio 2: accedi al grafico

Una volta caricata la presentazione, dobbiamo accedere al grafico all'interno della presentazione. In questo esempio presupponiamo che il grafico si trovi sulla prima diapositiva e che sia la prima forma su tale diapositiva.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Passaggio 3: modifica i dati del grafico

Ora modifichiamo i dati del grafico. Ci concentreremo sulla modifica di un punto dati specifico nel grafico. In questo esempio, impostiamo il valore del primo punto dati nella prima serie su 100. Puoi modificare questo valore secondo necessità.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Passaggio 4: salva la presentazione

Dopo aver apportato le modifiche necessarie ai dati del grafico, salva la presentazione modificata in un nuovo file. È possibile specificare il percorso e il formato del file di output in base alle proprie esigenze.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Passaggio 5: pulizia

Non dimenticare di eliminare l'oggetto di presentazione per liberare eventuali risorse.

```java
if (pres != null) pres.dispose();
```

Ora hai modificato con successo i dati del grafico in una cartella di lavoro esterna all'interno della presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare questo codice per adattarlo alle tue esigenze specifiche e integrarlo nelle tue applicazioni Java.

## Codice sorgente completo

```java
        // Presta attenzione: il percorso della cartella di lavoro esterna difficilmente viene salvato nella presentazione
        // quindi copia il file externalWorkbook.xlsx dalla directory Data/Charts D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ prima di eseguire l'esempio
        // Il percorso della directory dei documenti.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save(RunExamples.getOutPath() + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusione

In questa guida completa, abbiamo esplorato come modificare i dati del grafico in cartelle di lavoro esterne all'interno di presentazioni PowerPoint utilizzando Aspose.Slides per Java. Seguendo le istruzioni dettagliate e gli esempi di codice sorgente, hai acquisito le conoscenze e le competenze per modificare facilmente i dati del grafico a livello di codice.

## Domande frequenti

### Come faccio a specificare un grafico o una diapositiva diversa?

 Per accedere a un grafico o una diapositiva diversa, modificare l'indice appropriato nel file`getSlides().get_Item()` E`getShapes().get_Item()` metodi. Ricorda che l'indicizzazione inizia da 0.

### Posso modificare i dati in più grafici all'interno della stessa presentazione?

Sì, puoi modificare i dati in più grafici all'interno della stessa presentazione ripetendo i passaggi di modifica dei dati del grafico per ciascun grafico.

### Cosa succede se desidero modificare i dati in una cartella di lavoro esterna con un formato diverso?

È possibile adattare il codice per gestire diversi formati di cartelle di lavoro esterne utilizzando le classi e i metodi Aspose.Cells appropriati per leggere e scrivere dati in tale formato.

### Come posso automatizzare questo processo per più presentazioni?

È possibile creare un ciclo per elaborare più presentazioni, caricandole ciascuna, apportando le modifiche desiderate e salvando le presentazioni modificate una per una.