---
title: Riempi le forme con l'immagine in PowerPoint
linktitle: Riempi le forme con l'immagine in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come riempire forme con immagini nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Migliora l'attrattiva visiva senza sforzo.
type: docs
weight: 12
url: /it/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---
## introduzione
Le presentazioni di PowerPoint spesso richiedono elementi visivi come forme piene di immagini per aumentare il loro fascino e trasmettere le informazioni in modo efficace. Aspose.Slides per Java fornisce un potente set di strumenti per eseguire questa attività senza problemi. In questo tutorial impareremo come riempire forme con immagini utilizzando Aspose.Slides per Java passo dopo passo.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Slides per la libreria Java scaricata. Puoi ottenerlo da[Qui](https://releases.aspose.com/slides/java/).
3. Conoscenza base della programmazione Java.
## Importa pacchetti
Nel tuo progetto Java, importa i pacchetti necessari:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: imposta la directory del progetto
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Assicurarsi di sostituire`"Your Document Directory"` con il percorso della directory del progetto.
## Passaggio 2: crea una presentazione
```java
Presentation pres = new Presentation();
```
 Istanziare il`Presentation` classe per creare una nuova presentazione di PowerPoint.
## Passaggio 3: aggiungi una diapositiva e una forma
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Aggiungi una diapositiva alla presentazione e crea una forma rettangolare su di essa.
## Passaggio 4: imposta il tipo di riempimento su Immagine
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Imposta il tipo di riempimento della forma su immagine.
## Passaggio 5: impostare la modalità di riempimento immagine
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Imposta la modalità di riempimento dell'immagine della forma.
## Passaggio 6: imposta l'immagine
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Carica l'immagine e impostala come riempimento per la forma.
## Passaggio 7: salva la presentazione
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Salva la presentazione modificata in un file.

## Conclusione
Con Aspose.Slides per Java, riempire forme con immagini nelle presentazioni PowerPoint diventa un processo semplice. Seguendo i passaggi delineati in questo tutorial, puoi facilmente migliorare le tue presentazioni con elementi visivamente accattivanti.

## Domande frequenti
### Posso riempire forme diverse con immagini utilizzando Aspose.Slides per Java?
Sì, Aspose.Slides per Java supporta il riempimento di varie forme con immagini, offrendo flessibilità nel design.
### Aspose.Slides per Java è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides per Java genera presentazioni compatibili con PowerPoint 97 e versioni successive, garantendo un'ampia compatibilità.
### Come posso ridimensionare l'immagine all'interno della forma?
Puoi ridimensionare l'immagine all'interno della forma regolando le dimensioni della forma o ridimensionando l'immagine di conseguenza prima di impostarla come riempimento.
### Esistono limitazioni sui formati immagine supportati per il riempimento delle forme?
Aspose.Slides per Java supporta un'ampia gamma di formati di immagine, tra cui JPEG, PNG, GIF, BMP e TIFF, tra gli altri.
### Posso applicare effetti alle forme piene?
Sì, Aspose.Slides per Java fornisce API complete per applicare vari effetti, come ombre, riflessi e rotazioni 3D, alle forme piene.