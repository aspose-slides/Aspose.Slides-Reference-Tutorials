---
title: Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java
linktitle: Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare il formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides. Guida passo passo per una manipolazione efficiente della presentazione.
weight: 18
url: /it/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java

## introduzione
Nel campo della programmazione Java, la manipolazione efficiente delle presentazioni è un requisito comune, soprattutto quando si ha a che fare con elementi SmartArt. Aspose.Slides per Java emerge come un potente strumento per tali attività, offrendo una serie di funzionalità per gestire le presentazioni a livello di codice. In questo tutorial, approfondiremo il processo di impostazione del formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides, passo dopo passo.
## Prerequisiti
Prima di intraprendere questo tutorial, assicurati di disporre dei seguenti prerequisiti:
### Kit di sviluppo Java (JDK)
 È necessario che JDK sia installato sul tuo sistema. Puoi scaricarlo da[sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguire le istruzioni di installazione.
### Aspose.Slides per Java
 Scarica e installa Aspose.Slides per Java dal file[Link per scaricare](https://releases.aspose.com/slides/java/). Seguire le istruzioni di installazione fornite nella documentazione del proprio sistema operativo specifico.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Analizziamo l'esempio fornito in più passaggi per una chiara comprensione di come impostare il formato di riempimento del punto elenco in SmartArt utilizzando Java con Aspose.Slides.
## Passaggio 1: crea un oggetto di presentazione
```java
Presentation presentation = new Presentation();
```
Innanzitutto, crea una nuova istanza della classe Presentation, che rappresenta una presentazione di PowerPoint.
## Passaggio 2: aggiungi SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Successivamente, aggiungi una forma SmartArt alla diapositiva. Questa riga di codice inizializza una nuova forma SmartArt con dimensioni e layout specificati.
## Passaggio 3: accedi al nodo SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Ora accedi al primo nodo (o qualsiasi nodo desiderato) all'interno della forma SmartArt per modificarne le proprietà.
## Passaggio 4: imposta il formato di riempimento dei proiettili
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Qui controlliamo se il formato di riempimento dei punti elenco è supportato. Se lo è, carichiamo un file immagine e lo impostiamo come riempimento del punto elenco per il nodo SmartArt.
## Passaggio 5: salva la presentazione
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Infine, salva la presentazione modificata in una posizione specificata.

## Conclusione
Congratulazioni! Hai imparato con successo come impostare il formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides. Questa funzionalità apre un mondo di possibilità per presentazioni dinamiche e visivamente accattivanti nelle applicazioni Java.
## Domande frequenti
### Posso utilizzare Aspose.Slides per Java per creare presentazioni da zero?
Assolutamente! Aspose.Slides fornisce API complete per creare, modificare e manipolare presentazioni interamente tramite codice.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Sì, Aspose.Slides garantisce la compatibilità con varie versioni di Microsoft PowerPoint, consentendo una perfetta integrazione nel tuo flusso di lavoro.
### Posso personalizzare gli elementi SmartArt oltre il formato di riempimento puntato?
In effetti, Aspose.Slides ti consente di personalizzare ogni aspetto delle forme SmartArt, inclusi layout, stile, contenuto e altro ancora.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi esplorare le funzionalità di Aspose.Slides con una prova gratuita. Basta scaricarlo da[sito web](https://releases.aspose.com/slides/java/) e iniziare a esplorare.
### Dove posso trovare supporto per Aspose.Slides per Java?
 Per qualsiasi domanda o assistenza, puoi visitare il forum Aspose.Slides all'indirizzo[questo link](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
