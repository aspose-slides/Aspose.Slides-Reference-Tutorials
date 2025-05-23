---
"description": "Scopri come integrare perfettamente i frame degli oggetti OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java."
"linktitle": "Aggiungere un frame di oggetto OLE in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere un frame di oggetto OLE in PowerPoint"
"url": "/it/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere un frame di oggetto OLE in PowerPoint

## Introduzione
L'aggiunta di una cornice OLE (Object Linking and Embedding) nelle presentazioni di PowerPoint può migliorare significativamente l'aspetto e la funzionalità delle diapositive. Con Aspose.Slides per Java, questo processo diventa più semplice ed efficiente. In questo tutorial, vi guideremo attraverso i passaggi necessari per integrare perfettamente le cornici OLE nelle vostre presentazioni di PowerPoint.
### Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Ambiente di sviluppo Java: assicurati che Java Development Kit (JDK) sia installato sul tuo sistema.
2. Aspose.Slides per Java: scarica e installa Aspose.Slides per Java dal sito web [Qui](https://releases.aspose.com/slides/java/).
3. Nozioni di base sulla programmazione Java: familiarizzare con i concetti e la sintassi della programmazione Java.
## Importa pacchetti
Innanzitutto, è necessario importare i pacchetti necessari per sfruttare le funzionalità di Aspose.Slides per Java. Ecco come fare:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Passaggio 1: configura l'ambiente
Assicurati che il progetto sia configurato correttamente e che la libreria Aspose.Slides sia inclusa nel classpath.
## Passaggio 2: inizializzare l'oggetto di presentazione
Crea un oggetto Presentazione per rappresentare il file PowerPoint su cui stai lavorando:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Crea un'istanza della classe Presentazione che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva e carica l'oggetto
Accedi alla diapositiva in cui desideri aggiungere il frame dell'oggetto OLE e carica il file oggetto:
```java
ISlide sld = pres.getSlides().get_Item(0);
// Carica un file per lo streaming
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
Aggiungere una forma Cornice oggetto OLE alla diapositiva:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Passaggio 6: Salva la presentazione
Salva la presentazione modificata sul disco:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai imparato come aggiungere una cornice OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Questa potente funzionalità ti consente di incorporare vari tipi di oggetti, migliorando l'interattività e l'aspetto visivo delle tue diapositive.

## Domande frequenti
### Posso incorporare oggetti diversi dai file Excel utilizzando Aspose.Slides per Java?
Sì, puoi incorporare vari tipi di oggetti, tra cui documenti Word, file PDF e altro ancora.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides è compatibile con un'ampia gamma di versioni di PowerPoint, garantendo un'integrazione perfetta.
### Posso personalizzare l'aspetto della cornice dell'oggetto OLE?
Assolutamente sì! Aspose.Slides offre ampie opzioni per personalizzare l'aspetto e il comportamento dei frame degli oggetti OLE.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.Slides per Java?
Puoi cercare supporto e assistenza nel forum Aspose.Slides [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}