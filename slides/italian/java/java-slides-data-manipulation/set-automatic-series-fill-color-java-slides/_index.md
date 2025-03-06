---
title: Imposta il colore di riempimento della serie automatica nelle diapositive Java
linktitle: Imposta il colore di riempimento della serie automatica nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare il colore di riempimento delle serie automatiche in Diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per presentazioni dinamiche.
weight: 14
url: /it/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'impostazione del colore di riempimento delle serie automatiche nelle diapositive Java

In questo tutorial, esploreremo come impostare il colore di riempimento delle serie automatiche in Java Slides utilizzando l'API Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che ti consente di creare, manipolare e gestire presentazioni PowerPoint a livello di codice. Al termine di questa guida sarai in grado di creare grafici e impostare i colori di riempimento delle serie automatiche senza sforzo.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Libreria Aspose.Slides per Java aggiunta al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

Ora che abbiamo definito il nostro schema, iniziamo con la guida passo passo.

## Passaggio 1: Introduzione ad Aspose.Slides per Java

Aspose.Slides per Java è un'API Java che consente agli sviluppatori di lavorare con presentazioni PowerPoint. Fornisce un'ampia gamma di funzionalità, tra cui la creazione, la modifica e la manipolazione di diapositive, grafici, forme e altro ancora.

## Passaggio 2: configurazione del progetto Java

Prima di iniziare a scrivere codice, assicurati di aver impostato un progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Assicurati di aggiungere la libreria Aspose.Slides per Java al tuo progetto.

## Passaggio 3: creazione di una presentazione PowerPoint

Per iniziare, crea una nuova presentazione di PowerPoint utilizzando il seguente snippet di codice:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 Sostituire`"Your Document Directory"` con il percorso in cui desideri salvare la presentazione.

## Passaggio 4: aggiunta di un grafico alla presentazione

Successivamente, aggiungiamo un istogramma in cluster alla presentazione. Utilizzeremo il seguente codice per ottenere questo risultato:

```java
// Creazione di un istogramma a colonne raggruppate
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Questo codice crea un istogramma in cluster sulla prima diapositiva della presentazione.

## Passaggio 5: impostazione del colore di riempimento della serie automatica

Ora arriva la parte fondamentale: impostare il colore di riempimento della serie automatica. Eseguiremo l'iterazione delle serie del grafico e imposteremo il formato di riempimento su automatico:

```java
// Impostazione del formato di riempimento delle serie su automatico
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Questo codice garantisce che il colore di riempimento della serie sia impostato su automatico.

## Passaggio 6: salvataggio della presentazione

Per salvare la presentazione, utilizzare il seguente codice:

```java
// Scrivere il file di presentazione su disco
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 Sostituire`"AutoFillSeries_out.pptx"` con il nome file desiderato.

## Codice sorgente completo per impostare il colore di riempimento della serie automatica nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Creazione di un istogramma a colonne raggruppate
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Impostazione del formato di riempimento delle serie su automatico
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Scrivere il file di presentazione su disco
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Congratulazioni! Hai impostato con successo il colore di riempimento della serie automatica in una diapositiva Java utilizzando Aspose.Slides per Java. Ora puoi utilizzare queste conoscenze per creare presentazioni PowerPoint dinamiche e visivamente accattivanti nelle tue applicazioni Java.

## Domande frequenti

### Come posso cambiare il tipo di grafico in uno stile diverso?

 È possibile modificare il tipo di grafico sostituendo`ChartType.ClusteredColumn` con il tipo di grafico desiderato, ad esempio`ChartType.Line` O`ChartType.Pie`.

### Posso personalizzare ulteriormente l'aspetto del grafico?

Sì, puoi personalizzare l'aspetto del grafico modificando varie proprietà del grafico, come colori, caratteri ed etichette.

### Aspose.Slides per Java è adatto per l'uso commerciale?

Sì, Aspose.Slides per Java può essere utilizzato sia per progetti personali che commerciali. È possibile fare riferimento ai termini di licenza per maggiori dettagli.

### Ci sono altre funzionalità fornite da Aspose.Slides per Java?

Sì, Aspose.Slides per Java offre un'ampia gamma di funzionalità, tra cui la manipolazione delle diapositive, la formattazione del testo e il supporto delle animazioni.

### Dove posso trovare ulteriori risorse e documentazione?

 È possibile accedere alla documentazione completa per Aspose.Slides per Java all'indirizzo[Qui](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
