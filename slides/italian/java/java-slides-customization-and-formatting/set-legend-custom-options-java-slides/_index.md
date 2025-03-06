---
title: Imposta le opzioni personalizzate della legenda nelle diapositive Java
linktitle: Imposta le opzioni personalizzate della legenda nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare le opzioni della legenda personalizzata in Diapositive Java utilizzando Aspose.Slides per Java. Personalizza la posizione e le dimensioni della legenda nei grafici PowerPoint.
weight: 14
url: /it/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'impostazione delle opzioni personalizzate della legenda nelle diapositive Java

In questo tutorial, dimostreremo come personalizzare le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi modificare la posizione, le dimensioni e altri attributi della legenda per adattarli alle tue esigenze di presentazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per API Java installata.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: importa le classi necessarie:

```java
// Importa Aspose.Slides per le classi Java
import com.aspose.slides.*;
```

## Passaggio 2: specificare il percorso della directory dei documenti:

```java
String dataDir = "Your Document Directory";
```

##  Passaggio 3: crea un'istanza di`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Passaggio 4: aggiungi una diapositiva alla presentazione:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Passaggio 5: aggiungi un istogramma a colonne raggruppate alla diapositiva:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Passaggio 6. Imposta le proprietà della legenda:

- Imposta la posizione X della legenda (rispetto alla larghezza del grafico):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Imposta la posizione Y della legenda (rispetto all'altezza del grafico):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Imposta la larghezza della legenda (rispetto alla larghezza del grafico):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Imposta l'altezza della legenda (rispetto all'altezza del grafico):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Passaggio 7: salva la presentazione su disco:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Questo è tutto! Hai personalizzato con successo le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per le opzioni personalizzate della legenda impostata nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
try
{
	// Ottieni il riferimento della diapositiva
	ISlide slide = presentation.getSlides().get_Item(0);
	// Aggiungi un istogramma in cluster alla diapositiva
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Imposta le proprietà della legenda
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Scrivi la presentazione su disco
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Conclusione

In questo tutorial, abbiamo imparato come personalizzare le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi modificare la posizione, le dimensioni e altri attributi della legenda per creare presentazioni visivamente accattivanti e informative.

## Domande frequenti

## Come posso cambiare la posizione della legenda?

 Per modificare la posizione della legenda, utilizzare il file`setX` E`setY` metodi dell'oggetto legenda. I valori vengono specificati in relazione alla larghezza e all'altezza del grafico.

## Come posso regolare la dimensione della legenda?

 Puoi regolare la dimensione della legenda utilizzando il comando`setWidth` E`setHeight` metodi dell'oggetto legenda. Questi valori sono anche relativi alla larghezza e all'altezza del grafico.

## Posso personalizzare altri attributi della legenda?

Sì, puoi personalizzare vari attributi della legenda, come lo stile del carattere, il bordo, il colore dello sfondo e altro. Esplora la documentazione di Aspose.Slides per informazioni dettagliate sulla personalizzazione ulteriore delle legende.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
