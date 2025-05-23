---
"description": "Scopri come aggiungere cornici per immagini con altezza relativa in scala nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java, migliorando così i tuoi contenuti visivi."
"linktitle": "Aggiungi l'altezza relativa della cornice per immagini in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungi l'altezza relativa della cornice per immagini in PowerPoint"
"url": "/it/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi l'altezza relativa della cornice per immagini in PowerPoint

## Introduzione
In questo tutorial imparerai come aggiungere una cornice per immagini con altezza scala relativa nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul sistema.
2. Libreria Aspose.Slides per Java scaricata e aggiunta al progetto Java.

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
Per prima cosa, assicurati di aver impostato una directory per il tuo progetto e che l'ambiente Java sia configurato correttamente.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
Crea un nuovo oggetto di presentazione utilizzando Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: carica l'immagine da aggiungere
Carica l'immagine che vuoi aggiungere alla presentazione:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Passaggio 4: aggiungere la cornice alla diapositiva
Aggiungere una cornice per immagini a una diapositiva della presentazione:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Passaggio 5: imposta la larghezza e l'altezza della scala relativa
Imposta la larghezza e l'altezza della scala relativa per la cornice dell'immagine:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Passaggio 6: Salva la presentazione
Salva la presentazione con la cornice per l'immagine aggiunta:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Seguendo questi passaggi, puoi facilmente aggiungere una cornice con altezza scala relativa nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Sperimenta con diversi valori di scala per ottenere l'aspetto desiderato per le tue immagini.

## Domande frequenti
### Posso aggiungere più cornici a una singola diapositiva utilizzando questo metodo?
Sì, puoi aggiungere più cornici a una diapositiva ripetendo il procedimento per ogni immagine.
### Aspose.Slides per Java è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides per Java è compatibile con diverse versioni di PowerPoint, garantendo flessibilità nella creazione di presentazioni.
### Posso personalizzare la posizione e le dimensioni della cornice?
Assolutamente, puoi regolare i parametri di posizione e dimensione nel `addPictureFrame` metodo adatto alle tue esigenze.
### Aspose.Slides per Java supporta altri formati di immagine oltre a JPEG?
Sì, Aspose.Slides per Java supporta vari formati di immagine, tra cui PNG, GIF, BMP e altri.
### Esiste un forum della community o un canale di supporto disponibile per gli utenti di Aspose.Slides?
Sì, puoi visitare il forum di Aspose.Slides per qualsiasi domanda, discussione o assistenza riguardante la libreria.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}