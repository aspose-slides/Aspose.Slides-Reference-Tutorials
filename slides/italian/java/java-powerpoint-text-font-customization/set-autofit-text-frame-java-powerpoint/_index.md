---
"description": "Scopri come impostare l'adattamento automatico per le cornici di testo in Java PowerPoint utilizzando Aspose.Slides per Java. Crea presentazioni dinamiche senza sforzo."
"linktitle": "Imposta l'adattamento automatico della cornice di testo in Java PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta l'adattamento automatico della cornice di testo in Java PowerPoint"
"url": "/it/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta l'adattamento automatico della cornice di testo in Java PowerPoint

## Introduzione
Nello sviluppo di applicazioni Java, creare presentazioni PowerPoint dinamiche e visivamente accattivanti a livello di codice è un requisito comune. Aspose.Slides per Java offre un potente set di API per raggiungere questo obiettivo senza sforzo. Una funzionalità essenziale è l'impostazione dell'adattamento automatico per le cornici di testo, garantendo che il testo si adatti perfettamente alle forme senza bisogno di regolazioni manuali. Questo tutorial vi guiderà passo dopo passo attraverso il processo, sfruttando Aspose.Slides per Java per automatizzare l'adattamento del testo nelle diapositive di PowerPoint.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo sistema
- Libreria Aspose.Slides per Java scaricata e referenziata nel tuo progetto Java
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse
### Importa pacchetti
Per prima cosa, assicurati di importare le classi Aspose.Slides necessarie nel tuo progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: creare una nuova presentazione
Per prima cosa, crea una nuova istanza di presentazione PowerPoint in cui aggiungerai diapositive e forme.
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
```
## Passaggio 2: accedi alla diapositiva per aggiungere forme
Accedi alla prima diapositiva della presentazione in cui desideri aggiungere una forma con testo adattato automaticamente.
```java
// Accedi alla prima diapositiva 
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: aggiungere una forma automatica (rettangolo)
Aggiungere una forma automatica (rettangolo) alla diapositiva con coordinate e dimensioni specifiche.
```java
// Aggiungi una forma automatica di tipo rettangolo
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Passaggio 4: aggiungere TextFrame al rettangolo
Aggiungere una cornice di testo alla forma rettangolare.
```java
// Aggiungi TextFrame al rettangolo
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## Passaggio 5: imposta l'adattamento automatico per la cornice di testo
Imposta le proprietà di adattamento automatico per la cornice di testo per adattare il testo in base alle dimensioni della forma.
```java
// Accesso alla cornice di testo
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## Passaggio 6: aggiungere testo alla cornice di testo
Aggiungere contenuto di testo alla cornice di testo all'interno della forma.
```java
// Crea l'oggetto Paragrafo per la cornice di testo
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Crea un oggetto Porzione per il paragrafo
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Passaggio 7: Salva la presentazione
Salvare la presentazione modificata con la cornice di testo adattata automaticamente.
```java
// Salva presentazione
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, hai imparato come impostare l'adattamento automatico per le cornici di testo nelle presentazioni PowerPoint in Java utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi automatizzare l'adattamento del testo all'interno delle forme, migliorando la leggibilità e l'estetica delle tue presentazioni a livello di codice.

## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una solida API Java che consente agli sviluppatori di creare, leggere, manipolare e convertire presentazioni PowerPoint.
### Come posso scaricare Aspose.Slides per Java?
Puoi scaricare Aspose.Slides per Java da [Qui](https://releases.aspose.com/slides/java/).
### Posso provare Aspose.Slides per Java gratuitamente?
Sì, puoi ottenere una prova gratuita di Aspose.Slides per Java da [Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
Puoi trovare la documentazione dettagliata per Aspose.Slides per Java [Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto per Aspose.Slides per Java?
Puoi ottenere supporto professionale e comunitario per Aspose.Slides per Java da [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}