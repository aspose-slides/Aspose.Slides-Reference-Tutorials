---
"description": "Migliora le presentazioni di PowerPoint con stili, dimensioni e colori di carattere personalizzati per le singole legende in Java Slides utilizzando Aspose.Slides per Java."
"linktitle": "Proprietà del carattere per la legenda individuale nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Proprietà del carattere per la legenda individuale nelle diapositive Java"
"url": "/it/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Proprietà del carattere per la legenda individuale nelle diapositive Java


## Introduzione alle proprietà dei caratteri per le singole legende nelle diapositive Java

In questo tutorial, esploreremo come impostare le proprietà del carattere per una singola legenda in Java Slides utilizzando Aspose.Slides per Java. Personalizzando le proprietà del carattere, puoi rendere le tue legende visivamente più accattivanti e informative nelle tue presentazioni PowerPoint.

## Prerequisiti

Prima di iniziare, assicurati di aver integrato la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricarla da [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: inizializzare la presentazione e aggiungere il grafico

Per prima cosa, iniziamo inizializzando una presentazione PowerPoint e aggiungendovi un grafico. In questo esempio, useremo un istogramma a colonne raggruppate come esempio.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Il resto del codice va qui
} finally {
    if (pres != null) pres.dispose();
}
```

Sostituire `"Your Document Directory"` con la directory effettiva in cui si trova il documento PowerPoint.

## Passaggio 2: personalizzare le proprietà del carattere per la legenda

Ora personalizziamo le proprietà del carattere per una singola voce della legenda all'interno del grafico. In questo esempio, ci stiamo concentrando sulla seconda voce della legenda (indice 1), ma è possibile modificare l'indice in base alle proprie esigenze specifiche.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Ecco cosa fa ogni riga di codice:

- `get_Item(1)` Recupera la seconda voce della legenda (indice 1). È possibile modificare l'indice per individuare una voce diversa della legenda.
- `setFontBold(NullableBool.True)` imposta il carattere in grassetto.
- `setFontHeight(20)` imposta la dimensione del carattere a 20 punti.
- `setFontItalic(NullableBool.True)` imposta il carattere in corsivo.
- `setFillType(FillType.Solid)` specifica che il testo della voce della legenda deve avere un riempimento pieno.
- `getSolidFillColor().setColor(Color.BLUE)` imposta il colore di riempimento su blu. Puoi sostituire `Color.BLUE` con il colore desiderato.

## Passaggio 3: salvare la presentazione modificata

Infine, salva la presentazione modificata in un nuovo file per conservare le modifiche.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Sostituire `"output.pptx"` con il nome di file di output preferito.

Ecco fatto! Hai personalizzato con successo le proprietà del carattere per una singola voce della legenda in una presentazione Java Slides utilizzando Aspose.Slides per Java.

## Codice sorgente completo per le proprietà dei caratteri per le singole legende nelle diapositive Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato a personalizzare le proprietà del carattere per una singola legenda in Java Slides utilizzando Aspose.Slides per Java. Regolando stili, dimensioni e colori del carattere, è possibile migliorare l'aspetto visivo e la chiarezza delle presentazioni PowerPoint.

## Domande frequenti

### Come posso cambiare il colore del carattere?

Per cambiare il colore del carattere, utilizzare `tf.getPortionFormat().getFontColor().setColor(yourColor)` invece di cambiare il colore di riempimento. Sostituisci `yourColor` con il colore del carattere desiderato.

### Come posso modificare altre proprietà della legenda?

È possibile modificare diverse altre proprietà della legenda, come posizione, dimensione e formato. Per informazioni dettagliate sull'utilizzo delle legende, consultare la documentazione di Aspose.Slides per Java.

### Posso applicare queste modifiche a più voci della legenda?

Sì, puoi scorrere le voci della legenda e applicare queste modifiche a più voci regolando l'indice in `get_Item(index)` e ripetendo il codice di personalizzazione.

Ricordati di eliminare l'oggetto presentazione una volta terminato di rilasciare risorse:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}