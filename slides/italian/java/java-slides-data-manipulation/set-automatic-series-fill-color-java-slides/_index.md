---
"description": "Scopri come impostare il colore di riempimento automatico delle serie in Java Slides utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice per presentazioni dinamiche."
"linktitle": "Imposta il colore di riempimento automatico delle serie nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta il colore di riempimento automatico delle serie nelle diapositive Java"
"url": "/it/java/data-manipulation/set-automatic-series-fill-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il colore di riempimento automatico delle serie nelle diapositive Java


## Introduzione all'impostazione del colore di riempimento automatico delle serie in Java Slides

In questo tutorial, esploreremo come impostare il colore di riempimento automatico delle serie in Java Slides utilizzando l'API Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che consente di creare, manipolare e gestire le presentazioni di PowerPoint a livello di codice. Al termine di questa guida, sarete in grado di creare grafici e impostare i colori di riempimento automatico delle serie senza sforzo.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- La libreria Aspose.Slides per Java è stata aggiunta al tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

Ora che abbiamo delineato il nostro schema, iniziamo con la guida passo passo.

## Fase 1: Introduzione ad Aspose.Slides per Java

Aspose.Slides per Java è un'API Java che consente agli sviluppatori di lavorare con le presentazioni di PowerPoint. Offre un'ampia gamma di funzionalità, tra cui la creazione, la modifica e la manipolazione di diapositive, grafici, forme e altro ancora.

## Passaggio 2: impostazione del progetto Java

Prima di iniziare a scrivere codice, assicurati di aver configurato un progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Assicurati di aggiungere la libreria Aspose.Slides per Java al tuo progetto.

## Passaggio 3: creazione di una presentazione PowerPoint

Per iniziare, crea una nuova presentazione PowerPoint utilizzando il seguente frammento di codice:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

Sostituire `"Your Document Directory"` con il percorso in cui desideri salvare la presentazione.

## Passaggio 4: aggiunta di un grafico alla presentazione

Ora aggiungiamo un grafico a colonne raggruppate alla presentazione. Per farlo, useremo il seguente codice:

```java
// Creazione di un grafico a colonne raggruppate
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Questo codice crea un grafico a colonne raggruppate nella prima diapositiva della presentazione.

## Passaggio 5: impostazione del colore di riempimento automatico della serie

Ora arriva la parte fondamentale: impostare il colore di riempimento automatico delle serie. Esamineremo le serie del grafico e imposteremo il loro formato di riempimento su automatico:

```java
// Impostazione del formato di riempimento della serie su automatico
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Questo codice garantisce che il colore di riempimento della serie sia impostato su automatico.

## Passaggio 6: salvataggio della presentazione

Per salvare la presentazione, utilizzare il seguente codice:

```java
// Scrivi il file di presentazione sul disco
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

Sostituire `"AutoFillSeries_out.pptx"` con il nome file desiderato.

## Codice sorgente completo per impostare il colore di riempimento automatico delle serie nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Creazione di un grafico a colonne raggruppate
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Impostazione del formato di riempimento della serie su automatico
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Scrivi il file di presentazione sul disco
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

Congratulazioni! Hai impostato correttamente il colore di riempimento automatico delle serie in una diapositiva Java utilizzando Aspose.Slides per Java. Ora puoi utilizzare queste informazioni per creare presentazioni PowerPoint dinamiche e visivamente accattivanti nelle tue applicazioni Java.

## Domande frequenti

### Come posso cambiare il tipo di grafico con uno stile diverso?

È possibile modificare il tipo di grafico sostituendolo `ChartType.ClusteredColumn` con il tipo di grafico desiderato, ad esempio `ChartType.Line` O `ChartType.Pie`.

### Posso personalizzare ulteriormente l'aspetto del grafico?

Sì, puoi personalizzare l'aspetto del grafico modificandone varie proprietà, come colori, caratteri ed etichette.

### Aspose.Slides per Java è adatto all'uso commerciale?

Sì, Aspose.Slides per Java può essere utilizzato sia per progetti personali che commerciali. Per maggiori dettagli, consultare i termini di licenza.

### Aspose.Slides per Java offre altre funzionalità?

Sì, Aspose.Slides per Java offre un'ampia gamma di funzionalità, tra cui la manipolazione delle diapositive, la formattazione del testo e il supporto dell'animazione.

### Dove posso trovare ulteriori risorse e documentazione?

È possibile accedere alla documentazione completa per Aspose.Slides per Java su [Qui](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}