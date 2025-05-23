---
"description": "Scopri come impostare il formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides. Guida passo passo per una gestione efficiente delle presentazioni."
"linktitle": "Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java"
"url": "/it/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il formato di riempimento dei punti elenco in SmartArt utilizzando Java

## Introduzione
Nell'ambito della programmazione Java, la manipolazione efficiente delle presentazioni è un requisito comune, soprattutto quando si lavora con elementi SmartArt. Aspose.Slides per Java si propone come uno strumento potente per questo tipo di attività, offrendo una serie di funzionalità per la gestione delle presentazioni a livello di codice. In questo tutorial, approfondiremo passo dopo passo il processo di impostazione del formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides.
## Prerequisiti
Prima di iniziare questo tutorial, assicurati di avere i seguenti prerequisiti:
### Kit di sviluppo Java (JDK)
È necessario che JDK sia installato sul sistema. È possibile scaricarlo da [sito web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguire le istruzioni di installazione.
### Aspose.Slides per Java
Scarica e installa Aspose.Slides per Java da [collegamento per il download](https://releases.aspose.com/slides/java/)Seguire le istruzioni di installazione fornite nella documentazione relativa al sistema operativo in uso.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Scomponiamo l'esempio fornito in più passaggi per comprendere chiaramente come impostare il formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides.
## Passaggio 1: creare un oggetto di presentazione
```java
Presentation presentation = new Presentation();
```
Per prima cosa, crea una nuova istanza della classe Presentation, che rappresenta una presentazione di PowerPoint.
## Passaggio 2: aggiungere SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Successivamente, aggiungi una forma SmartArt alla diapositiva. Questa riga di codice inizializza una nuova forma SmartArt con dimensioni e layout specificati.
## Passaggio 3: accedi al nodo SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Ora accedi al primo nodo (o a qualsiasi altro nodo desiderato) all'interno della forma SmartArt per modificarne le proprietà.
## Passaggio 4: imposta il formato di riempimento dei punti elenco
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Qui controlliamo se il formato di riempimento dei punti elenco è supportato. In tal caso, carichiamo un file immagine e lo impostiamo come riempimento dei punti elenco per il nodo SmartArt.
## Passaggio 5: Salva la presentazione
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Infine, salva la presentazione modificata nella posizione specificata.

## Conclusione
Congratulazioni! Hai imparato come impostare il formato di riempimento dei punti elenco in SmartArt utilizzando Java con Aspose.Slides. Questa funzionalità apre un mondo di possibilità per presentazioni dinamiche e visivamente accattivanti nelle applicazioni Java.
## Domande frequenti
### Posso usare Aspose.Slides per Java per creare presentazioni da zero?
Assolutamente sì! Aspose.Slides fornisce API complete per creare, modificare e manipolare presentazioni interamente tramite codice.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Sì, Aspose.Slides garantisce la compatibilità con diverse versioni di Microsoft PowerPoint, consentendo un'integrazione perfetta nel tuo flusso di lavoro.
### Posso personalizzare gli elementi SmartArt oltre il formato di riempimento dei punti elenco?
Aspose.Slides ti consente infatti di personalizzare ogni aspetto delle forme SmartArt, tra cui layout, stile, contenuto e altro ancora.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi esplorare le funzionalità di Aspose.Slides con una prova gratuita. Basta scaricarlo da [sito web](https://releases.aspose.com/slides/java/) e inizia ad esplorare.
### Dove posso trovare supporto per Aspose.Slides per Java?
Per qualsiasi domanda o assistenza, puoi visitare il forum Aspose.Slides all'indirizzo [questo collegamento](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}