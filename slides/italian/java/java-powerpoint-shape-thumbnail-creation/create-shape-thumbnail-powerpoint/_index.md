---
"description": "Scopri come generare miniature di forme nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Guida dettagliata fornita."
"linktitle": "Crea miniatura di forma in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Crea miniatura di forma in PowerPoint"
"url": "/it/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea miniatura di forma in PowerPoint

## Introduzione
In questo tutorial, approfondiremo la creazione di miniature di forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori di lavorare con i file di PowerPoint a livello di codice, consentendo l'automazione di diverse attività, inclusa la generazione di miniature di forme.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base della programmazione Java.
- Java Development Kit (JDK) installato sul sistema.
- Scarica e configura la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Innanzitutto, è necessario importare i pacchetti necessari nel codice Java per utilizzare le funzionalità di Aspose.Slides. Includere le seguenti istruzioni di importazione all'inizio del file Java:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: definire la directory dei documenti
```java
String dataDir = "Your Document Directory";
```
Sostituire `"Your Document Directory"` con il percorso della directory contenente il file PowerPoint.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Crea una nuova istanza di `Presentation` classe, passando il percorso al file PowerPoint come parametro.
## Passaggio 3: Genera miniatura della forma
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Recupera la miniatura della forma desiderata dalla prima diapositiva della presentazione.
## Passaggio 4: salva l'immagine in miniatura
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Salvare l'immagine in miniatura generata sul disco in formato PNG con il nome file specificato.

## Conclusione
In conclusione, questo tutorial ha mostrato come creare miniature di forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Seguendo la guida passo passo e utilizzando i frammenti di codice forniti, è possibile generare in modo efficiente miniature di forme a livello di codice.

## Domande frequenti
### Posso creare miniature per le forme in qualsiasi diapositiva della presentazione?
Sì, puoi modificare il codice per applicare le forme a qualsiasi diapositiva, modificando di conseguenza l'indice della diapositiva.
### Aspose.Slides supporta altri formati di immagine per il salvataggio delle miniature?
Sì, oltre a PNG, Aspose.Slides supporta il salvataggio delle miniature in vari formati immagine, come JPEG, GIF e BMP.
### Aspose.Slides è adatto all'uso commerciale?
Sì, Aspose.Slides offre licenze commerciali per aziende e organizzazioni. Puoi acquistare una licenza da [Qui](https://purchase.aspose.com/buy).
### Posso provare Aspose.Slides prima di acquistarlo?
Assolutamente! Puoi scaricare una versione di prova gratuita di Aspose.Slides da [Qui](https://releases.aspose.com/) per valutarne le caratteristiche e le capacità.
### Dove posso trovare supporto per Aspose.Slides?
Se hai domande o hai bisogno di assistenza con Aspose.Slides, puoi visitare [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11) per supporto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}