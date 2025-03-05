---
title: Imposta il numero di punti elenco personalizzati in Java PowerPoint
linktitle: Imposta il numero di punti elenco personalizzati in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare numeri di punti elenco personalizzati in Java PowerPoint con Aspose.Slides, migliorando la chiarezza e la struttura della presentazione a livello di codice.
type: docs
weight: 15
url: /it/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## introduzione
Nell'era digitale di oggi, la creazione di presentazioni dinamiche è fondamentale per comunicare in modo efficace idee e dati. Aspose.Slides per Java fornisce un potente toolkit per manipolare le presentazioni PowerPoint a livello di codice, offrendo funzionalità estese per migliorare il processo di creazione delle presentazioni. Questo articolo approfondisce l'impostazione di numeri di punti elenco personalizzati nelle presentazioni Java PowerPoint utilizzando Aspose.Slides. Che tu sia uno sviluppatore esperto o un nuovo arrivato, questo tutorial ti guiderà passo dopo passo attraverso il processo, assicurandoti di poter sfruttare questa funzionalità in modo efficiente.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti configurati nel tuo ambiente di sviluppo:
- Kit di sviluppo Java (JDK) installato
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/)
- Conoscenza di base del linguaggio di programmazione Java e dei concetti orientati agli oggetti

## Importa pacchetti
Innanzitutto, importa le classi Aspose.Slides necessarie e altre librerie standard Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: crea un oggetto di presentazione
Inizia creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Passaggio 2: aggiungi una forma automatica con testo
Inserisci una forma automatica (rettangolo) sulla diapositiva e accedi alla sua cornice di testo.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Passaggio 3: rimuovere il paragrafo predefinito
Rimuove il paragrafo esistente predefinito dalla cornice di testo.
```java
textFrame.getParagraphs().removeAt(0);
```
## Passaggio 4: aggiungi elenchi puntati numerati
Aggiungi paragrafi con punti elenco numerati personalizzati a partire da numeri specifici.
```java
// Paragrafo di esempio con punto elenco che inizia da 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Paragrafo di esempio con punto elenco che inizia da 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Paragrafo di esempio con punto elenco a partire da 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Passaggio 5: salva la presentazione
Infine, salva la presentazione modificata nella posizione desiderata.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Conclusione
In conclusione, Aspose.Slides per Java semplifica il processo di impostazione dei numeri di punti elenco personalizzati nelle presentazioni di PowerPoint a livello di programmazione. Seguendo i passaggi delineati in questo tutorial, puoi migliorare in modo efficiente la chiarezza visiva e la struttura delle tue presentazioni.
## Domande frequenti
### Posso personalizzare ulteriormente l'aspetto dei punti elenco?
Sì, Aspose.Slides offre ampie opzioni per personalizzare il tipo, le dimensioni, il colore dei proiettili e altro ancora.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta i formati PowerPoint dal 97-2003 alle versioni più recenti.
### Come posso ottenere supporto tecnico per Aspose.Slides?
 Visita[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per assistenza tecnica.
### Posso provare Aspose.Slides prima dell'acquisto?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso acquistare Aspose.Slides?
 È possibile acquistare Aspose.Slides da[Qui](https://purchase.aspose.com/buy).