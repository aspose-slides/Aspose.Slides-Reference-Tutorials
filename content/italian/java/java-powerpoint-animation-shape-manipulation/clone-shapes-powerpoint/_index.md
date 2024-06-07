---
title: Clonare forme in PowerPoint
linktitle: Clonare forme in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come clonare forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Semplifica il tuo flusso di lavoro con questo tutorial facile da seguire.
type: docs
weight: 16
url: /it/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---
## introduzione
In questo tutorial esploreremo come clonare forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. La clonazione delle forme consente di duplicare forme esistenti all'interno di una presentazione, il che può essere particolarmente utile per creare layout coerenti o ripetere elementi tra diapositive.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere Java Development Kit installato sul tuo sistema. È possibile scaricare e installare la versione più recente da[sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Libreria Aspose.Slides per Java: scarica e includi la libreria Aspose.Slides per Java nel tuo progetto Java. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, dovrai importare i pacchetti necessari nel tuo progetto Java. Questi pacchetti forniscono le funzionalità necessarie per lavorare con presentazioni PowerPoint utilizzando Aspose.Slides per Java.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Passaggio 1: caricare la presentazione
 Per prima cosa devi caricare la presentazione PowerPoint contenente le forme che desideri clonare. Usa il`Presentation` class per caricare la presentazione di origine.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Passaggio 2: clona le forme
Successivamente, clonerai le forme dalla presentazione di origine e le aggiungerai a una nuova diapositiva nella stessa presentazione. Ciò comporta l'accesso alle forme di origine, la creazione di una nuova diapositiva e quindi l'aggiunta delle forme clonate alla nuova diapositiva.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Passaggio 3: salva la presentazione
Infine, salva la presentazione modificata con le forme clonate in un nuovo file.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Conclusione
La clonazione di forme nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java è un processo semplice che può aiutare a semplificare il flusso di lavoro di creazione della presentazione. Seguendo i passaggi descritti in questo tutorial, puoi facilmente duplicare le forme esistenti e personalizzarle secondo necessità.

## Domande frequenti
### Posso clonare forme su diapositive diverse?
Sì, puoi clonare forme da qualsiasi diapositiva della presentazione e aggiungerle a un'altra diapositiva utilizzando Aspose.Slides per Java.
### Esistono limitazioni alla clonazione delle forme?
Sebbene Aspose.Slides per Java offra solide funzionalità di clonazione, forme o animazioni complesse potrebbero non essere replicate perfettamente.
### Posso modificare le forme clonate dopo averle aggiunte a una diapositiva?
Assolutamente, una volta clonate e aggiunte le forme a una diapositiva, puoi modificarne le proprietà, lo stile e il contenuto come richiesto.
### Aspose.Slides per Java supporta la clonazione di altri elementi oltre alle forme?
Sì, puoi clonare diapositive, testo, immagini e altri elementi all'interno di una presentazione PowerPoint utilizzando Aspose.Slides per Java.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.Slides per Java da[sito web](https://releases.aspose.com/slides/java/).