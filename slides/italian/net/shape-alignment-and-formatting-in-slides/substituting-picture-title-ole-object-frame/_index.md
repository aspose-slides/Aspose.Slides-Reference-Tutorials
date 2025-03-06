---
title: Incorporamento della guida agli oggetti OLE con Aspose.Slides per .NET
linktitle: Sostituzione del titolo dell'immagine della cornice dell'oggetto OLE nelle diapositive della presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le diapositive della tua presentazione con oggetti OLE dinamici utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
weight: 15
url: /it/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
La creazione di diapositive di presentazione dinamiche e coinvolgenti spesso comporta l'incorporazione di vari elementi multimediali. In questo tutorial, esploreremo come sostituire il titolo dell'immagine di un frame di oggetti OLE (Object Linking and Embedding) nelle diapositive di presentazione utilizzando la potente libreria Aspose.Slides per .NET. Aspose.Slides semplifica il processo di gestione degli oggetti OLE, fornendo agli sviluppatori gli strumenti per migliorare facilmente le loro presentazioni.
## Prerequisiti
Prima di immergerci nella guida passo passo, assicurati di disporre dei seguenti prerequisiti:
-  Libreria Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides per .NET installata. Puoi scaricarlo da[Aspose.Slides Documentazione .NET](https://reference.aspose.com/slides/net/).
- Dati di esempio: prepara un file Excel di esempio (ad esempio, "ExcelObject.xlsx") che desideri incorporare come oggetto OLE nella presentazione. Inoltre, procurati un file immagine (ad esempio, "Image.png") che fungerà da icona per l'oggetto OLE.
- Ambiente di sviluppo: configura un ambiente di sviluppo con gli strumenti necessari, come Visual Studio o qualsiasi altro IDE preferito per lo sviluppo .NET.
## Importa spazi dei nomi
Nel tuo progetto .NET, assicurati di importare gli spazi dei nomi richiesti per lavorare con Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Passaggio 1: impostare la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
```
Assicurati di sostituire "La tua directory dei documenti" con il percorso effettivo della directory dei documenti.
## Passaggio 2: definire i percorsi del file di origine OLE e dei file di icone
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Aggiorna questi percorsi con i percorsi effettivi del file Excel e del file immagine di esempio.
## Passaggio 3: crea un'istanza di presentazione
```csharp
using (Presentation pres = new Presentation())
{
    // Il codice per i passaggi successivi andrà qui
}
```
 Inizializza una nuova istanza di`Presentation` classe.
## Passaggio 4: aggiungere la cornice dell'oggetto OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Aggiungi una cornice di oggetto OLE alla diapositiva, specificandone la posizione e le dimensioni.
## Passaggio 5: aggiungi oggetto immagine
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Leggi il file immagine e aggiungilo alla presentazione come oggetto immagine.
## Passaggio 6: imposta la didascalia sull'icona OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Imposta la didascalia desiderata per l'icona OLE.
## Conclusione
Incorporare oggetti OLE nelle diapositive della presentazione utilizzando Aspose.Slides per .NET è un processo semplice. Questo tutorial ti ha guidato attraverso i passaggi essenziali, dall'impostazione della directory dei documenti all'aggiunta e alla personalizzazione degli oggetti OLE. Sperimenta diversi tipi di file e didascalie per migliorare l'impatto visivo delle tue presentazioni.
## Domande frequenti
### Posso incorporare altri tipi di file come oggetti OLE utilizzando Aspose.Slides?
Sì, Aspose.Slides supporta l'incorporamento di vari tipi di file, come fogli di calcolo Excel, documenti Word e altro.
### L'icona dell'oggetto OLE è personalizzabile?
Assolutamente. Puoi sostituire l'icona predefinita con qualsiasi immagine di tua scelta per adattarla meglio al tema della presentazione.
### Aspose.Slides fornisce supporto per le animazioni con oggetti OLE?
partire dall'ultima versione, Aspose.Slides si concentra sull'incorporamento e sulla visualizzazione di oggetti OLE e non gestisce direttamente le animazioni all'interno degli oggetti OLE.
### Posso manipolare gli oggetti OLE a livello di codice dopo averli aggiunti a una diapositiva?
Certamente. Hai il controllo programmatico completo sugli oggetti OLE, consentendoti di modificarne le proprietà e l'aspetto secondo necessità.
### Esistono limitazioni alla dimensione degli oggetti OLE incorporati?
Sebbene esistano limiti di dimensione, generalmente sono generosi. Si consiglia di eseguire il test con il caso d'uso specifico per garantire prestazioni ottimali.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
