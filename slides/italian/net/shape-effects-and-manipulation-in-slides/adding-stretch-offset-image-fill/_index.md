---
"description": "Scopri come migliorare le presentazioni di PowerPoint con Aspose.Slides per .NET. Segui una guida passo passo per aggiungere un offset di estensione per il riempimento delle immagini."
"linktitle": "Aggiunta di offset di allungamento per il riempimento dell'immagine nelle diapositive"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aggiunta di offset di allungamento per il riempimento dell'immagine nelle presentazioni di PowerPoint"
"url": "/it/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiunta di offset di allungamento per il riempimento dell'immagine nelle presentazioni di PowerPoint

## Introduzione
Nel dinamico mondo delle presentazioni, gli elementi visivi svolgono un ruolo fondamentale nel catturare l'attenzione del pubblico. Aspose.Slides per .NET consente agli sviluppatori di migliorare le proprie presentazioni PowerPoint offrendo un solido set di funzionalità. Una di queste è la possibilità di aggiungere un offset di allungamento per il riempimento delle immagini, consentendo di realizzare diapositive creative e visivamente accattivanti.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Aspose.Slides per la libreria .NET: scarica e installa la libreria da [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/).
2. Ambiente di sviluppo: assicurati di aver configurato un ambiente di sviluppo .NET funzionante.
Ora iniziamo con la guida passo passo.
## Importa spazi dei nomi
Per prima cosa, importa gli spazi dei nomi necessari per sfruttare la funzionalità Aspose.Slides all'interno della tua applicazione .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto .NET nel tuo ambiente di sviluppo preferito. Assicurati che Aspose.Slides per .NET sia correttamente referenziato.
## Passaggio 2: inizializzare la classe di presentazione
Istanziare il `Presentation` classe per rappresentare il file PowerPoint.
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
## Passaggio 3: Ottieni la prima diapositiva
Recupera la prima diapositiva dalla presentazione con cui lavorare.
```csharp
ISlide sld = pres.Slides[0];
```
## Passaggio 4: creare un'istanza della classe ImageEx
Crea un'istanza di `ImageEx` classe per gestire l'immagine che vuoi aggiungere alla diapositiva.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Passaggio 5: aggiungere la cornice
Utilizzare il `AddPictureFrame` Metodo per aggiungere una cornice alla diapositiva. Specifica le dimensioni e la posizione della cornice.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Passaggio 6: Salva la presentazione
Salvare la presentazione modificata sul disco.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Ecco fatto! Hai aggiunto correttamente un offset di estensione per il riempimento delle immagini nelle diapositive utilizzando Aspose.Slides per .NET.
## Conclusione
Migliorare le tue presentazioni PowerPoint è ora più facile che mai con Aspose.Slides per .NET. Seguendo questo tutorial, hai imparato come integrare l'offset di allungamento per il riempimento delle immagini, portando un nuovo livello di creatività alle tue diapositive.
## Domande frequenti
### Posso utilizzare Aspose.Slides per .NET nelle mie applicazioni web?
Sì, Aspose.Slides per .NET è adatto sia per applicazioni desktop che web.
### È disponibile una prova gratuita di Aspose.Slides per .NET?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per .NET?
Visita il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.
### Dove posso trovare la documentazione completa per Aspose.Slides per .NET?
Fare riferimento al [documentazione](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
### Posso acquistare Aspose.Slides per .NET?
Sì, puoi acquistare il prodotto [Qui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}