---
"description": "Scopri come modificare i dati degli oggetti OLE in PowerPoint utilizzando Aspose.Slides per Java. Una guida passo passo per aggiornamenti semplici ed efficienti."
"linktitle": "Modificare i dati degli oggetti OLE in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Modificare i dati degli oggetti OLE in PowerPoint"
"url": "/it/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Modificare i dati degli oggetti OLE in PowerPoint

## Introduzione
Modificare i dati degli oggetti OLE nelle presentazioni di PowerPoint può essere un'operazione cruciale quando è necessario aggiornare il contenuto incorporato senza dover modificare manualmente ogni diapositiva. Questa guida completa vi guiderà attraverso il processo utilizzando Aspose.Slides per Java, una potente libreria progettata per la gestione delle presentazioni di PowerPoint. Che siate sviluppatori esperti o alle prime armi, troverete questo tutorial utile e facile da seguire.
## Prerequisiti
Prima di immergerci nel codice, assicuriamoci di avere tutto il necessario per iniziare.
1. Java Development Kit (JDK): assicurati di aver installato il JDK sul tuo sistema. Puoi scaricarlo da [Sito di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides per Java: scarica l'ultima versione da [Pagina di download di Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): puoi utilizzare qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
4. Aspose.Cells per Java: necessario per modificare i dati incorporati nell'oggetto OLE. Scaricalo da [Pagina di download di Aspose.Cells](https://releases.aspose.com/cells/java/).
5. File di presentazione: prepara un file PowerPoint con un oggetto OLE incorporato. Per questo tutorial, diamogli un nome. `ChangeOLEObjectData.pptx`.
## Importa pacchetti
Per prima cosa, importiamo i pacchetti necessari nel tuo progetto Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Ora scomponiamo il processo in passaggi semplici e gestibili.
## Passaggio 1: caricare la presentazione di PowerPoint
Per iniziare, è necessario caricare la presentazione PowerPoint contenente l'oggetto OLE.
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Passaggio 2: accedere alla diapositiva contenente l'oggetto OLE
Successivamente, occorre ottenere la diapositiva in cui è incorporato l'oggetto OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 3: trova l'oggetto OLE nella diapositiva
Scorrere le forme nella diapositiva per individuare l'oggetto OLE.
```java
OleObjectFrame ole = null;
// Attraversamento di tutte le forme per Ole frame
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Passaggio 4: estrarre i dati incorporati dall'oggetto OLE
Se l'oggetto OLE viene trovato, estrarne i dati incorporati.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Passaggio 5: modificare i dati incorporati utilizzando Aspose.Cells
Ora, utilizziamo Aspose.Cells per leggere e modificare i dati incorporati, che in questo caso sono probabilmente una cartella di lavoro di Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modificare i dati della cartella di lavoro
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Passaggio 6: salvare i dati modificati nell'oggetto OLE
Dopo aver apportato le modifiche necessarie, salvare nuovamente la cartella di lavoro modificata nell'oggetto OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Passaggio 7: salvare la presentazione aggiornata
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
Aggiornare i dati degli oggetti OLE nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java è un processo semplice, se suddiviso in semplici passaggi. Questa guida vi ha illustrato come caricare una presentazione, accedere e modificare i dati OLE incorporati e salvare la presentazione aggiornata. Con questi passaggi, potete gestire e aggiornare in modo efficiente i contenuti incorporati nelle diapositive di PowerPoint a livello di codice.
## Domande frequenti
### Che cosa è un oggetto OLE in PowerPoint?
Un oggetto OLE (Object Linking and Embedding) consente di incorporare contenuti da altre applicazioni, come fogli di calcolo Excel, nelle diapositive di PowerPoint.
### Posso usare Aspose.Slides con altri linguaggi di programmazione?
Sì, Aspose.Slides supporta diversi linguaggi, tra cui .NET, Python e C++.
### Ho bisogno di Aspose.Cells per modificare gli oggetti OLE in PowerPoint?
Sì, se l'oggetto OLE è un foglio di calcolo Excel, per modificarlo sarà necessario Aspose.Cells.
### Esiste una versione di prova di Aspose.Slides?
Sì, puoi ottenere un [prova gratuita](https://releases.aspose.com/) per testare le funzionalità di Aspose.Slides.
### Dove posso trovare la documentazione per Aspose.Slides?
Puoi trovare la documentazione dettagliata su [Pagina di documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}