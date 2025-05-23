---
"description": "Scopri come creare miniature con fattore di scala in Java utilizzando Aspose.Slides per Java. Guida facile da seguire con istruzioni dettagliate."
"linktitle": "Crea miniatura del fattore di scala"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Crea miniatura del fattore di scala"
"url": "/it/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea miniatura del fattore di scala

## Introduzione
In questo tutorial, ti guideremo attraverso il processo di creazione di una miniatura con fattore di scala utilizzando Aspose.Slides per Java. Segui queste istruzioni passo passo per ottenere il risultato desiderato.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
- Java Development Kit (JDK) installato sul sistema.
- Scaricata e configurata nel progetto Java la libreria Aspose.Slides per Java.
- Conoscenza di base del linguaggio di programmazione Java.

## Importa pacchetti
Per prima cosa, importa i pacchetti necessari per lavorare con Aspose.Slides nel tuo codice Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Ora scomponiamo l'esempio fornito in più passaggi:
## Passaggio 1: impostare la directory dei documenti
Definisci il percorso della directory dei documenti in cui si trova il file della presentazione di PowerPoint.
```java
String dataDir = "Your Document Directory";
```
Sostituire `"Your Document Directory"` con il percorso verso la directory effettiva del documento.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
Creare un'istanza della classe Presentation per rappresentare il file di presentazione di PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Assicurarsi di sostituire `"HelloWorld.pptx"` con il nome del file della presentazione PowerPoint.
## Passaggio 3: creare un'immagine a grandezza naturale
Genera un'immagine a grandezza naturale della diapositiva desiderata dalla presentazione.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Questo codice recupera la miniatura della prima forma nella prima diapositiva della presentazione.
## Passaggio 4: salva l'immagine
Salvare l'immagine generata sul disco in formato PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Assicurarsi di sostituire `"Scaling Factor Thumbnail_out.png"` con il nome del file di output desiderato.

## Conclusione
In conclusione, hai creato con successo una miniatura con fattore di scala utilizzando Aspose.Slides per Java. Seguendo i passaggi indicati, puoi integrare facilmente questa funzionalità nelle tue applicazioni Java.
## Domande frequenti
### Posso usare Aspose.Slides per Java con qualsiasi IDE Java?
Sì, Aspose.Slides per Java può essere utilizzato con qualsiasi Java Integrated Development Environment (IDE) come Eclipse, IntelliJ IDEA o NetBeans.
### È disponibile una versione di prova gratuita di Aspose.Slides per Java?
Sì, puoi usufruire di una prova gratuita di Aspose.Slides per Java visitando il [sito web](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Slides per Java?
Puoi trovare supporto per Aspose.Slides per Java su [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Come posso acquistare Aspose.Slides per Java?
Puoi acquistare Aspose.Slides per Java da [pagina di acquisto](https://purchase.aspose.com/buy).
### Ho bisogno di una licenza temporanea per utilizzare Aspose.Slides per Java?
Sì, puoi ottenere una licenza temporanea dall' [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}