---
"description": "Scopri come impostare opzioni di legenda personalizzate in Java Slides utilizzando Aspose.Slides per Java. Personalizza posizione e dimensioni della legenda nei grafici di PowerPoint."
"linktitle": "Imposta le opzioni personalizzate della legenda nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta le opzioni personalizzate della legenda nelle diapositive Java"
"url": "/it/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta le opzioni personalizzate della legenda nelle diapositive Java


## Introduzione alle opzioni personalizzate di impostazione della legenda in Java Slides

In questo tutorial, mostreremo come personalizzare le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. È possibile modificare la posizione, le dimensioni e altri attributi della legenda in base alle esigenze della presentazione.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Installata l'API Aspose.Slides per Java.
- Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: importare le classi necessarie:

```java
// Importa Aspose.Slides per le classi Java
import com.aspose.slides.*;
```

## Passaggio 2: specificare il percorso della directory del documento:

```java
String dataDir = "Your Document Directory";
```

## Passaggio 3: creare un'istanza di `Presentation` classe:

```java
Presentation presentation = new Presentation();
```

## Passaggio 4: aggiungere una diapositiva alla presentazione:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Passaggio 5: aggiungere un grafico a colonne raggruppate alla diapositiva:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Passaggio 6. Imposta le proprietà della legenda:

- Imposta la posizione X della legenda (relativa alla larghezza del grafico):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Imposta la posizione Y della legenda (relativa all'altezza del grafico):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Imposta la larghezza della legenda (relativamente alla larghezza del grafico):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Imposta l'altezza della legenda (relativamente all'altezza del grafico):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Passaggio 7: Salvare la presentazione sul disco:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Ecco fatto! Hai personalizzato con successo le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per impostare le opzioni personalizzate della legenda in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
try
{
	// Ottieni il riferimento della diapositiva
	ISlide slide = presentation.getSlides().get_Item(0);
	// Aggiungere un grafico a colonne raggruppate alla diapositiva
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Imposta proprietà legenda
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

In questo tutorial, abbiamo imparato a personalizzare le proprietà della legenda di un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. È possibile modificare la posizione, le dimensioni e altri attributi della legenda per creare presentazioni visivamente accattivanti e informative.

## Domande frequenti

## Come posso modificare la posizione della legenda?

Per modificare la posizione della legenda, utilizzare `setX` E `setY` metodi dell'oggetto legenda. I valori sono specificati in relazione alla larghezza e all'altezza del grafico.

## Come posso regolare le dimensioni della legenda?

È possibile regolare la dimensione della legenda utilizzando `setWidth` E `setHeight` metodi dell'oggetto legenda. Questi valori sono anche relativi alla larghezza e all'altezza del grafico.

## Posso personalizzare altri attributi della legenda?

Sì, puoi personalizzare vari attributi della legenda, come lo stile del carattere, il bordo, il colore di sfondo e altro ancora. Consulta la documentazione di Aspose.Slides per informazioni dettagliate sulla personalizzazione delle legende.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}