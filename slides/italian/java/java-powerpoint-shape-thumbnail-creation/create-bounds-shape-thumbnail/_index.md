---
title: Crea miniatura forma limiti
linktitle: Crea miniatura forma limiti
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare miniature di forme con limiti utilizzando Aspose.Slides per Java. Questo tutorial passo passo ti guida attraverso il processo.
type: docs
weight: 10
url: /it/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## introduzione
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori Java di creare, manipolare e convertire presentazioni PowerPoint a livello di codice. In questo tutorial impareremo come creare un'immagine in miniatura di una forma con limiti utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Slides per la libreria Java scaricata e aggiunta al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Assicurati di importare i pacchetti necessari nel tuo codice Java:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto Java nel tuo IDE preferito e aggiungi la libreria Aspose.Slides per Java alle dipendenze del tuo progetto.
## Passaggio 2: creare un'istanza di un oggetto di presentazione
 Istanziare a`Presentation` oggetto fornendo il percorso del file di presentazione di PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Passaggio 3: crea una miniatura della forma dei limiti
Ora creiamo un'immagine in miniatura di una forma con i limiti della presentazione.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusione
In questo tutorial, abbiamo imparato come creare un'immagine in miniatura di una forma con limiti utilizzando Aspose.Slides per Java. Seguendo questi passaggi è possibile generare facilmente anteprime delle forme nelle presentazioni PowerPoint a livello di codice.
## Domande frequenti
### Posso creare miniature per forme specifiche all'interno di una diapositiva?
Sì, puoi accedere a singole forme all'interno di una diapositiva e generare miniature per esse utilizzando Aspose.Slides per Java.
### Aspose.Slides per Java è compatibile con tutte le versioni dei file PowerPoint?
Aspose.Slides per Java supporta vari formati di file PowerPoint, inclusi PPT, PPTX, PPS, PPSX e altri.
### Posso personalizzare l'aspetto delle immagini in miniatura generate?
Sì, puoi regolare le proprietà delle immagini in miniatura, come dimensioni e qualità, in base alle tue esigenze.
### Aspose.Slides per Java supporta altre funzionalità oltre alla generazione di miniature?
Sì, Aspose.Slides per Java fornisce funzionalità estese per lavorare con presentazioni PowerPoint, tra cui la manipolazione delle diapositive, l'estrazione del testo e la generazione di grafici.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).