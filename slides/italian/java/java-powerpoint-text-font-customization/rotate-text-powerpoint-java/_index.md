---
"description": "Scopri come ruotare il testo in PowerPoint usando Java con Aspose.Slides. Tutorial passo passo per utenti principianti ed esperti."
"linktitle": "Ruotare il testo in PowerPoint utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Ruotare il testo in PowerPoint utilizzando Java"
"url": "/it/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ruotare il testo in PowerPoint utilizzando Java

## Introduzione
In questo tutorial, esploreremo come ruotare il testo nelle presentazioni di PowerPoint a livello di codice utilizzando Java e Aspose.Slides. La rotazione del testo può essere una funzionalità utile nella progettazione di diapositive per creare presentazioni visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza di base del linguaggio di programmazione Java.
- JDK installato sul tuo sistema.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) come IntelliJ IDEA o Eclipse installato sul computer.
## Importa pacchetti
Per prima cosa, è necessario importare le classi Aspose.Slides necessarie per lavorare con i file PowerPoint in Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: imposta il tuo progetto
Per prima cosa, crea un nuovo progetto Java nel tuo IDE e aggiungi il file JAR Aspose.Slides al percorso di build del tuo progetto.
## Passaggio 2: inizializzare gli oggetti di presentazione e diapositiva
```java
// Il percorso della directory in cui si desidera salvare la presentazione
String dataDir = "Your_Document_Directory/";
// Crea un'istanza della classe Presentazione
Presentation presentation = new Presentation();
// Ottieni la prima diapositiva 
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: aggiungere una forma rettangolare
```java
// Aggiungi una forma automatica di tipo rettangolo
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Passaggio 4: aggiungere testo alla forma rettangolare
```java
// Aggiungi TextFrame al rettangolo
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// Accesso alla cornice di testo
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## Passaggio 5: imposta il contenuto del testo e lo stile
```java
// Crea l'oggetto Paragrafo per la cornice di testo
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Crea un oggetto Porzione per il paragrafo
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Passaggio 6: Salva la presentazione
```java
// Salva presentazione
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial abbiamo imparato come ruotare il testo nelle presentazioni di PowerPoint utilizzando Java e Aspose.Slides. Seguendo questi passaggi, puoi manipolare dinamicamente l'orientamento del testo nelle diapositive per migliorarne l'impatto visivo.
## Domande frequenti
### Posso ruotare il testo in qualsiasi angolazione in PowerPoint utilizzando Aspose.Slides per Java?
Sì, è possibile specificare a livello di programmazione qualsiasi angolo desiderato per la rotazione del testo.
### Aspose.Slides supporta altre opzioni di formattazione del testo, come la dimensione del carattere e l'allineamento?
Certamente, Aspose.Slides fornisce API complete per gestire vari requisiti di formattazione del testo.
### Come posso iniziare a usare Aspose.Slides per Java?
Puoi scaricare una versione di prova gratuita di Aspose.Slides da [Qui](https://releases.aspose.com/) per esplorarne le caratteristiche.
### Dove posso trovare ulteriore documentazione e supporto per Aspose.Slides?
Per la documentazione dettagliata, visitare [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/)Puoi anche ottenere supporto dalla comunità su [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Come posso ottenere una licenza temporanea per Aspose.Slides?
È possibile ottenere una licenza temporanea da [Qui](https://purchase.aspose.com/temporary-license/) per valutare Aspose.Slides senza limitazioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}