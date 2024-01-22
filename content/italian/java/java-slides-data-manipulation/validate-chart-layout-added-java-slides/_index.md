---
title: Convalida il layout del grafico aggiunto nelle diapositive Java
linktitle: Convalida il layout del grafico aggiunto nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Convalida del layout del grafico principale in PowerPoint con Aspose.Slides per Java. Impara a manipolare i grafici in modo programmatico per presentazioni straordinarie.
type: docs
weight: 10
url: /it/java/data-manipulation/validate-chart-layout-added-java-slides/
---

## Introduzione alla convalida del layout del grafico in Aspose.Slides per Java

In questo tutorial esploreremo come convalidare il layout del grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questa libreria ti consente di lavorare con le presentazioni PowerPoint a livello di codice, semplificando la manipolazione e la convalida di vari elementi, inclusi i grafici.

## Passaggio 1: inizializzazione della presentazione

Innanzitutto, dobbiamo inizializzare un oggetto di presentazione e caricare una presentazione PowerPoint esistente. Sostituire`"Your Document Directory"` con il percorso effettivo del file di presentazione (`test.pptx` in questo esempio).

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Passaggio 2: aggiunta di un grafico

 Successivamente, aggiungeremo un grafico alla presentazione. In questo esempio stiamo aggiungendo un istogramma a colonne raggruppate, ma puoi modificare il file`ChartType` come necessario.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Passaggio 3: convalida del layout del grafico

 Ora convalideremo il layout del grafico utilizzando il file`validateChartLayout()` metodo. Ciò garantisce che il grafico sia disposto correttamente all'interno della diapositiva.

```java
chart.validateChartLayout();
```

## Passaggio 4: recupero della posizione e delle dimensioni del grafico

Dopo aver convalidato il layout del grafico, potresti voler recuperare informazioni sulla sua posizione e dimensione. Possiamo ottenere le coordinate X e Y effettive, nonché la larghezza e l'altezza dell'area del tracciato del grafico.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Passaggio 5: salvataggio della presentazione

 Infine, non dimenticare di salvare la presentazione modificata. In questo esempio, lo salviamo come`Result.pptx`, ma puoi specificare un nome file diverso, se necessario.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per la convalida del layout del grafico aggiunto nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Salvataggio della presentazione
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo approfondito il mondo del lavoro con i grafici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Abbiamo coperto i passaggi essenziali per convalidare il layout del grafico, recuperarne la posizione e le dimensioni e salvare la presentazione modificata. Ecco un breve riepilogo:

## Domande frequenti

### Come posso cambiare il tipo di grafico?

 Per modificare il tipo di grafico, è sufficiente sostituirlo`ChartType.ClusteredColumn` con il tipo di grafico desiderato nel file`addChart()` metodo.

### Posso personalizzare i dati del grafico?

Sì, puoi personalizzare i dati del grafico aggiungendo e modificando serie, categorie e valori di dati. Fare riferimento alla documentazione di Aspose.Slides per maggiori dettagli.

### Cosa succede se voglio modificare altre proprietà del grafico?

Puoi accedere a varie proprietà del grafico e personalizzarle in base alle tue esigenze. Esplora la documentazione di Aspose.Slides per informazioni complete sulla manipolazione dei grafici.
