---
title: Modificare i dati dell'oggetto OLE in PowerPoint
linktitle: Modificare i dati dell'oggetto OLE in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come modificare i dati degli oggetti OLE in PowerPoint utilizzando Aspose.Slides per Java. Una guida passo passo per aggiornamenti semplici ed efficienti.
weight: 14
url: /it/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificare i dati dell'oggetto OLE in PowerPoint

## introduzione
La modifica dei dati degli oggetti OLE nelle presentazioni di PowerPoint può essere un'attività cruciale quando è necessario aggiornare il contenuto incorporato senza modificare manualmente ciascuna diapositiva. Questa guida completa ti guiderà attraverso il processo utilizzando Aspose.Slides per Java, una potente libreria progettata per la gestione delle presentazioni PowerPoint. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, troverai questo tutorial utile e facile da seguire.
## Prerequisiti
Prima di immergerci nel codice, assicuriamoci di avere tutto il necessario per iniziare.
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[Il sito di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides per Java: scarica l'ultima versione da[Pagina di download di Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): è possibile utilizzare qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
4.  Aspose.Cells per Java: è necessario per modificare i dati incorporati all'interno dell'oggetto OLE. Scaricalo da[Pagina di download di Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  File di presentazione: preparare un file PowerPoint con un oggetto OLE incorporato. Per questo tutorial, diamogli un nome`ChangeOLEObjectData.pptx`.
## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari nel tuo progetto Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Ora suddividiamo il processo in passaggi semplici e gestibili.
## Passaggio 1: carica la presentazione di PowerPoint
Per iniziare è necessario caricare la presentazione PowerPoint contenente l'oggetto OLE.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Passaggio 2: accedi alla diapositiva contenente l'oggetto OLE
Successivamente, ottieni la diapositiva in cui è incorporato l'oggetto OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 3: trova l'oggetto OLE nella diapositiva
Scorrere le forme nella diapositiva per individuare l'oggetto OLE.
```java
OleObjectFrame ole = null;
// Attraversando tutte le forme per il telaio Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Passaggio 4: estrarre i dati incorporati dall'oggetto OLE
Se viene trovato l'oggetto OLE, estrarne i dati incorporati.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Passaggio 5: modificare i dati incorporati utilizzando Aspose.Cells
Ora utilizza Aspose.Cells per leggere e modificare i dati incorporati, che in questo caso è probabilmente una cartella di lavoro di Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modificare i dati della cartella di lavoro
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Passaggio 6: salvare nuovamente i dati modificati nell'oggetto OLE
Dopo aver apportato le modifiche necessarie, salvare nuovamente la cartella di lavoro modificata nell'oggetto OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Passaggio 7: salva la presentazione aggiornata
Infine, salva la presentazione PowerPoint aggiornata.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusione
L'aggiornamento dei dati degli oggetti OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java è un processo semplice una volta suddiviso in semplici passaggi. Questa guida ti ha guidato attraverso il caricamento di una presentazione, l'accesso e la modifica dei dati OLE incorporati e il salvataggio della presentazione aggiornata. Con questi passaggi è possibile gestire e aggiornare in modo efficiente il contenuto incorporato nelle diapositive di PowerPoint a livello di codice.
## Domande frequenti
### Che cos'è un oggetto OLE in PowerPoint?
Un oggetto OLE (Object Linking and Embedding) consente di incorporare contenuti da altre applicazioni, come fogli di calcolo Excel, in diapositive di PowerPoint.
### Posso utilizzare Aspose.Slides con altri linguaggi di programmazione?
Sì, Aspose.Slides supporta diversi linguaggi tra cui .NET, Python e C++.
### Ho bisogno di Aspose.Cells per modificare gli oggetti OLE in PowerPoint?
Sì, se l'oggetto OLE è un foglio di calcolo Excel, avrai bisogno di Aspose.Cells per modificarlo.
### Esiste una versione di prova di Aspose.Slides?
 Sì, puoi ottenere un[prova gratuita](https://releases.aspose.com/) per testare le funzionalità di Aspose.Slides.
### Dove posso trovare la documentazione per Aspose.Slides?
 È possibile trovare documentazione dettagliata su[Pagina della documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
