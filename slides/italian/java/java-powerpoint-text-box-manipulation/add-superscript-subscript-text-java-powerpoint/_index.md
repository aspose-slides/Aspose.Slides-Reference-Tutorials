---
"description": "Scopri come aggiungere testo in apice e pedice nelle presentazioni PowerPoint in Java utilizzando Aspose.Slides per Java. Perfetto per migliorare le tue diapositive."
"linktitle": "Aggiungere testo in apice e pedice in Java PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere testo in apice e pedice in Java PowerPoint"
"url": "/it/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere testo in apice e pedice in Java PowerPoint

## Introduzione
Creare presentazioni PowerPoint coinvolgenti e informative richiede spesso l'utilizzo di funzioni di formattazione come apici e pedici. Questo tutorial vi guiderà attraverso il processo di inserimento di testo in apici e pedici nelle vostre presentazioni PowerPoint in Java utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul sistema.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse configurato per lo sviluppo Java.
- Conoscenza di base della programmazione Java e delle presentazioni PowerPoint.

## Importa pacchetti
Per prima cosa, importa i pacchetti necessari da Aspose.Slides per Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: impostare la presentazione
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Passaggio 2: accedi alla diapositiva
```java
// Ottieni la prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: creare una casella di testo
```java
// Crea una forma automatica da utilizzare come casella di testo
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Passaggio 4: aggiungere testo in apice
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
// Aggiungi il paragrafo principale con apice alla casella di testo
textFrame.getParagraphs().add(mainParagraph);
```
## Passaggio 5: aggiungere il testo in pedice
```java
// Crea un altro paragrafo per il testo in pedice
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Crea una porzione per il testo in pedice
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Imposta lo scappamento per l'indice
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Aggiungere il paragrafo in pedice alla casella di testo
textFrame.getParagraphs().add(subscriptParagraph);
```
## Passaggio 6: Salva la presentazione
```java
// Salva la presentazione
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo esplorato come migliorare le vostre presentazioni PowerPoint in Java con testo in apice e pedice utilizzando Aspose.Slides per Java. Seguendo questi passaggi, potrete creare diapositive visivamente più accattivanti e informative, che comunichino efficacemente i vostri contenuti.

## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una libreria solida che consente agli sviluppatori di creare, manipolare e convertire le presentazioni di PowerPoint a livello di programmazione.
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
La documentazione dettagliata può essere trovata [Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere una licenza temporanea per Aspose.Slides per Java?
Puoi ottenere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).
### Posso provare Aspose.Slides per Java gratuitamente?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Slides per Java?
Per supporto e discussioni, visita il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}