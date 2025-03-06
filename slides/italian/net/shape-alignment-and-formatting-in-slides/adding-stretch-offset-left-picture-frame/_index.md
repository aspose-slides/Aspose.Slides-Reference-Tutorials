---
title: Aggiunta dell'offset allungamento a sinistra in PowerPoint con Aspose.Slide
linktitle: Aggiunta dell'offset allungamento a sinistra per la cornice in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per aggiungere l'offset stretch a sinistra per le cornici.
weight: 14
url: /it/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di manipolare facilmente le presentazioni PowerPoint. In questo tutorial, esploreremo il processo di aggiunta di un offset di stiramento a sinistra per una cornice utilizzando Aspose.Slides per .NET. Segui questa guida passo passo per migliorare le tue capacità di lavorare con immagini e forme all'interno delle presentazioni PowerPoint.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria installata. In caso contrario, scaricalo da[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).
- Ambiente di sviluppo: disporre di un ambiente di sviluppo funzionante con funzionalità .NET.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto o aprine uno esistente. Assicurati di avere la libreria Aspose.Slides referenziata nel tuo progetto.
## Passaggio 2: crea un oggetto di presentazione
 Istanziare il`Presentation` classe, che rappresenta il file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Il tuo codice per i passaggi successivi andrà qui.
}
```
## Passaggio 3: ottieni la prima diapositiva
Recupera la prima diapositiva della presentazione:
```csharp
ISlide slide = pres.Slides[0];
```
## Passaggio 4: istanziare l'immagine
Carica l'immagine che desideri utilizzare:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Passaggio 5: aggiungi la forma automatica rettangolare
Crea una forma automatica di tipo rettangolo:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Passaggio 6: impostare il tipo di riempimento e la modalità di riempimento immagine
Configura il tipo di riempimento della forma e la modalità di riempimento dell'immagine:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Passaggio 7: imposta l'immagine per riempire la forma
Specificare l'immagine per riempire la forma:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Passaggio 8: specificare gli offset di stiramento
Definisci gli offset dell'immagine dai bordi corrispondenti del riquadro di delimitazione della forma:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Passaggio 9: salva la presentazione
Scrivi il file PPTX su disco:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Congratulazioni! Hai aggiunto con successo un offset di stiramento a sinistra per una cornice utilizzando Aspose.Slides per .NET.
## Conclusione
In questo tutorial, abbiamo esplorato il processo di manipolazione delle cornici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Seguendo la guida passo passo, hai acquisito informazioni dettagliate su come lavorare con immagini, forme e offset.
## Domande frequenti
### D: Posso applicare spostamenti di stiramento ad altre forme oltre ai rettangoli?
R: Sebbene questo tutorial si concentri sui rettangoli, gli offset di allungamento possono essere applicati a varie forme supportate da Aspose.Slides.
### D: Come posso regolare gli offset di allungamento per effetti diversi?
R: Sperimenta diversi valori di offset per ottenere l'impatto visivo desiderato. Ottimizzare i valori in base alle proprie esigenze specifiche.
### D: Aspose.Slides è compatibile con l'ultimo framework .NET?
R: Aspose.Slides viene regolarmente aggiornato per garantire la compatibilità con le ultime versioni di .NET framework.
### D: Dove posso trovare ulteriori esempi e risorse per Aspose.Slides?
 R: Esplora il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/net/) per esempi e indicazioni esaustivi.
### D: Posso applicare più offset di stiramento a una singola forma?
R: Sì, puoi combinare più offset di stiramento per ottenere effetti visivi complessi e personalizzati.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
