---
title: Aggiungi offset di stiramento per riempimento immagine in PowerPoint
linktitle: Aggiungi offset di stiramento per riempimento immagine in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere un offset stirato per il riempimento delle immagini nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Tutorial passo passo incluso.
type: docs
weight: 16
url: /it/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---
## introduzione
In questo tutorial imparerai come utilizzare Aspose.Slides per Java per aggiungere un offset di allungamento per il riempimento delle immagini nelle presentazioni di PowerPoint. Questa funzione ti consente di manipolare le immagini all'interno delle tue diapositive, offrendoti un maggiore controllo sul loro aspetto.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2. Aspose.Slides per la libreria Java scaricata e configurata nel tuo progetto Java.
## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: imposta la directory dei documenti
Definisci la directory in cui si trova il tuo documento PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: crea un oggetto di presentazione
Creare un'istanza della classe Presentation per rappresentare il file PowerPoint:
```java
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungi l'immagine alla diapositiva
Recupera la prima diapositiva e aggiungi un'immagine:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## Passaggio 4: aggiungi la cornice
Crea una cornice con le dimensioni equivalenti all'immagine:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## Passaggio 5: salva la presentazione
Salva il file PowerPoint modificato:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere un offset di stiramento per il riempimento dell'immagine in PowerPoint utilizzando Aspose.Slides per Java. Questa funzionalità apre un mondo di possibilità per migliorare le tue presentazioni con immagini personalizzate.
## Domande frequenti
### Posso utilizzare questo metodo per aggiungere immagini a diapositive specifiche in una presentazione?
Sì, puoi specificare l'indice della diapositiva quando recuperi l'oggetto diapositiva per indirizzare una diapositiva specifica.
### Aspose.Slides per Java supporta altri formati di immagine oltre a JPEG?
Sì, Aspose.Slides per Java supporta vari formati di immagine, tra cui PNG, GIF e BMP, tra gli altri.
### Esiste un limite alla dimensione delle immagini che posso aggiungere utilizzando questo metodo?
Aspose.Slides per Java può gestire immagini di varie dimensioni, ma si consiglia di ottimizzare le immagini per ottenere prestazioni migliori nelle presentazioni.
### Posso applicare effetti o trasformazioni aggiuntivi alle immagini dopo averle aggiunte alle diapositive?
Sì, puoi applicare un'ampia gamma di effetti e trasformazioni alle immagini utilizzando Aspose.Slides per l'ampia API di Java.
### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides per Java?
 Puoi visitare il[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/) per guide dettagliate ed esplorare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.