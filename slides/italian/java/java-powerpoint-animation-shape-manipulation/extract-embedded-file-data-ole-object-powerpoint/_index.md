---
title: Estrai i dati del file incorporato dall'oggetto OLE in PowerPoint
linktitle: Estrai i dati del file incorporato dall'oggetto OLE in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come estrarre i dati dei file incorporati dalle presentazioni di PowerPoint utilizzando Aspose.Slides per Java, migliorando le funzionalità di gestione dei documenti.
type: docs
weight: 22
url: /it/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/
---

## introduzione
Nel campo della programmazione Java, l'estrazione dei dati dei file incorporati dagli oggetti OLE (Object Linking and Embedding) all'interno delle presentazioni PowerPoint è un compito che si presenta spesso, in particolare nelle applicazioni di gestione dei documenti o di estrazione dei dati. Aspose.Slides per Java offre una soluzione solida per la gestione delle presentazioni PowerPoint a livello di codice. In questo tutorial esploreremo come estrarre i dati dei file incorporati da oggetti OLE utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di approfondire il tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza base della programmazione Java.
- JDK (Java Development Kit) installato sul tuo sistema.
- Aspose.Slides per la libreria Java scaricata e referenziata nel tuo progetto.

## Importa pacchetti
Innanzitutto, assicurati di importare i pacchetti necessari nel tuo progetto Java per utilizzare le funzionalità fornite da Aspose.Slides per Java.
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

Ora suddividiamo il processo in più passaggi:
## Passaggio 1: fornire il percorso della directory dei documenti
```java
String dataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso della directory contenente la presentazione di PowerPoint.
## Passaggio 2: specificare il nome del file PowerPoint
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
 Assicurarsi di sostituire`"TestOlePresentation.pptx"` con il nome del file di presentazione di PowerPoint.
## Passaggio 3: caricare la presentazione
```java
Presentation pres = new Presentation(pptxFileName);
```
 Questa riga inizializza una nuova istanza di`Presentation` classe, caricando il file di presentazione PowerPoint specificato.
## Passaggio 4: scorrere diapositive e forme
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
Qui, iteriamo attraverso ogni diapositiva e forma all'interno della presentazione.
## Passaggio 5: verificare la presenza di oggetto OLE
```java
if (shape instanceof OleObjectFrame) {
```
Questa condizione controlla se la forma è un oggetto OLE.
## Passaggio 6: estrazione dei dati del file incorporato
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
Se la forma è un oggetto OLE, estraiamo i dati del file incorporato.
## Passaggio 7: determinare l'estensione del file
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
Questa riga recupera l'estensione del file incorporato estratto.
## Passaggio 8: salva il file estratto
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
Infine, salviamo i dati del file estratto nella directory specificata.

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare Aspose.Slides per Java per estrarre i dati dei file incorporati da oggetti OLE all'interno delle presentazioni di PowerPoint. Seguendo i passaggi forniti, puoi integrare perfettamente questa funzionalità nelle tue applicazioni Java, migliorando le capacità di gestione dei documenti.
## Domande frequenti
### Aspose.Slides può estrarre dati da tutti i tipi di oggetti incorporati?
Aspose.Slides fornisce un ampio supporto per l'estrazione di dati da vari oggetti incorporati, inclusi oggetti OLE, grafici e altro.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Sì, Aspose.Slides garantisce la compatibilità con le presentazioni PowerPoint in diverse versioni, garantendo un'estrazione senza interruzioni dei dati incorporati.
### Aspose.Slides richiede una licenza per uso commerciale?
 Sì, è necessaria una licenza valida per l'uso commerciale di Aspose.Slides. È possibile ottenere una licenza da Aspose[sito web](https://purchase.aspose.com/temporary-license/).
### Posso automatizzare il processo di estrazione utilizzando Aspose.Slides?
Assolutamente, Aspose.Slides fornisce API complete per automatizzare attività come l'estrazione dei dati di file incorporati, consentendo un'elaborazione dei documenti efficiente e semplificata.
### Dove posso trovare ulteriore assistenza o supporto per Aspose.Slides?
 Per qualsiasi domanda, assistenza tecnica o supporto della community, puoi visitare il forum Aspose.Slides o fare riferimento alla documentazione[Aspose.Slides](https://reference.aspose.com/slides/java/).