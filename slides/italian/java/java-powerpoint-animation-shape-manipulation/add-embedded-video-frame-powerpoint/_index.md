---
title: Aggiungi frame video incorporato in PowerPoint
linktitle: Aggiungi frame video incorporato in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come incorporare fotogrammi video in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial passo passo. Migliora facilmente le tue presentazioni.
weight: 21
url: /it/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi frame video incorporato in PowerPoint

## introduzione
L'aggiunta di video alle presentazioni PowerPoint può renderle più coinvolgenti e informative. Utilizzando Aspose.Slides per Java, puoi facilmente incorporare video direttamente nelle tue diapositive. In questo tutorial ti guideremo attraverso il processo passo dopo passo, assicurandoti di comprendere ogni parte del codice e come funziona. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti aiuterà a migliorare le tue presentazioni con video incorporati.
## Prerequisiti
Prima di immergerti nel codice, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer.
2. Aspose.Slides per Java: scarica e installa la libreria Aspose.Slides per Java.
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse per una migliore esperienza di sviluppo.
4. File video: disponi di un file video che desideri incorporare nella presentazione di PowerPoint.
## Importa pacchetti
Innanzitutto, dovrai importare i pacchetti necessari per lavorare con Aspose.Slides. Queste importazioni ti aiuteranno a gestire diapositive, video e file di presentazione.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Passaggio 1: configura il tuo ambiente
Prima di iniziare a scrivere codice, assicurati che il tuo ambiente sia configurato correttamente. Ciò comporta la creazione delle directory necessarie e la preparazione del file video.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Crea directory se non è già presente.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Passaggio 2: istanziare la lezione di presentazione
 Crea un'istanza di`Presentation` classe. Questa classe rappresenta il tuo file PowerPoint.
```java
// Crea un'istanza della classe Presentation che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: ottieni la prima diapositiva
Accedi alla prima diapositiva della presentazione in cui incorporerai il video.
```java
// Ottieni la prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungi il video alla presentazione
Incorpora il file video nella presentazione. Assicurati che il percorso video sia specificato correttamente.
```java
// Incorpora il video nella presentazione
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Passaggio 5: aggiungi un fotogramma video alla diapositiva
Crea un fotogramma video sulla diapositiva e impostane le dimensioni e la posizione.
```java
// Aggiungi fotogramma video
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Passaggio 6: configurare le proprietà del fotogramma video
Imposta il video sul fotogramma video e configura le sue impostazioni di riproduzione come modalità di riproduzione e volume.
```java
// Imposta il video su Fotogramma video
vf.setEmbeddedVideo(vid);
// Imposta la modalità di riproduzione e il volume del video
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Passaggio 7: salva la presentazione
Salva la presentazione con il video incorporato nella directory specificata.
```java
// Scrivi il file PPTX su disco
pres.save(resultPath, SaveFormat.Pptx);
```
## Passaggio 8: ripulire le risorse
Infine, elimina l'oggetto di presentazione per liberare risorse.
```java
// Smaltire l'oggetto della presentazione
if (pres != null) pres.dispose();
```
## Conclusione
Incorporare un video nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java è un processo semplice. Seguendo i passaggi descritti in questa guida, puoi migliorare le tue presentazioni con contenuti video accattivanti. Ricorda, la pratica rende perfetti, quindi prova a incorporare video diversi e a modificare le loro proprietà per vedere cosa funziona meglio per le tue esigenze.
## Domande frequenti
### Posso incorporare più video in una singola diapositiva?
Sì, puoi incorporare più video in una singola diapositiva aggiungendo più fotogrammi video.
### Come posso controllare la riproduzione del video?
 È possibile controllare la riproduzione utilizzando`setPlayMode` E`setVolume` metodi del`IVideoFrame` classe.
### Quali formati video sono supportati da Aspose.Slides?
Aspose.Slides supporta vari formati video tra cui MP4, AVI e WMV.
### Ho bisogno di una licenza per utilizzare Aspose.Slides?
Sì, è necessaria una licenza valida per utilizzare Aspose.Slides. È possibile ottenere una licenza temporanea per la valutazione.
### Posso personalizzare le dimensioni e la posizione del fotogramma video?
Sì, puoi personalizzare le dimensioni e la posizione impostando i parametri appropriati quando aggiungi il fotogramma video.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
