---
"description": "Migliora le presentazioni di PowerPoint con Aspose.Slides per Java. Scopri come personalizzare le dimensioni dei caratteri della legenda e altro ancora nella nostra guida dettagliata."
"linktitle": "Legenda delle dimensioni del carattere nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Legenda delle dimensioni del carattere nelle diapositive Java"
"url": "/it/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda delle dimensioni del carattere nelle diapositive Java


## Introduzione alla legenda delle dimensioni del carattere in Java Slides

In questo tutorial imparerai come personalizzare la dimensione del carattere della legenda in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java. Forniremo istruzioni dettagliate e il codice sorgente per raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: inizializzare la presentazione

Per prima cosa, importa le classi necessarie e inizializza la presentazione PowerPoint.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Sostituire `"Your Document Directory"` con il percorso effettivo del file PowerPoint.

## Passaggio 2: aggiungere un grafico

Successivamente aggiungeremo un grafico alla diapositiva e imposteremo la dimensione del carattere della legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

In questo codice, creiamo un grafico a colonne raggruppate nella prima diapositiva e impostiamo la dimensione del carattere del testo della legenda a 20 punti. È possibile regolare `setFontHeight` valore per modificare la dimensione del carattere in base alle proprie esigenze.

## Passaggio 3: personalizzare i valori degli assi

Adesso personalizziamo i valori dell'asse verticale del grafico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Qui impostiamo i valori minimo e massimo per l'asse verticale. È possibile modificare i valori in base alle proprie esigenze di dati.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione modificata in un nuovo file.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Questo codice salva la presentazione modificata come "output.pptx" nella directory specificata.

## Codice sorgente completo per la legenda delle dimensioni del carattere nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

Hai personalizzato con successo la dimensione del carattere della legenda in una diapositiva Java di PowerPoint utilizzando Aspose.Slides per Java. Puoi esplorare ulteriormente le funzionalità di Aspose.Slides per creare presentazioni interattive e visivamente accattivanti.

## Domande frequenti

### Come faccio a modificare la dimensione del carattere del testo della legenda in un grafico?

Per modificare la dimensione del carattere del testo della legenda in un grafico, puoi utilizzare il seguente codice:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

In questo codice, creiamo un grafico e impostiamo la dimensione del carattere del testo della legenda a 20 punti. È possibile regolare `setFontHeight` valore per modificare la dimensione del carattere.

### Posso personalizzare altre proprietà della legenda in un grafico?

Sì, puoi personalizzare diverse proprietà della legenda in un grafico utilizzando Aspose.Slides. Alcune delle proprietà più comuni che puoi personalizzare includono la formattazione del testo, la posizione, la visibilità e altro ancora. Ad esempio, per modificare la posizione della legenda, puoi utilizzare:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Questo codice imposta la legenda in modo che appaia in fondo al grafico. Esplora la documentazione di Aspose.Slides per ulteriori opzioni di personalizzazione.

### Come posso impostare i valori minimo e massimo per l'asse verticale in un grafico?

Per impostare i valori minimo e massimo per l'asse verticale in un grafico, puoi utilizzare il seguente codice:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Qui disattiviamo la scala automatica degli assi e specifichiamo i valori minimo e massimo per l'asse verticale. Adatta i valori in base alle tue esigenze in base ai dati del grafico.

### Dove posso trovare maggiori informazioni e documentazione su Aspose.Slides?

Puoi trovare documentazione completa e riferimenti API per Aspose.Slides per Java sul sito web della documentazione di Aspose. Visita [Qui](https://reference.aspose.com/slides/java/) per informazioni dettagliate sull'utilizzo della biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}