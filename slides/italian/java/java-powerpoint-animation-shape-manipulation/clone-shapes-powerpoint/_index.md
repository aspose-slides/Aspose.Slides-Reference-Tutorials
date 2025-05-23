---
"description": "Scopri come clonare le forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Semplifica il tuo flusso di lavoro con questo tutorial facile da seguire."
"linktitle": "Clonare forme in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Clonare forme in PowerPoint"
"url": "/it/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Clonare forme in PowerPoint

## Introduzione
In questo tutorial, esploreremo come clonare le forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. La clonazione delle forme consente di duplicare forme esistenti all'interno di una presentazione, il che può essere particolarmente utile per creare layout coerenti o ripetere elementi tra le diapositive.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di aver installato Java Development Kit sul tuo sistema. Puoi scaricare e installare la versione più recente da [sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Libreria Aspose.Slides per Java: scarica e includi la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi trovare il link per il download. [Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, dovrai importare i pacchetti necessari nel tuo progetto Java. Questi pacchetti forniscono le funzionalità necessarie per lavorare con le presentazioni PowerPoint utilizzando Aspose.Slides per Java.
```java
import com.aspose.slides.*;

```
## Passaggio 1: caricare la presentazione
Per prima cosa, devi caricare la presentazione di PowerPoint contenente le forme che vuoi clonare. Usa il `Presentation` classe per caricare la presentazione sorgente.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Passaggio 2: clonare le forme
Successivamente, clonerai le forme dalla presentazione di origine e le aggiungerai a una nuova diapositiva nella stessa presentazione. Questo significa accedere alle forme di origine, creare una nuova diapositiva e quindi aggiungere le forme clonate alla nuova diapositiva.
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
Clonare forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java è un processo semplice che può contribuire a semplificare il flusso di lavoro di creazione delle presentazioni. Seguendo i passaggi descritti in questo tutorial, è possibile duplicare facilmente forme esistenti e personalizzarle in base alle proprie esigenze.

## Domande frequenti
### Posso clonare le forme in diapositive diverse?
Sì, puoi clonare le forme da qualsiasi diapositiva della presentazione e aggiungerle a un'altra diapositiva utilizzando Aspose.Slides per Java.
### Esistono delle limitazioni alla clonazione delle forme?
Sebbene Aspose.Slides per Java offra solide funzionalità di clonazione, forme o animazioni complesse potrebbero non essere replicate perfettamente.
### Posso modificare le forme clonate dopo averle aggiunte a una diapositiva?
Certamente, una volta clonate e aggiunte le forme a una diapositiva, puoi modificarne le proprietà, lo stile e il contenuto a seconda delle tue esigenze.
### Aspose.Slides per Java supporta la clonazione di altri elementi oltre alle forme?
Sì, puoi clonare diapositive, testo, immagini e altri elementi all'interno di una presentazione PowerPoint utilizzando Aspose.Slides per Java.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi scaricare una versione di prova gratuita di Aspose.Slides per Java da [sito web](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}