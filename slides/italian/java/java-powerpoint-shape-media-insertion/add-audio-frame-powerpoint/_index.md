---
title: Aggiungi cornice audio in PowerPoint
linktitle: Aggiungi cornice audio in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere fotogrammi audio alle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Migliora le tue presentazioni con elementi audio accattivanti senza sforzo.
weight: 12
url: /it/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
Migliorare le presentazioni con elementi audio può aumentarne significativamente l'impatto e il coinvolgimento. Con Aspose.Slides per Java, l'integrazione di frame audio nelle presentazioni PowerPoint diventa un processo senza interruzioni. Questo tutorial ti guiderà attraverso il processo passo passo di aggiunta di frame audio alle tue presentazioni utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
2.  Aspose.Slides per la libreria Java: scarica e installa la libreria Aspose.Slides per Java. Puoi scaricarlo da[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).
3. File audio: prepara il file audio (ad esempio, formato WAV) che desideri aggiungere alla presentazione.
## Importa pacchetti
Importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Passaggio 1: imposta la directory del progetto
Assicurati di avere una struttura di directory impostata per il tuo progetto. In caso contrario, creane uno per organizzare i tuoi file in modo efficace.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## Passaggio 2: istanziare la lezione di presentazione
 Istanziare il`Presentation` classe per rappresentare la presentazione di PowerPoint.
```java
Presentation pres = new Presentation();
```
## Passaggio 3: ottieni la diapositiva e carica il file audio
Recupera la prima diapositiva e carica il file audio dalla tua directory.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## Passaggio 4: aggiungi cornice audio
Aggiungi il fotogramma audio alla diapositiva.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Passaggio 5: imposta le proprietà audio
Imposta proprietà come la riproduzione tra diapositive, il riavvolgimento dell'audio, la modalità di riproduzione e il volume.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## Passaggio 6: salva la presentazione
Salva la presentazione modificata con il fotogramma audio aggiunto.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Incorporare elementi audio nelle tue presentazioni PowerPoint può migliorarne l'efficacia e affascinare il tuo pubblico. Con Aspose.Slides per Java, il processo di aggiunta di frame audio diventa semplice, consentendoti di creare presentazioni dinamiche e coinvolgenti senza sforzo.

## Domande frequenti
### Posso aggiungere file audio di formati diversi alla mia presentazione?
Sì, Aspose.Slides per Java supporta vari formati audio, inclusi WAV, MP3 e altri.
### È possibile regolare i tempi di riproduzione dell'audio nelle diapositive?
Assolutamente. È possibile sincronizzare la riproduzione audio con transizioni di diapositive specifiche utilizzando Aspose.Slides per Java.
### Aspose.Slides per Java fornisce supporto per la compatibilità multipiattaforma?
Sì, puoi creare presentazioni PowerPoint con fotogrammi audio incorporati compatibili su diverse piattaforme.
### Posso personalizzare l'aspetto del lettore audio nella presentazione?
Aspose.Slides per Java offre ampie opzioni di personalizzazione, che ti consentono di personalizzare l'aspetto del lettore audio in base alle tue preferenze.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi accedere a una prova gratuita di Aspose.Slides per Java dal loro[sito web](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
