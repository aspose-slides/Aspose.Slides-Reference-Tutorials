---
"description": "Scopri come aggiungere un offset di allungamento per il riempimento delle immagini nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Tutorial passo passo incluso."
"linktitle": "Aggiungere offset di allungamento per il riempimento dell'immagine in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere offset di allungamento per il riempimento dell'immagine in PowerPoint"
"url": "/it/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere offset di allungamento per il riempimento dell'immagine in PowerPoint

## Introduzione
In questo tutorial imparerai come utilizzare Aspose.Slides per Java per aggiungere un offset di allungamento per il riempimento delle immagini nelle presentazioni di PowerPoint. Questa funzionalità ti consente di manipolare le immagini all'interno delle diapositive, offrendoti un maggiore controllo sul loro aspetto.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul sistema.
2. Scaricata e configurata nel progetto Java la libreria Aspose.Slides per Java.
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
Definisci la directory in cui si trova il documento PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: creare un oggetto di presentazione
Creare un'istanza della classe Presentation per rappresentare il file PowerPoint:
```java
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungere l'immagine alla diapositiva
Recupera la prima diapositiva e aggiungi un'immagine:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## Passaggio 4: aggiungere la cornice
Crea una cornice con le dimensioni equivalenti all'immagine:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## Passaggio 5: Salva la presentazione
Salvare il file PowerPoint modificato:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai imparato come aggiungere un offset di allungamento per il riempimento delle immagini in PowerPoint utilizzando Aspose.Slides per Java. Questa funzionalità apre un mondo di possibilità per migliorare le tue presentazioni con immagini personalizzate.
## Domande frequenti
### Posso usare questo metodo per aggiungere immagini a diapositive specifiche di una presentazione?
Sì, puoi specificare l'indice della diapositiva quando recuperi l'oggetto diapositiva per indirizzarlo a una diapositiva specifica.
### Aspose.Slides per Java supporta altri formati di immagine oltre a JPEG?
Sì, Aspose.Slides per Java supporta vari formati di immagine, tra cui PNG, GIF e BMP, tra gli altri.
### C'è un limite alla dimensione delle immagini che posso aggiungere utilizzando questo metodo?
Aspose.Slides per Java può gestire immagini di varie dimensioni, ma è consigliabile ottimizzarle per ottenere prestazioni migliori nelle presentazioni.
### Posso applicare ulteriori effetti o trasformazioni alle immagini dopo averle aggiunte alle diapositive?
Sì, puoi applicare un'ampia gamma di effetti e trasformazioni alle immagini utilizzando l'ampia API di Aspose.Slides per Java.
### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides per Java?
Puoi visitare il [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/) per guide dettagliate ed esplora il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}