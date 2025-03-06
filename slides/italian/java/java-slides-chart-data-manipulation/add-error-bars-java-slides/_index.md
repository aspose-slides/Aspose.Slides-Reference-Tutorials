---
title: Aggiungi barre di errore nelle diapositive Java
linktitle: Aggiungi barre di errore nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere barre di errore ai grafici PowerPoint in Java utilizzando Aspose.Slides. Guida passo passo con codice sorgente per personalizzare le barre di errore.
weight: 13
url: /it/java/chart-data-manipulation/add-error-bars-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi barre di errore nelle diapositive Java


## Introduzione all'aggiunta di barre di errore nelle diapositive Java utilizzando Aspose.Slides

In questo tutorial, dimostreremo come aggiungere barre di errore a un grafico in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java. Le barre di errore forniscono informazioni preziose sulla variabilità o sull'incertezza dei dati in un grafico. Creeremo un grafico a bolle e vi aggiungeremo delle barre di errore. Iniziamo!

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria da[Sito web Aspose](https://downloads.aspose.com/slides/java).

## Passaggio 1: crea una presentazione vuota

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
```

In questo passaggio creiamo una presentazione vuota in cui aggiungeremo il nostro grafico con le barre di errore.

## Passaggio 2: crea un grafico a bolle

```java
// Creazione di un grafico a bolle
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Qui creiamo un grafico a bolle e ne specifichiamo la posizione e le dimensioni sulla diapositiva.

## Passaggio 3: aggiunta di barre di errore e impostazione del formato

```java
// Aggiunta di barre di errore e impostazione del relativo formato
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

In questo passaggio aggiungiamo le barre di errore al grafico e ne impostiamo il formato. È possibile personalizzare le barre di errore modificando valori, tipi e altre proprietà.

- `errBarX` rappresenta le barre di errore lungo l'asse X.
- `errBarY` rappresenta le barre di errore lungo l'asse Y.
- Rendiamo visibili le barre di errore X e Y.
- `setValueType` specifica il tipo di valore per le barre di errore (ad esempio, Fisso o Percentuale).
- `setValue` imposta il valore per le barre di errore.
- `setType` definisce il tipo di barre di errore (ad esempio, Più o Meno).
-  Impostiamo la larghezza delle linee della barra di errore utilizzando`getFormat().getLine().setWidth(2)`.
- `setEndCap`specifica se includere le estremità finali nelle barre di errore.

## Passaggio 4: salva la presentazione

```java
// Salvataggio della presentazione
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Infine, salviamo la presentazione con le barre di errore aggiunte in una posizione specifica.

Questo è tutto! Hai aggiunto con successo le barre di errore a un grafico in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per aggiungere barre di errore nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
try
{
	// Creazione di un grafico a bolle
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Aggiunta di barre di errore e impostazione del relativo formato
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Salvataggio della presentazione
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come migliorare le tue presentazioni PowerPoint aggiungendo barre di errore ai grafici utilizzando Aspose.Slides per Java. Le barre di errore forniscono informazioni preziose sulla variabilità e sulle incertezze dei dati, rendendo le tue presentazioni più informative e visivamente accattivanti.

## Domande frequenti

### Come posso personalizzare ulteriormente l'aspetto delle barre di errore?

Puoi personalizzare le barre di errore modificandone le proprietà, come stile di linea, colore e larghezza, come dimostrato nel passaggio 3.

### Posso aggiungere barre di errore a diversi tipi di grafici?

Sì, puoi aggiungere barre di errore a vari tipi di grafici supportati da Aspose.Slides per Java. Crea semplicemente il tipo di grafico desiderato e segui gli stessi passaggi di personalizzazione della barra di errore.

### Come posso regolare la posizione e la dimensione del grafico sulla diapositiva?

 Puoi controllare la posizione e le dimensioni del grafico regolando i parametri nel file`addChart` metodo, come mostrato nel passaggio 2.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per Java?

 Puoi fare riferimento a[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/) per informazioni dettagliate sull'utilizzo della libreria.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
