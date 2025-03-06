---
title: Aggiungi la cornice per l'altezza in scala relativa in PowerPoint
linktitle: Aggiungi la cornice per l'altezza in scala relativa in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere cornici di altezza in scala relativa nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java, migliorando il tuo contenuto visivo.
weight: 15
url: /it/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
In questo tutorial imparerai come aggiungere una cornice con altezza relativa in scala nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2. Aspose.Slides per la libreria Java scaricata e aggiunta al tuo progetto Java.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: imposta il tuo progetto
Innanzitutto, assicurati di avere una directory impostata per il tuo progetto e che il tuo ambiente Java sia configurato correttamente.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
Crea un nuovo oggetto di presentazione utilizzando Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: caricare l'immagine da aggiungere
Carica l'immagine che desideri aggiungere alla presentazione:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Passaggio 4: aggiungi la cornice alla diapositiva
Aggiungi una cornice immagine a una diapositiva nella presentazione:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Passaggio 5: impostare la larghezza e l'altezza della scala relativa
Imposta la larghezza e l'altezza della scala relativa per la cornice dell'immagine:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Passaggio 6: salva la presentazione
Salva la presentazione con la cornice aggiunta:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Seguendo questi passaggi, puoi facilmente aggiungere una cornice con altezza in scala relativa nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Sperimenta diversi valori di scala per ottenere l'aspetto desiderato per le tue immagini.

## Domande frequenti
### Posso aggiungere più cornici a una singola diapositiva utilizzando questo metodo?
Sì, puoi aggiungere più cornici a una diapositiva ripetendo la procedura per ciascuna immagine.
### Aspose.Slides per Java è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides per Java è compatibile con varie versioni di PowerPoint, garantendo flessibilità nella creazione di presentazioni.
### Posso personalizzare la posizione e le dimensioni della cornice?
 Assolutamente, puoi regolare i parametri di posizione e dimensione nel file`addPictureFrame` metodo adatto alle vostre esigenze.
### Aspose.Slides per Java supporta altri formati di immagine oltre a JPEG?
Sì, Aspose.Slides per Java supporta vari formati di immagine, inclusi PNG, GIF, BMP e altri.
### Esiste un forum della community o un canale di supporto disponibile per gli utenti di Aspose.Slides?
Sì, puoi visitare il forum Aspose.Slides per qualsiasi domanda, discussione o assistenza riguardante la libreria.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
