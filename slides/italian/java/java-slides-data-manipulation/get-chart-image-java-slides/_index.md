---
title: Ottieni l'immagine del grafico nelle diapositive Java
linktitle: Ottieni l'immagine del grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come ottenere immagini di grafici in Java Slides utilizzando Aspose.Slides per Java. Questa guida passo passo fornisce il codice sorgente e suggerimenti per un'integrazione perfetta.
weight: 19
url: /it/java/data-manipulation/get-chart-image-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione a come ottenere l'immagine del grafico nelle diapositive Java

Aspose.Slides per Java è una potente libreria che ti consente di lavorare con presentazioni PowerPoint a livello di codice. Con questa libreria puoi creare, manipolare ed estrarre vari elementi dalle presentazioni, inclusi i grafici. Un requisito comune è ottenere immagini di grafici dalle diapositive e in questa guida dimostreremo come farlo.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java scaricata e configurata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: imposta il tuo progetto

Inizia creando un progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito. Assicurati di aver aggiunto la libreria Aspose.Slides per Java alle dipendenze del tuo progetto.

## Passaggio 2: inizializzare la presentazione

Per iniziare, è necessario inizializzare una presentazione di PowerPoint. In questo esempio presupponiamo che tu abbia un file PowerPoint denominato "test.pptx" nella directory dei documenti.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Passaggio 3: aggiungi un grafico e ottieni l'immagine

Successivamente, puoi aggiungere un grafico a una diapositiva e ottenerne l'immagine. In questo esempio aggiungeremo un istogramma a colonne raggruppate.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

In questo frammento di codice creiamo un istogramma raggruppato sulla prima diapositiva della presentazione e quindi otteniamo la sua immagine in miniatura. L'immagine viene salvata come "image.png" nella directory specificata.

## Codice sorgente completo per ottenere l'immagine del grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

Ottenere immagini di grafici da Java Slides utilizzando Aspose.Slides per Java è un processo semplice. Con il codice fornito, puoi facilmente integrare questa funzionalità nelle tue applicazioni Java, permettendoti di lavorare in modo efficace con le presentazioni PowerPoint.

## Domande frequenti

### Come installo Aspose.Slides per Java?

 Installare Aspose.Slides per Java è semplice. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/) e seguire le istruzioni di installazione fornite nella documentazione.

### Posso personalizzare il grafico prima di ottenerne l'immagine?

Sì, puoi personalizzare l'aspetto, i dati e altre proprietà del grafico prima di ottenerne l'immagine. Aspose.Slides per Java offre ampie opzioni per la personalizzazione del grafico.

### Quali altre funzionalità offre Aspose.Slides per Java?

Aspose.Slides per Java offre un'ampia gamma di funzionalità per lavorare con presentazioni PowerPoint, tra cui la creazione di diapositive, la manipolazione del testo, la modifica delle forme e molto altro. È possibile esplorare la documentazione per informazioni dettagliate.

### Aspose.Slides per Java è adatto per l'uso commerciale?

Sì, Aspose.Slides per Java può essere utilizzato per scopi commerciali. Fornisce opzioni di licenza adatte sia ai singoli sviluppatori che alle aziende.

### Posso salvare l'immagine della carta in un formato diverso?

 Certamente! Puoi salvare l'immagine della carta in vari formati, come JPEG o GIF, specificando l'estensione file appropriata nel file`ImageIO.write` metodo.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
