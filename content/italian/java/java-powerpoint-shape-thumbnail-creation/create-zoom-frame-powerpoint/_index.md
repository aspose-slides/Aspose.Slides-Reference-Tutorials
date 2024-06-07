---
title: Crea cornice di zoom in PowerPoint
linktitle: Crea cornice di zoom in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare fotogrammi Zoom accattivanti in PowerPoint utilizzando Aspose.Slides per Java. Segui la nostra guida per aggiungere elementi interattivi alle tue presentazioni.
type: docs
weight: 17
url: /it/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---
## introduzione
Creare presentazioni PowerPoint accattivanti è un'arte e, a volte, le più piccole aggiunte possono fare un'enorme differenza. Una di queste funzionalità è Zoom Frame, che consente di ingrandire diapositive o immagini specifiche, creando una presentazione dinamica e interattiva. In questo tutorial ti guideremo attraverso il processo di creazione di un frame di zoom in PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse.
- Conoscenza base della programmazione Java.
## Importa pacchetti
Per cominciare, devi importare i pacchetti necessari nel tuo progetto Java. Queste importazioni forniranno l'accesso alle funzionalità Aspose.Slides richieste per questo tutorial.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Passaggio 1: impostazione della presentazione
Per prima cosa dobbiamo creare una nuova presentazione e aggiungervi un paio di diapositive.
```java
// Nome del file di output
String resultPath = "ZoomFramePresentation.pptx";
// Percorso dell'immagine di origine
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // Aggiungi nuove diapositive alla presentazione
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## Passaggio 2: personalizzazione degli sfondi delle diapositive
Vogliamo rendere le nostre diapositive visivamente distinte aggiungendo colori di sfondo.
### Impostazione dello sfondo per la seconda diapositiva
```java
    //Crea uno sfondo per la seconda diapositiva
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // Crea una casella di testo per la seconda diapositiva
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### Impostazione dello sfondo per la terza diapositiva
```java
    // Crea uno sfondo per la terza diapositiva
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // Crea una casella di testo per la terza diapositiva
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## Passaggio 3: aggiunta di fotogrammi di zoom
Ora aggiungiamo fotogrammi Zoom alla presentazione. Aggiungeremo un fotogramma zoom con un'anteprima della diapositiva e un altro con un'immagine personalizzata.
### Aggiunta di un riquadro di zoom con anteprima diapositiva
```java
    // Aggiungi oggetti ZoomFrame con anteprima della diapositiva
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### Aggiunta di una cornice di zoom con un'immagine personalizzata
```java
    // Aggiungi oggetti ZoomFrame con immagine personalizzata
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## Passaggio 4: personalizzazione dei fotogrammi di zoom
Per far risaltare le nostre cornici Zoom, personalizzeremo il loro aspetto.
### Personalizzazione del secondo fotogramma di zoom
```java
    // Imposta un formato del riquadro di zoom per l'oggetto zoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### Nascondere lo sfondo per il primo fotogramma di zoom
```java
    // Non mostrare lo sfondo per l'oggetto zoomFrame1
    zoomFrame1.setShowBackground(false);
```
## Passaggio 5: salvataggio della presentazione
Infine, salviamo la nostra presentazione nel percorso specificato.
```java
    // Salva la presentazione
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusione
La creazione di fotogrammi di zoom in PowerPoint utilizzando Aspose.Slides per Java può migliorare significativamente l'interattività e il coinvolgimento delle tue presentazioni. Seguendo i passaggi delineati in questo tutorial, puoi aggiungere facilmente sia anteprime di diapositive che immagini personalizzate come fotogrammi di zoom, personalizzandole per adattarle al tema della tua presentazione. Buona presentazione!
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare e manipolare presentazioni PowerPoint a livello di codice.
### Come installo Aspose.Slides per Java?
 È possibile scaricare Aspose.Slides per Java dal file[sito web](https://releases.aspose.com/slides/java/) e aggiungilo alle dipendenze del tuo progetto.
### Posso personalizzare l'aspetto dei fotogrammi di zoom?
Sì, Aspose.Slides ti consente di personalizzare varie proprietà dei fotogrammi di zoom, come lo stile della linea, il colore e la visibilità dello sfondo.
### È possibile aggiungere immagini ai fotogrammi Zoom?
Assolutamente! Puoi aggiungere immagini personalizzate ai fotogrammi Zoom leggendo i file immagine e aggiungendoli alla presentazione.
### Dove posso trovare altri esempi e documentazione?
 È possibile trovare documentazione completa ed esempi su[Aspose.Slides per la pagina della documentazione Java](https://reference.aspose.com/slides/java/).