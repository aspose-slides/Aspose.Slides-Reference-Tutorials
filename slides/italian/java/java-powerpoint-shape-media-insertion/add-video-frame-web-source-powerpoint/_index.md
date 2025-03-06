---
title: Aggiungi frame video dalla sorgente Web in PowerPoint
linktitle: Aggiungi frame video dalla sorgente Web in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come migliorare le tue presentazioni PowerPoint aggiungendo fotogrammi video da fonti Web utilizzando Aspose.Slides per Java.
weight: 18
url: /it/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
In questo tutorial impareremo come aggiungere un fotogramma video da una fonte Web, come YouTube, a una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Seguendo queste istruzioni passo passo, sarai in grado di migliorare le tue presentazioni incorporando elementi multimediali accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
- JDK (Java Development Kit) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java scaricata e aggiunta al tuo progetto Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Una connessione Internet attiva per accedere alla fonte web (ad esempio YouTube).

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Passaggio 1: crea un oggetto di presentazione di PowerPoint
Inizializza un oggetto Presentation, che rappresenta una presentazione di PowerPoint:
```java
Presentation pres = new Presentation();
```
## Passaggio 2: aggiungi un fotogramma video
Ora aggiungiamo un fotogramma video alla presentazione. Questo frame conterrà il video dalla sorgente web. Utilizzeremo il metodo addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Sostituisci "VIDEO_ID" con l'ID del video YouTube che desideri incorporare.
## Passaggio 3: imposta la modalità di riproduzione video
Imposta la modalità di riproduzione per il fotogramma video. In questo esempio, lo imposteremo su Auto:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Passaggio 4: carica la miniatura
Per migliorare l'impatto visivo, caricheremo la miniatura del video. Questo passaggio prevede il recupero dell'immagine in miniatura dalla sorgente web:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Passaggio 5: salva la presentazione
Infine, salva la presentazione modificata:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Sostituisci "YOUR_DIRECTORY" con la directory in cui desideri salvare la presentazione.

## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere un fotogramma video da una fonte Web in PowerPoint utilizzando Aspose.Slides per Java. Incorporare elementi multimediali come i video può migliorare significativamente l'impatto e il coinvolgimento delle tue presentazioni.
## Domande frequenti
### Posso aggiungere video da fonti diverse da YouTube?
Sì, puoi aggiungere video da varie fonti web purché forniscano un collegamento incorporabile.
### Ho bisogno di una connessione Internet per riprodurre il video incorporato?
Sì, è necessaria una connessione Internet attiva per riprodurre in streaming il video dalla fonte web.
### Posso personalizzare l'aspetto del fotogramma video?
Assolutamente! Aspose.Slides offre ampie opzioni per personalizzare l'aspetto e il comportamento dei fotogrammi video.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta un'ampia gamma di versioni di PowerPoint, garantendo la compatibilità su diverse piattaforme.
### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides?
 Puoi visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per assistenza, documentazione e supporto comunitario.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
