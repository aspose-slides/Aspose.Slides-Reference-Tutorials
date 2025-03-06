---
title: Crea miniatura della nota figlio SmartArt
linktitle: Crea miniatura della nota figlio SmartArt
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare miniature di note secondarie SmartArt in Java con Aspose.Slides, migliorando le tue presentazioni PowerPoint senza sforzo.
type: docs
weight: 15
url: /it/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## introduzione
In questo tutorial esploreremo come creare miniature di note secondarie SmartArt in Java utilizzando Aspose.Slides. Aspose.Slides è una potente API Java che consente agli sviluppatori di lavorare con presentazioni PowerPoint a livello di codice, consentendo loro di creare, modificare e manipolare le diapositive con facilità.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Slides per la libreria Java scaricata e configurata nel tuo progetto. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

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
## Passaggio 2: crea una presentazione
 Istanziare il`Presentation` classe per rappresentare il file PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungi SmartArt
Aggiungi SmartArt alla diapositiva della presentazione:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Passaggio 4: ottenere un riferimento al nodo
Ottieni il riferimento di un nodo utilizzando il suo indice:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Passaggio 5: ottieni la miniatura
Recupera l'immagine in miniatura del nodo SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Passaggio 6: salva la miniatura
Salva l'immagine in miniatura in un file:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Ripeti questi passaggi per ciascun nodo SmartArt secondo necessità nella presentazione.

## Conclusione
In questo tutorial, abbiamo imparato come creare miniature di note secondarie SmartArt in Java utilizzando Aspose.Slides. Con questa conoscenza, puoi migliorare le tue presentazioni PowerPoint a livello di codice, aggiungendo facilmente elementi visivamente accattivanti.
## Domande frequenti
### Posso utilizzare Aspose.Slides per manipolare file PowerPoint esistenti?
Sì, Aspose.Slides ti consente di modificare i file PowerPoint esistenti, inclusa l'aggiunta, la rimozione o la modifica delle diapositive e dei loro contenuti.
### Aspose.Slides supporta l'esportazione di diapositive in diversi formati di file?
Assolutamente! Aspose.Slides supporta l'esportazione di diapositive in vari formati, tra cui PDF, immagini e HTML, tra gli altri.
### Aspose.Slides è adatto per l'automazione di PowerPoint a livello aziendale?
Sì, Aspose.Slides è progettato per gestire le attività di automazione di PowerPoint a livello aziendale in modo efficiente e affidabile.
### Posso creare diagrammi SmartArt complessi a livello di codice con Aspose.Slides?
Certamente! Aspose.Slides fornisce un supporto completo per la creazione e la manipolazione di diagrammi SmartArt di varia complessità.
### Aspose.Slides offre supporto tecnico per gli sviluppatori?
 Sì, Aspose.Slides fornisce supporto tecnico dedicato agli sviluppatori attraverso il loro[Forum](https://forum.aspose.com/c/slides/11) e altri canali.