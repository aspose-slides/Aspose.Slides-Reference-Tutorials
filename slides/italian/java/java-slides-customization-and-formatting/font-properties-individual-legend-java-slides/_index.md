---
title: Proprietà dei caratteri per la legenda individuale nelle diapositive Java
linktitle: Proprietà dei caratteri per la legenda individuale nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Migliora le presentazioni PowerPoint con stili di carattere, dimensioni e colori personalizzati per le singole legende in Diapositive Java utilizzando Aspose.Slides per Java.
weight: 12
url: /it/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione alle proprietà dei caratteri per le singole legende nelle diapositive Java

In questo tutorial, esploreremo come impostare le proprietà del carattere per una singola legenda in Java Slides utilizzando Aspose.Slides per Java. Personalizzando le proprietà del carattere, puoi rendere le tue legende più accattivanti e informative nelle tue presentazioni PowerPoint.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java integrata nel tuo progetto. Puoi scaricarlo da[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: inizializza la presentazione e aggiungi grafico

Innanzitutto, iniziamo inizializzando una presentazione PowerPoint e aggiungendovi un grafico. In questo esempio, utilizzeremo un istogramma a colonne raggruppate come illustrazione.

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

 Sostituire`"Your Document Directory"` con la directory effettiva in cui si trova il documento PowerPoint.

## Passaggio 2: personalizzare le proprietà dei caratteri per la legenda

Ora personalizziamo le proprietà del carattere per una singola voce della legenda all'interno del grafico. In questo esempio, stiamo prendendo di mira la seconda voce della legenda (indice 1), ma puoi modificare l'indice in base ai tuoi requisiti specifici.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Ecco cosa fa ogni riga di codice:

- `get_Item(1)` recupera la seconda voce della legenda (indice 1). È possibile modificare l'indice per scegliere come target una voce della legenda diversa.
- `setFontBold(NullableBool.True)` imposta il carattere in grassetto.
- `setFontHeight(20)` imposta la dimensione del carattere su 20 punti.
- `setFontItalic(NullableBool.True)` imposta il carattere in corsivo.
- `setFillType(FillType.Solid)` specifica che il testo della voce della legenda deve avere un riempimento continuo.
- `getSolidFillColor().setColor(Color.BLUE)` imposta il colore di riempimento su blu. Puoi sostituire`Color.BLUE` con il colore desiderato.

## Passaggio 3: salva la presentazione modificata

Infine, salva la presentazione modificata in un nuovo file per preservare le modifiche.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Sostituire`"output.pptx"` con il nome del file di output preferito.

Questo è tutto! Hai personalizzato con successo le proprietà del carattere per una singola voce della legenda in una presentazione di Diapositive Java utilizzando Aspose.Slides per Java.

## Codice sorgente completo per le proprietà dei caratteri per la legenda individuale nelle diapositive Java

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

In questo tutorial, abbiamo imparato come personalizzare le proprietà del carattere per una singola legenda in Java Slides utilizzando Aspose.Slides per Java. Regolando gli stili, le dimensioni e i colori dei caratteri, puoi migliorare l'attrattiva visiva e la chiarezza delle tue presentazioni PowerPoint.

## Domande frequenti

### Come posso cambiare il colore del carattere?

 Per cambiare il colore del carattere, utilizzare`tf.getPortionFormat().getFontColor().setColor(yourColor)` invece di cambiare il colore di riempimento. Sostituire`yourColor` con il colore del carattere desiderato.

### Come posso modificare le altre proprietà della legenda?

Puoi modificare varie altre proprietà della legenda, come posizione, dimensione e formato. Fare riferimento alla documentazione Aspose.Slides per Java per informazioni dettagliate sull'utilizzo delle legende.

### Posso applicare queste modifiche a più voci della legenda?

 Sì, puoi scorrere le voci della legenda e applicare queste modifiche a più voci regolando l'indice`get_Item(index)` e ripetendo il codice di personalizzazione.

Ricordati di eliminare l'oggetto di presentazione quando hai finito di rilasciare le risorse:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
