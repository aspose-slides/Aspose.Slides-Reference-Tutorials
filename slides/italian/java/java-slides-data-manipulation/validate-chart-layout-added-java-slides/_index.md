---
"description": "Convalida il layout dei grafici in PowerPoint con Aspose.Slides per Java. Impara a manipolare i grafici programmaticamente per creare presentazioni di grande impatto."
"linktitle": "Convalida layout grafico aggiunto in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Convalida layout grafico aggiunto in Java Slides"
"url": "/it/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convalida layout grafico aggiunto in Java Slides


## Introduzione alla convalida del layout del grafico in Aspose.Slides per Java

In questo tutorial, esploreremo come convalidare il layout del grafico in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Questa libreria consente di lavorare con le presentazioni PowerPoint a livello di codice, semplificando la manipolazione e la convalida di vari elementi, inclusi i grafici.

## Fase 1: Inizializzazione della presentazione

Per prima cosa, dobbiamo inizializzare un oggetto presentazione e caricare una presentazione PowerPoint esistente. Sostituisci `"Your Document Directory"` con il percorso effettivo del file di presentazione (`test.pptx` in questo esempio).

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Passaggio 2: aggiunta di un grafico

Successivamente, aggiungeremo un grafico alla presentazione. In questo esempio, stiamo aggiungendo un grafico a colonne raggruppate, ma è possibile modificare il `ChartType` secondo necessità.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Passaggio 3: convalida del layout del grafico

Ora, convalideremo il layout del grafico utilizzando `validateChartLayout()` metodo. In questo modo si garantisce che il grafico sia disposto correttamente all'interno della diapositiva.

```java
chart.validateChartLayout();
```

## Passaggio 4: recupero della posizione e delle dimensioni del grafico

Dopo aver convalidato il layout del grafico, potresti voler recuperare informazioni sulla sua posizione e dimensione. Possiamo ottenere le coordinate X e Y effettive, nonché la larghezza e l'altezza dell'area del grafico.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Passaggio 5: salvataggio della presentazione

Infine, non dimenticare di salvare la presentazione modificata. In questo esempio, la salviamo come `Result.pptx`, ma se necessario puoi specificare un nome file diverso.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per il layout del grafico di convalida aggiunto in Java Slides

```java
// Percorso verso la directory dei documenti.
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

In questo tutorial, abbiamo approfondito l'utilizzo dei grafici nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Abbiamo illustrato i passaggi essenziali per convalidare il layout del grafico, recuperarne posizione e dimensioni e salvare la presentazione modificata. Ecco un breve riepilogo:

## Domande frequenti

### Come faccio a cambiare il tipo di grafico?

Per cambiare il tipo di grafico, è sufficiente sostituire `ChartType.ClusteredColumn` con il tipo di grafico desiderato nel `addChart()` metodo.

### Posso personalizzare i dati del grafico?

Sì, è possibile personalizzare i dati del grafico aggiungendo e modificando serie di dati, categorie e valori. Per maggiori dettagli, consultare la documentazione di Aspose.Slides.

### Cosa succede se voglio modificare altre proprietà del grafico?

Puoi accedere a diverse proprietà dei grafici e personalizzarle in base alle tue esigenze. Esplora la documentazione di Aspose.Slides per informazioni complete sulla manipolazione dei grafici.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}