---
title: Aggiungi cornice oggetto OLE in PowerPoint
linktitle: Aggiungi cornice oggetto OLE in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come integrare perfettamente i frame di oggetti OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java.
type: docs
weight: 13
url: /it/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---
## introduzione
L'aggiunta di una cornice oggetto OLE (collegamento e incorporamento di oggetti) nelle presentazioni di PowerPoint può migliorare in modo significativo l'attrattiva visiva e la funzionalità delle diapositive. Con Aspose.Slides per Java, questo processo diventa snello ed efficiente. In questo tutorial ti guideremo attraverso i passaggi necessari per integrare perfettamente i frame di oggetti OLE nelle tue presentazioni PowerPoint.
### Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1. Ambiente di sviluppo Java: assicurati di avere Java Development Kit (JDK) installato sul tuo sistema.
2. Aspose.Slides per Java: scaricare e installare Aspose.Slides per Java dal sito Web[Qui](https://releases.aspose.com/slides/java/).
3. Comprensione di base della programmazione Java: familiarizza con i concetti e la sintassi della programmazione Java.
## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per sfruttare le funzionalità di Aspose.Slides per Java. Ecco come puoi farlo:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Passaggio 1: configura il tuo ambiente
Assicurati che il tuo progetto sia configurato correttamente e che la libreria Aspose.Slides sia inclusa nel tuo classpath.
## Passaggio 2: inizializzare l'oggetto di presentazione
Crea un oggetto Presentazione per rappresentare il file PowerPoint con cui stai lavorando:
```java
String dataDir = "Your Document Directory";
String outPath = RunExamples.getOutPath();
// Crea un'istanza della classe Presentation che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva e carica l'oggetto
Accedi alla diapositiva in cui desideri aggiungere il frame oggetto OLE e carica il file oggetto:
```java
ISlide sld = pres.getSlides().get_Item(0);
// Carica un file da trasmettere in streaming
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## Passaggio 4: creare un oggetto dati incorporato
Crea un oggetto dati per incorporare il file:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## Passaggio 5: aggiungere la cornice dell'oggetto OLE
Aggiungi una forma cornice oggetto OLE alla diapositiva:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Passaggio 6: salva la presentazione
Salva la presentazione modificata su disco:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere un frame oggetto OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Questa potente funzionalità ti consente di incorporare vari tipi di oggetti, migliorando l'interattività e il fascino visivo delle tue diapositive.

## Domande frequenti
### Posso incorporare oggetti diversi dai file Excel utilizzando Aspose.Slides per Java?
Sì, puoi incorporare vari tipi di oggetti tra cui documenti Word, file PDF e altro.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides fornisce compatibilità con un'ampia gamma di versioni di PowerPoint, garantendo una perfetta integrazione.
### Posso personalizzare l'aspetto della cornice dell'oggetto OLE?
Assolutamente! Aspose.Slides offre ampie opzioni per personalizzare l'aspetto e il comportamento dei frame di oggetti OLE.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Slides per Java?
 Puoi chiedere supporto e assistenza al forum Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11).