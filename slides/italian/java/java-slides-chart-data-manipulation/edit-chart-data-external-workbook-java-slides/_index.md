---
"description": "Scopri come modificare i dati di un grafico in una cartella di lavoro esterna utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente."
"linktitle": "Modificare i dati del grafico nella cartella di lavoro esterna in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Modificare i dati del grafico nella cartella di lavoro esterna in Java Slides"
"url": "/it/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Modificare i dati del grafico nella cartella di lavoro esterna in Java Slides


## Introduzione alla modifica dei dati del grafico in una cartella di lavoro esterna in Java Slides

In questa guida, mostreremo come modificare i dati di un grafico in una cartella di lavoro esterna utilizzando Aspose.Slides per Java. Imparerai a modificare i dati di un grafico all'interno di una presentazione PowerPoint a livello di codice. Assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto.

## Prerequisiti

- Aspose.Slides per Java
- Ambiente di sviluppo Java

## Passaggio 1: caricare la presentazione

Per prima cosa, dobbiamo caricare la presentazione di PowerPoint che contiene il grafico di cui vogliamo modificare i dati. Sostituisci `"Your Document Directory"` con il percorso effettivo del file della presentazione.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Passaggio 2: accedi al grafico

Una volta caricata la presentazione, dobbiamo accedere al grafico al suo interno. In questo esempio, supponiamo che il grafico si trovi nella prima diapositiva e che sia la prima forma di quella diapositiva.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Passaggio 3: modificare i dati del grafico

Ora modifichiamo i dati del grafico. Ci concentreremo sulla modifica di un punto dati specifico nel grafico. In questo esempio, impostiamo il valore del primo punto dati della prima serie a 100. È possibile modificare questo valore secondo necessità.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Passaggio 4: salva la presentazione

Dopo aver apportato le modifiche necessarie ai dati del grafico, salva la presentazione modificata in un nuovo file. Puoi specificare il percorso e il formato del file di output in base alle tue esigenze.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Fase 5: Pulizia

Non dimenticare di eliminare l'oggetto presentazione per liberare risorse.

```java
if (pres != null) pres.dispose();
```

Ora hai modificato correttamente i dati del grafico in una cartella di lavoro esterna all'interno della tua presentazione PowerPoint utilizzando Aspose.Slides per Java. Puoi personalizzare questo codice in base alle tue esigenze specifiche e integrarlo nelle tue applicazioni Java.

## Codice sorgente completo

```java
        // Prestare attenzione al fatto che il percorso verso la cartella di lavoro esterna viene difficilmente salvato nella presentazione
        // quindi copiare il file externalWorkbook.xlsx dalla directory Dati/Grafici D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ prima di eseguire l'esempio
        // Percorso verso la directory dei documenti.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusione

In questa guida completa, abbiamo esplorato come modificare i dati dei grafici in cartelle di lavoro esterne all'interno di presentazioni PowerPoint utilizzando Aspose.Slides per Java. Seguendo le istruzioni dettagliate e gli esempi di codice sorgente, hai acquisito le conoscenze e le competenze per modificare i dati dei grafici a livello di codice con facilità.

## Domande frequenti

### Come faccio a specificare un grafico o una diapositiva diversi?

Per accedere a un grafico o a una diapositiva diversa, modificare l'indice appropriato nel `getSlides().get_Item()` E `getShapes().get_Item()` metodi. Ricorda che l'indicizzazione parte da 0.

### Posso modificare i dati in più grafici all'interno della stessa presentazione?

Sì, puoi modificare i dati in più grafici all'interno della stessa presentazione ripetendo i passaggi di modifica dei dati per ogni grafico.

### Cosa succede se voglio modificare i dati in una cartella di lavoro esterna con un formato diverso?

È possibile adattare il codice per gestire diversi formati di cartelle di lavoro esterne utilizzando le classi e i metodi Aspose.Cells appropriati per la lettura e la scrittura dei dati in tale formato.

### Come posso automatizzare questo processo per più presentazioni?

È possibile creare un ciclo per elaborare più presentazioni, caricandone una alla volta, apportando le modifiche desiderate e salvando le presentazioni modificate una alla volta.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}