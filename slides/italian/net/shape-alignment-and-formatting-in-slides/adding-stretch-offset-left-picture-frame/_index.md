---
"description": "Scopri come migliorare le presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per aggiungere un offset di allungamento a sinistra per le cornici delle immagini."
"linktitle": "Aggiunta di offset di allungamento a sinistra per la cornice dell'immagine in Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aggiungere l'offset di allungamento a sinistra in PowerPoint con Aspose.Slide"
"url": "/it/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere l'offset di allungamento a sinistra in PowerPoint con Aspose.Slide

## Introduzione
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di manipolare facilmente le presentazioni di PowerPoint. In questo tutorial, esploreremo il processo di aggiunta di un offset di estensione a sinistra per una cornice per immagini utilizzando Aspose.Slides per .NET. Segui questa guida passo passo per migliorare le tue competenze nell'utilizzo di immagini e forme nelle presentazioni di PowerPoint.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria. In caso contrario, scaricala da [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/).
- Ambiente di sviluppo: disporre di un ambiente di sviluppo funzionante con funzionalità .NET.
## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nel tuo progetto .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto o aprine uno esistente. Assicurati di aver fatto riferimento alla libreria Aspose.Slides nel tuo progetto.
## Passaggio 2: creare un oggetto di presentazione
Istanziare il `Presentation` classe, che rappresenta il file PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Qui verrà inserito il codice per i passaggi successivi.
}
```
## Passaggio 3: Ottieni la prima diapositiva
Recupera la prima diapositiva dalla presentazione:
```csharp
ISlide slide = pres.Slides[0];
```
## Passaggio 4: creare un'istanza dell'immagine
Carica l'immagine che vuoi utilizzare:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Passaggio 5: aggiungere la forma automatica del rettangolo
Crea una forma automatica di tipo rettangolo:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Passaggio 6: imposta il tipo di riempimento e la modalità di riempimento dell'immagine
Configura il tipo di riempimento della forma e la modalità di riempimento dell'immagine:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Passaggio 7: imposta l'immagine per riempire la forma
Specificare l'immagine con cui riempire la forma:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Passaggio 8: specificare gli offset di allungamento
Definisci gli offset dell'immagine dai bordi corrispondenti del riquadro di delimitazione della forma:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Passaggio 9: Salva la presentazione
Scrivere il file PPTX sul disco:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Congratulazioni! Hai aggiunto con successo un offset di estensione a sinistra per una cornice per immagini utilizzando Aspose.Slides per .NET.
## Conclusione
In questo tutorial abbiamo esplorato il processo di manipolazione delle cornici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Seguendo la guida passo passo, hai acquisito nozioni su come lavorare con immagini, forme e offset.
## Domande frequenti
### D: Posso applicare gli offset di estensione anche ad altre forme oltre ai rettangoli?
R: Sebbene questo tutorial si concentri sui rettangoli, gli offset di estensione possono essere applicati a varie forme supportate da Aspose.Slides.
### D: Come posso regolare gli offset di allungamento per ottenere effetti diversi?
R: Sperimenta diversi valori di offset per ottenere l'impatto visivo desiderato. Regola i valori in base alle tue esigenze specifiche.
### D: Aspose.Slides è compatibile con l'ultimo framework .NET?
R: Aspose.Slides viene aggiornato regolarmente per garantire la compatibilità con le ultime versioni del framework .NET.
### D: Dove posso trovare ulteriori esempi e risorse per Aspose.Slides?
A: Esplora il [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/net/) per esempi e indicazioni esaustivi.
### D: Posso applicare più offset di allungamento a una singola forma?
R: Sì, è possibile combinare più offset di estensione per ottenere effetti visivi complessi e personalizzati.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}