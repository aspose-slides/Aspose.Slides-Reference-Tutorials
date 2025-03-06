---
title: Legenda della dimensione del carattere nelle diapositive Java
linktitle: Legenda della dimensione del carattere nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Migliora le presentazioni PowerPoint con Aspose.Slides per Java. Scopri come personalizzare le dimensioni dei caratteri della legenda e altro ancora nella nostra guida passo passo.
weight: 13
url: /it/java/chart-elements/font-size-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione alla legenda delle dimensioni dei caratteri nelle diapositive Java

In questo tutorial imparerai come personalizzare la dimensione del carattere della legenda in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java. Forniremo istruzioni dettagliate e codice sorgente per raggiungere questo obiettivo.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: inizializzare la presentazione

Innanzitutto, importa le classi necessarie e inizializza la presentazione di PowerPoint.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Sostituire`"Your Document Directory"` con il percorso effettivo del file PowerPoint.

## Passaggio 2: aggiungi un grafico

Successivamente, aggiungeremo un grafico alla diapositiva e imposteremo la dimensione del carattere della legenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 In questo codice creiamo un istogramma raggruppato sulla prima diapositiva e impostiamo la dimensione del carattere del testo della legenda su 20 punti. Puoi regolare il`setFontHeight`valore per modificare la dimensione del carattere secondo necessità.

## Passaggio 3: personalizzare i valori degli assi

Ora personalizziamo i valori dell'asse verticale del grafico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Qui impostiamo i valori minimo e massimo per l'asse verticale. È possibile modificare i valori in base ai requisiti dei dati.

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

## Codice sorgente completo per la legenda della dimensione del carattere nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

Hai personalizzato con successo la dimensione del carattere della legenda in una diapositiva Java PowerPoint utilizzando Aspose.Slides per Java. Puoi esplorare ulteriormente le capacità di Aspose.Slides per creare presentazioni interattive e visivamente accattivanti.

## Domande frequenti

### Come posso modificare la dimensione del carattere del testo della legenda in un grafico?

Per modificare la dimensione del carattere del testo della legenda in un grafico, puoi utilizzare il seguente codice:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 In questo codice creiamo un grafico e impostiamo la dimensione del carattere del testo della legenda su 20 punti. Puoi regolare il`setFontHeight` valore per modificare la dimensione del carattere.

### Posso personalizzare altre proprietà della legenda in un grafico?

Sì, puoi personalizzare varie proprietà della legenda in un grafico utilizzando Aspose.Slides. Alcune delle proprietà comuni che puoi personalizzare includono la formattazione del testo, la posizione, la visibilità e altro ancora. Ad esempio, per modificare la posizione della legenda, puoi utilizzare:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Questo codice imposta la legenda in modo che venga visualizzata nella parte inferiore del grafico. Esplora la documentazione di Aspose.Slides per ulteriori opzioni di personalizzazione.

### Come posso impostare i valori minimo e massimo per l'asse verticale in un grafico?

Per impostare i valori minimo e massimo per l'asse verticale in un grafico, puoi utilizzare il seguente codice:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Qui disabilitiamo il ridimensionamento automatico dell'asse e specifichiamo i valori minimo e massimo per l'asse verticale. Regola i valori secondo necessità per i dati del grafico.

### Dove posso trovare ulteriori informazioni e documentazione per Aspose.Slides?

 È possibile trovare documentazione completa e riferimenti API per Aspose.Slides per Java sul sito Web della documentazione di Aspose. Visita[Qui](https://reference.aspose.com/slides/java/) per informazioni dettagliate sull'utilizzo della libreria.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
