---
"description": "Scopri come aggiungere colonne nelle cornici di testo utilizzando Aspose.Slides per Java per migliorare le tue presentazioni PowerPoint. La nostra guida passo passo semplifica il processo."
"linktitle": "Aggiungere colonne nella cornice di testo utilizzando Aspose.Slides per Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere colonne nella cornice di testo utilizzando Aspose.Slides per Java"
"url": "/it/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere colonne nella cornice di testo utilizzando Aspose.Slides per Java

## Introduzione
In questo tutorial, esploreremo come manipolare le cornici di testo per aggiungere colonne utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori Java di creare, manipolare e convertire le presentazioni di PowerPoint a livello di codice. L'aggiunta di colonne alle cornici di testo migliora l'aspetto visivo e l'organizzazione del testo nelle diapositive, rendendo le presentazioni più accattivanti e facili da leggere.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul computer.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
- Conoscenza di base della programmazione Java.
- Ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA.
- Familiarità con la gestione delle dipendenze del progetto utilizzando strumenti come Maven o Gradle.

## Importa pacchetti
Per prima cosa, importa i pacchetti necessari da Aspose.Slides per lavorare con presentazioni e cornici di testo:
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
## Passaggio 2: aggiungere una forma automatica con cornice di testo
Aggiungere una forma automatica (ad esempio un rettangolo) alla prima diapositiva e accedere alla sua cornice di testo:
```java
// Aggiungi una forma automatica alla prima diapositiva
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// Accedi alla cornice di testo dell'AutoShape
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
Salvare la presentazione dopo aver apportato le modifiche:
```java
// Salva la presentazione
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## Passaggio 5: regola la spaziatura delle colonne (facoltativo)
Se necessario, regola la spaziatura tra le colonne:
```java
// Imposta la spaziatura delle colonne
format.setColumnSpacing(20);
// Salva la presentazione con la spaziatura delle colonne aggiornata
pres.save(outPptxFileName, SaveFormat.Pptx);
// Se necessario, puoi modificare nuovamente il numero di colonne e la spaziatura
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo mostrato come utilizzare Aspose.Slides per Java per aggiungere colonne all'interno di cornici di testo nelle presentazioni di PowerPoint tramite codice. Questa funzionalità migliora la presentazione visiva del contenuto testuale, migliorando la leggibilità e la struttura delle diapositive.
## Domande frequenti
### Posso aggiungere più di tre colonne a una cornice di testo?
Sì, puoi regolare il `setColumnCount` metodo per aggiungere altre colonne secondo necessità.
### Aspose.Slides supporta la regolazione individuale della larghezza delle colonne?
No, Aspose.Slides imposta automaticamente la stessa larghezza per le colonne all'interno di una cornice di testo.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi scaricare una versione di prova gratuita [Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
È disponibile la documentazione dettagliata [Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto tecnico per Aspose.Slides per Java?
Puoi cercare supporto dalla comunità [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}