---
title: Imposta l'adattamento automatico della cornice di testo in Java PowerPoint
linktitle: Imposta l'adattamento automatico della cornice di testo in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare l'adattamento automatico per le cornici di testo in Java PowerPoint utilizzando Aspose.Slides per Java. Crea presentazioni dinamiche senza sforzo.
weight: 14
url: /it/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta l'adattamento automatico della cornice di testo in Java PowerPoint

## introduzione
Nello sviluppo di applicazioni Java, la creazione di presentazioni PowerPoint dinamiche e visivamente accattivanti a livello di programmazione è un requisito comune. Aspose.Slides per Java fornisce un potente set di API per raggiungere questo obiettivo senza sforzo. Una caratteristica essenziale è l'impostazione dell'adattamento automatico per le cornici di testo, garantendo che il testo si adatti perfettamente all'interno delle forme senza regolazioni manuali. Questo tutorial ti guiderà attraverso il processo passo dopo passo, sfruttando Aspose.Slides per Java per automatizzare l'adattamento del testo nelle diapositive di PowerPoint.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo sistema
- Aspose.Slides per la libreria Java scaricata e referenziata nel tuo progetto Java
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse
### Importa pacchetti
Innanzitutto, assicurati di importare le classi Aspose.Slides necessarie nel tuo progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: crea una nuova presentazione
Inizia creando una nuova istanza di presentazione di PowerPoint in cui aggiungerai diapositive e forme.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation presentation = new Presentation();
```
## Passaggio 2: accedi alla diapositiva per aggiungere forme
Accedi alla prima diapositiva della presentazione in cui desideri aggiungere una forma con testo adattato automaticamente.
```java
// Accedi alla prima diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: aggiungi una forma automatica (rettangolo)
Aggiungi una forma automatica (rettangolo) alla diapositiva con coordinate e dimensioni specifiche.
```java
// Aggiungi una forma automatica di tipo rettangolo
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Passaggio 4: aggiungi TextFrame al rettangolo
Aggiungi una cornice di testo alla forma rettangolare.
```java
// Aggiungi TextFrame al rettangolo
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## Passaggio 5: imposta l'adattamento automatico per la cornice di testo
Imposta le proprietà di adattamento automatico per la cornice di testo per regolare il testo in base alle dimensioni della forma.
```java
// Accesso alla cornice di testo
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## Passaggio 6: aggiungi testo alla cornice di testo
Aggiungi contenuto di testo alla cornice di testo all'interno della forma.
```java
// Crea l'oggetto Paragrafo per la cornice di testo
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Crea un oggetto Porzione per il paragrafo
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Passaggio 7: salva la presentazione
Salva la presentazione modificata con la cornice di testo adattata automaticamente.
```java
// Salva presentazione
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, hai imparato come impostare l'adattamento automatico per le cornici di testo nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi automatizzare l'adattamento del testo all'interno delle forme, migliorando la leggibilità e l'estetica delle tue presentazioni a livello di codice.

## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una solida API Java che consente agli sviluppatori di creare, leggere, manipolare e convertire presentazioni PowerPoint.
### Come posso scaricare Aspose.Slides per Java?
 È possibile scaricare Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
### Posso provare Aspose.Slides per Java gratuitamente?
 Sì, puoi ottenere una prova gratuita di Aspose.Slides per Java da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 È possibile trovare la documentazione dettagliata per Aspose.Slides per Java[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto per Aspose.Slides per Java?
 È possibile ottenere supporto comunitario e professionale per Aspose.Slides per Java da[Qui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
