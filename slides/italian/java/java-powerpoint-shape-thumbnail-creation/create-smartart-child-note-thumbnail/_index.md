---
"description": "Scopri come creare miniature di note figlio SmartArt in Java con Aspose.Slides, migliorando senza sforzo le tue presentazioni PowerPoint."
"linktitle": "Crea miniatura della nota secondaria SmartArt"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Crea miniatura della nota secondaria SmartArt"
"url": "/it/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea miniatura della nota secondaria SmartArt

## Introduzione
In questo tutorial, esploreremo come creare miniature di note figlio SmartArt in Java utilizzando Aspose.Slides. Aspose.Slides è una potente API Java che consente agli sviluppatori di lavorare con le presentazioni di PowerPoint a livello di codice, consentendo loro di creare, modificare e manipolare le diapositive con facilità.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul sistema.
2. Scaricata e configurata nel tuo progetto la libreria Aspose.Slides per Java. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Assicurati di importare i pacchetti necessari nella tua classe Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: imposta il tuo progetto
Assicurati di avere un progetto Java impostato e configurato con la libreria Aspose.Slides.
## Passaggio 2: creare una presentazione
Istanziare il `Presentation` classe per rappresentare il file PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungere SmartArt
Aggiungi SmartArt alla diapositiva della presentazione:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Passaggio 4: ottenere un riferimento al nodo
Ottieni il riferimento di un nodo utilizzando il suo indice:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Passaggio 5: Ottieni miniatura
Recupera l'immagine in miniatura del nodo SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Passaggio 6: salva miniatura
Salva l'immagine in miniatura in un file:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Ripetere questi passaggi per ogni nodo SmartArt in base alle esigenze della presentazione.

## Conclusione
In questo tutorial, abbiamo imparato a creare miniature di note figlio SmartArt in Java utilizzando Aspose.Slides. Con queste conoscenze, puoi migliorare le tue presentazioni PowerPoint programmando, aggiungendo facilmente elementi visivamente accattivanti.
## Domande frequenti
### Posso usare Aspose.Slides per manipolare file PowerPoint esistenti?
Sì, Aspose.Slides consente di modificare i file PowerPoint esistenti, ad esempio aggiungendo, rimuovendo o modificando le diapositive e il loro contenuto.
### Aspose.Slides supporta l'esportazione di diapositive in diversi formati di file?
Assolutamente sì! Aspose.Slides supporta l'esportazione di diapositive in vari formati, tra cui PDF, immagini e HTML, tra gli altri.
### Aspose.Slides è adatto all'automazione di PowerPoint a livello aziendale?
Sì, Aspose.Slides è progettato per gestire in modo efficiente e affidabile le attività di automazione di PowerPoint a livello aziendale.
### Posso creare diagrammi SmartArt complessi a livello di programmazione con Aspose.Slides?
Certamente! Aspose.Slides offre un supporto completo per la creazione e la manipolazione di diagrammi SmartArt di varia complessità.
### Aspose.Slides offre supporto tecnico agli sviluppatori?
Sì, Aspose.Slides fornisce supporto tecnico dedicato per gli sviluppatori tramite il loro [foro](https://forum.aspose.com/c/slides/11) e altri canali.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}