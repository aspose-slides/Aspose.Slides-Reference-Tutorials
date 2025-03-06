---
title: Aggiunta di uno spostamento di stiramento per il riempimento di immagini nelle presentazioni di PowerPoint
linktitle: Aggiunta di uno spostamento di stiramento per il riempimento di immagini nelle diapositive
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le presentazioni di PowerPoint con Aspose.Slides per .NET. Segui una guida passo passo per aggiungere un offset di stiramento per il riempimento dell'immagine.
weight: 18
url: /it/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiunta di uno spostamento di stiramento per il riempimento di immagini nelle presentazioni di PowerPoint

## introduzione
Nel dinamico mondo delle presentazioni, le immagini svolgono un ruolo fondamentale nel catturare l'attenzione del pubblico. Aspose.Slides per .NET consente agli sviluppatori di migliorare le loro presentazioni PowerPoint fornendo un solido set di funzionalità. Una di queste funzionalità è la possibilità di aggiungere un offset di stiramento per il riempimento dell'immagine, consentendo diapositive creative e visivamente accattivanti.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1.  Aspose.Slides per .NET Library: scarica e installa la libreria da[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).
2. Ambiente di sviluppo: assicurati di avere configurato un ambiente di sviluppo .NET funzionante.
Ora iniziamo con la guida passo passo.
## Importa spazi dei nomi
Innanzitutto, importa gli spazi dei nomi necessari per sfruttare la funzionalità Aspose.Slides all'interno della tua applicazione .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto .NET nel tuo ambiente di sviluppo preferito. Assicurarsi che Aspose.Slides per .NET sia correttamente referenziato.
## Passaggio 2: inizializzare la classe di presentazione
 Istanziare il`Presentation` classe per rappresentare il file PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Il tuo codice va qui
}
```
## Passaggio 3: ottieni la prima diapositiva
Recupera la prima diapositiva della presentazione su cui lavorare.
```csharp
ISlide sld = pres.Slides[0];
```
## Passaggio 4: creare un'istanza della classe ImageEx
 Crea un'istanza di`ImageEx`classe per gestire l'immagine che desideri aggiungere alla diapositiva.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Passaggio 5: aggiungi la cornice
 Utilizza il`AddPictureFrame` metodo per aggiungere una cornice alla diapositiva. Specificare le dimensioni e la posizione della cornice.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Passaggio 6: salva la presentazione
Salva la presentazione modificata su disco.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Questo è tutto! Hai aggiunto con successo un offset di stiramento per il riempimento delle immagini nelle diapositive utilizzando Aspose.Slides per .NET.
## Conclusione
Migliorare le tue presentazioni PowerPoint è ora più facile che mai con Aspose.Slides per .NET. Seguendo questo tutorial, hai imparato come incorporare l'offset allungamento per il riempimento dell'immagine, portando un nuovo livello di creatività nelle tue diapositive.
## Domande frequenti
### Posso utilizzare Aspose.Slides per .NET nelle mie applicazioni web?
Sì, Aspose.Slides per .NET è adatto sia per applicazioni desktop che web.
### È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per .NET?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.
### Dove posso trovare la documentazione completa per Aspose.Slides per .NET?
 Fare riferimento al[documentazione](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
### Posso acquistare Aspose.Slides per .NET?
 Sì, puoi acquistare il prodotto[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
