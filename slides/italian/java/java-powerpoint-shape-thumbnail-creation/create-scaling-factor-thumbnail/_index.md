---
title: Crea miniatura del fattore di scala
linktitle: Crea miniatura del fattore di scala
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare miniature dei fattori di ridimensionamento in Java utilizzando Aspose.Slides per Java. Guida facile da seguire con istruzioni passo passo.
weight: 12
url: /it/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
In questo tutorial, ti guideremo attraverso il processo di creazione di una miniatura del fattore di scala utilizzando Aspose.Slides per Java. Segui queste istruzioni passo passo per ottenere il risultato desiderato.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo sistema.
- Aspose.Slides per la libreria Java scaricata e configurata nel tuo progetto Java.
- Conoscenza di base del linguaggio di programmazione Java.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari richiesti per lavorare con Aspose.Slides nel tuo codice Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Ora suddividiamo l'esempio fornito in più passaggi:
## Passaggio 1: impostare la directory dei documenti
Definisci il percorso della directory dei documenti in cui si trova il file di presentazione di PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso della directory effettiva dei documenti.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
Crea un'istanza della classe Presentation per rappresentare il file di presentazione di PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Assicurarsi di sostituire`"HelloWorld.pptx"` con il nome del file di presentazione di PowerPoint.
## Passaggio 3: crea un'immagine in scala reale
Genera un'immagine in scala reale della diapositiva desiderata dalla presentazione.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Questo codice recupera la miniatura della prima forma nella prima diapositiva della presentazione.
## Passaggio 4: salva l'immagine
Salva l'immagine generata su disco in formato PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Assicurarsi di sostituire`"Scaling Factor Thumbnail_out.png"` con il nome del file di output desiderato.

## Conclusione
In conclusione, hai creato con successo una miniatura del fattore di scala utilizzando Aspose.Slides per Java. Seguendo i passaggi forniti, puoi facilmente integrare questa funzionalità nelle tue applicazioni Java.
## Domande frequenti
### Posso utilizzare Aspose.Slides per Java con qualsiasi IDE Java?
Sì, Aspose.Slides per Java può essere utilizzato con qualsiasi Java Integrated Development Environment (IDE) come Eclipse, IntelliJ IDEA o NetBeans.
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi usufruire di una prova gratuita di Aspose.Slides per Java visitando il sito[sito web](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Slides per Java?
 Puoi trovare supporto per Aspose.Slides per Java su[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Come posso acquistare Aspose.Slides per Java?
 È possibile acquistare Aspose.Slides per Java da[pagina di acquisto](https://purchase.aspose.com/buy).
### Ho bisogno di una licenza temporanea per utilizzare Aspose.Slides per Java?
 Sì, puoi ottenere una licenza temporanea da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
