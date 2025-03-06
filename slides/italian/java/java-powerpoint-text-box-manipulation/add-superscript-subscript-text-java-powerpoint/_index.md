---
title: Aggiungi testo in apice e pedice in Java PowerPoint
linktitle: Aggiungi testo in apice e pedice in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere testo in apice e pedice nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per Java. Perfetto per migliorare le tue diapositive.
weight: 13
url: /it/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
La creazione di presentazioni PowerPoint accattivanti e informative richiede spesso l'uso di funzionalità di formattazione come il testo in apice e pedice. Questo tutorial ti guiderà attraverso il processo di incorporazione del testo in apice e pedice nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse configurato per lo sviluppo Java.
- Familiarità di base con la programmazione Java e presentazioni PowerPoint.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari da Aspose.Slides per Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: impostare la presentazione
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Passaggio 2: accedi alla diapositiva
```java
// Ottieni la prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: crea una casella di testo
```java
// Crea una forma da utilizzare come casella di testo
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Passaggio 4: aggiungi testo in apice
```java
// Crea un paragrafo per il testo principale
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Crea una porzione per il testo in apice
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Imposta lo scappamento per l'apice
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Aggiungi il paragrafo principale con l'apice alla casella di testo
textFrame.getParagraphs().add(mainParagraph);
```
## Passaggio 5: aggiungi testo in pedice
```java
// Crea un altro paragrafo per il testo in pedice
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crea una porzione per il testo in pedice
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Imposta lo scappamento per il pedice
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Aggiungi il paragrafo in pedice alla casella di testo
textFrame.getParagraphs().add(subscriptParagraph);
```
## Passaggio 6: salva la presentazione
```java
// Salva la presentazione
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo esplorato come migliorare le tue presentazioni Java PowerPoint con testo in apice e pedice utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi creare diapositive più accattivanti e informative che comunicano in modo efficace i tuoi contenuti.

## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una solida libreria che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint a livello di codice.
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
 È possibile trovare documentazione dettagliata[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere una licenza temporanea per Aspose.Slides per Java?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Posso provare Aspose.Slides per Java gratuitamente?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Slides per Java?
 Per supporto e discussioni, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
