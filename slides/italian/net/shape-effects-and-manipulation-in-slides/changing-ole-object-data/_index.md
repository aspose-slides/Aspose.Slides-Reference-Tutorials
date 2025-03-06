---
title: Modifica dei dati dell'oggetto OLE nella presentazione con Aspose.Slides
linktitle: Modifica dei dati dell'oggetto OLE nella presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Esplora la potenza di Aspose.Slides per .NET nel modificare facilmente i dati degli oggetti OLE. Migliora le tue presentazioni con contenuti dinamici.
weight: 25
url: /it/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifica dei dati dell'oggetto OLE nella presentazione con Aspose.Slides

## introduzione
La creazione di presentazioni PowerPoint dinamiche e interattive è un requisito comune nel mondo digitale di oggi. Uno strumento potente per raggiungere questo obiettivo è Aspose.Slides per .NET, una solida libreria che consente agli sviluppatori di manipolare e migliorare le presentazioni di PowerPoint a livello di codice. In questo tutorial, approfondiremo il processo di modifica dei dati degli oggetti OLE (Object Linking and Embedding) all'interno delle diapositive della presentazione utilizzando Aspose.Slides.
## Prerequisiti
Prima di iniziare a lavorare con Aspose.Slides per .NET, assicurati di disporre dei seguenti prerequisiti:
1. Ambiente di sviluppo: configura un ambiente di sviluppo con .NET installato.
2.  Libreria Aspose.Slides: scarica e installa la libreria Aspose.Slides per .NET. Puoi trovare la biblioteca[Qui](https://releases.aspose.com/slides/net/).
3. Comprensione di base: familiarizza con i concetti di base della programmazione C# e delle presentazioni PowerPoint.
## Importa spazi dei nomi
Nel tuo progetto C#, importa gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Passaggio 1: imposta il tuo progetto
Inizia creando un nuovo progetto C# e importando la libreria Aspose.Slides. Assicurati che il tuo progetto sia configurato correttamente e che disponi delle dipendenze richieste.
## Passaggio 2: accedi a presentazione e diapositiva
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Passaggio 3: individuare l'oggetto OLE
Attraversa tutte le forme nella diapositiva per trovare la cornice dell'oggetto OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Passaggio 4: leggere e modificare i dati della cartella di lavoro
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Lettura dei dati dell'oggetto nella cartella di lavoro
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modifica dei dati della cartella di lavoro
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Modifica dei dati dell'oggetto frame Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Passaggio 5: salva la presentazione
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusione
Seguendo questi passaggi, è possibile modificare senza problemi i dati degli oggetti OLE all'interno delle diapositive di presentazione utilizzando Aspose.Slides per .NET. Ciò apre un mondo di possibilità per creare presentazioni dinamiche e personalizzate su misura per le tue esigenze specifiche.
## Domande frequenti
### Cos'è Aspose.Slides per .NET?
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di lavorare con presentazioni PowerPoint a livello di codice, consentendo una facile manipolazione e miglioramento.
### Dove posso trovare la documentazione di Aspose.Slides?
 È possibile trovare la documentazione per Aspose.Slides per .NET[Qui](https://reference.aspose.com/slides/net/).
### Come posso scaricare Aspose.Slides per .NET?
 È possibile scaricare la libreria dalla pagina di rilascio[Qui](https://releases.aspose.com/slides/net/).
### È disponibile una prova gratuita per Aspose.Slides?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Slides per .NET?
 Per supporto e discussioni, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
