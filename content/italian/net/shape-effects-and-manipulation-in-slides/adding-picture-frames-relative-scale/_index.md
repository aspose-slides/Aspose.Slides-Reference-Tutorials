---
title: Aggiunta di cornici con altezza relativa in scala in Aspose.Slides
linktitle: Aggiunta di cornici con altezza relativa in scala in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le tue presentazioni aggiungendo cornici con altezza in scala relativa utilizzando Aspose.Slides per .NET. Crea diapositive visivamente accattivanti senza sforzo.
type: docs
weight: 17
url: /it/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

## introduzione

Nel dinamico mondo delle presentazioni, gli elementi visivi svolgono un ruolo fondamentale nel trasmettere le informazioni in modo efficace. Aspose.Slides per .NET ti consente di andare oltre le nozioni di base e migliorare le tue presentazioni incorporando cornici con altezza in scala relativa. Questa guida ti guiderà attraverso il processo passo dopo passo, fornendoti le competenze per creare diapositive visivamente accattivanti che si distinguono. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato con Aspose.Slides, questa guida ti aiuterà a padroneggiare l'arte di aggiungere cornici con altezza in scala relativa.

## Aggiunta di cornici con altezza relativa in scala in Aspose.Slides

Quando si tratta di aggiungere cornici con altezza in scala relativa in Aspose.Slides, il processo è straordinariamente intuitivo. Segui questi passaggi per migliorare le tue presentazioni:

### Passaggio 1: inizializzare la presentazione

Inizia inizializzando l'oggetto di presentazione utilizzando il seguente codice:

```csharp
Presentation presentation = new Presentation();
```

### Passaggio 2: aggiungi una diapositiva

Per aggiungere una nuova diapositiva, utilizza il seguente snippet di codice:

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

### Passaggio 3: inserisci un'immagine

Ora è il momento di inserire l'immagine nella diapositiva. Il codice seguente illustra come ottenere questo risultato:

```csharp
byte[] imageBytes = File.ReadAllBytes("image.jpg");
IPPImage image = presentation.Images.AddImage(imageBytes);
slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, image.Width, image.Height, image);
```

### Passaggio 4: regolare l'altezza della scala

Per creare un'altezza in scala relativa per la cornice, utilizza lo snippet di codice riportato di seguito:

```csharp
IPictureFrame pictureFrame = (IPictureFrame)slide.Shapes[0];
pictureFrame.PictureFormat.Picture.ImageScale.HeightScale = 50; // Regolare la percentuale di scala come desiderato
```

## Domande frequenti

### Come posso modificare l'altezza della scala della cornice?

 Per modificare l'altezza della scala della cornice, è possibile utilizzare`PictureFormat.Picture.ImageScale.HeightScale` proprietà e assegnargli il valore percentuale desiderato.

### Posso aggiungere più cornici a una singola diapositiva?

Sì, puoi aggiungere più cornici a una singola diapositiva seguendo i passaggi menzionati in precedenza per ciascuna cornice che desideri inserire.

### È possibile animare le cornici delle immagini in una presentazione?

Assolutamente! Aspose.Slides offre potenti funzionalità di animazione. Puoi applicare animazioni alle cornici utilizzando vari effetti di animazione disponibili nella libreria.

### Quali formati di immagine sono supportati per l'inserimento?

Aspose.Slides supporta un'ampia gamma di formati di immagine, inclusi JPEG, PNG, GIF, BMP e altri. Puoi inserire facilmente immagini di questi formati nelle tue diapositive.

### Come posso impostare la posizione della cornice sulla diapositiva?

 È possibile impostare la posizione della cornice specificando le coordinate X e Y quando si aggiunge la cornice utilizzando`slide.Shapes.AddPictureFrame` metodo.

### È possibile personalizzare l'aspetto della cornice?

Sì, puoi personalizzare l'aspetto della cornice utilizzando proprietà come il colore del bordo, il colore di riempimento e altro. Fare riferimento alla documentazione di Aspose.Slides per informazioni dettagliate.

## Conclusione

Incorporare cornici con altezza in scala relativa nelle presentazioni può migliorare notevolmente il loro fascino visivo e il loro coinvolgimento. Con Aspose.Slides per .NET, il processo diventa semplice e personalizzabile, consentendoti di creare diapositive straordinarie che lasciano un impatto duraturo. Che tu stia creando contenuti didattici, presentazioni aziendali o vetrine creative, padroneggiare questa funzionalità migliorerà senza dubbio il tuo gioco di presentazione.

Ricorda, la chiave sta nella sperimentazione e nella creatività. Sfruttando la potenza di Aspose.Slides, non stai solo creando diapositive; stai creando esperienze coinvolgenti per il tuo pubblico.