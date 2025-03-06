---
title: Aggiungi colonne nella cornice di testo utilizzando Aspose.Slides per Java
linktitle: Aggiungi colonne nella cornice di testo utilizzando Aspose.Slides per Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere colonne nelle cornici di testo utilizzando Aspose.Slides per Java per migliorare le tue presentazioni PowerPoint. La nostra guida passo passo semplifica il processo.
weight: 11
url: /it/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
In questo tutorial esploreremo come manipolare le cornici di testo per aggiungere colonne utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori Java di creare, manipolare e convertire presentazioni PowerPoint a livello di codice. L'aggiunta di colonne alle cornici di testo migliora l'aspetto visivo e l'organizzazione del testo all'interno delle diapositive, rendendo le presentazioni più coinvolgenti e più facili da leggere.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo computer.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Conoscenza di base della programmazione Java.
- Ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA.
- Familiarità con la gestione delle dipendenze del progetto utilizzando strumenti come Maven o Gradle.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari da Aspose.Slides per lavorare con presentazioni e cornici di testo:
```java
import com.aspose.slides.*;
```
## Passaggio 1: inizializzare la presentazione
Inizia creando un nuovo oggetto di presentazione di PowerPoint:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// Crea un nuovo oggetto di presentazione
Presentation pres = new Presentation();
```
## Passaggio 2: aggiungi una forma automatica con cornice di testo
Aggiungi una forma automatica (ad esempio un rettangolo) alla prima diapositiva e accedi alla sua cornice di testo:
```java
// Aggiungi una forma alla prima diapositiva
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// Accedi alla cornice di testo della forma
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## Passaggio 3: imposta il conteggio delle colonne e il testo
Imposta il numero di colonne e il contenuto del testo all'interno della cornice di testo:
```java
// Imposta il numero di colonne
format.setColumnCount(2);
// Imposta il contenuto del testo
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Passaggio 4: salva la presentazione
Salva la presentazione dopo aver apportato le modifiche:
```java
// Salva la presentazione
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## Passaggio 5: regolare la spaziatura delle colonne (facoltativo)
Se necessario, regola la spaziatura tra le colonne:
```java
// Imposta la spaziatura delle colonne
format.setColumnSpacing(20);
// Salva la presentazione con la spaziatura delle colonne aggiornata
pres.save(outPptxFileName, SaveFormat.Pptx);
// Se necessario, è possibile modificare nuovamente il conteggio delle colonne e la spaziatura
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo dimostrato come utilizzare Aspose.Slides per Java per aggiungere colonne all'interno di cornici di testo nelle presentazioni di PowerPoint a livello di codice. Questa funzionalità migliora la presentazione visiva del contenuto testuale, migliorando la leggibilità e la struttura delle diapositive.
## Domande frequenti
### Posso aggiungere più di tre colonne a una cornice di testo?
 Sì, puoi regolare il`setColumnCount` metodo per aggiungere più colonne secondo necessità.
### Aspose.Slides supporta la regolazione della larghezza delle colonne individualmente?
No, Aspose.Slides imposta automaticamente la stessa larghezza per le colonne all'interno di una cornice di testo.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
 È disponibile la documentazione dettagliata[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto tecnico per Aspose.Slides per Java?
 Puoi chiedere sostegno alla comunità[Qui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
