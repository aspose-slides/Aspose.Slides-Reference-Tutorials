---
title: Aggiunta di un offset di stiramento per l'immagine Riempi le diapositive con Aspose.Slides
linktitle: Aggiunta di uno spostamento di stiramento per il riempimento di immagini nelle diapositive
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le diapositive della tua presentazione utilizzando Aspose.Slides per .NET. Questa guida passo passo illustra l'aggiunta dell'offset di stiramento per il riempimento dell'immagine, la creazione di immagini dinamiche e l'ottimizzazione del design.
type: docs
weight: 18
url: /it/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

Nelle presentazioni moderne, le immagini svolgono un ruolo cruciale nel trasmettere i messaggi in modo efficace. Aspose.Slides, una potente API per lavorare con file di presentazione in .NET, offre una funzionalità chiamata "Stretch Offset" che ti consente di controllare con precisione il modo in cui le immagini vengono riempite all'interno delle forme. Questo articolo ti guiderà attraverso il processo di aggiunta dell'offset allungato per il riempimento delle immagini nelle diapositive della presentazione utilizzando Aspose.Slides per .NET.

## Introduzione all'offset di stiramento

L'offset allungamento è una tecnica utile quando è necessario personalizzare il modo in cui le immagini vengono visualizzate all'interno delle forme. Ti consente di controllare la posizione e l'allineamento dell'immagine all'interno di una forma, consentendo di realizzare progetti di diapositive creativi e visivamente accattivanti. Utilizzando l'API Aspose.Slides, puoi implementare a livello di codice l'offset di allungamento e dare vita alle tue presentazioni.

## Configurazione dell'ambiente di sviluppo

 Prima di immergerci nell'implementazione, assicurati di avere Aspose.Slides per .NET installato nel tuo ambiente di sviluppo. Puoi scaricarlo dal sito web di Aspose[Link per scaricare](https://releases.aspose.com/slides/net/)Una volta scaricato, segui le istruzioni di installazione per configurare l'API per il tuo progetto.

## Aggiunta di un'immagine a una diapositiva

Per dimostrare la funzionalità di offset dell'allungamento, iniziamo aggiungendo un'immagine a una diapositiva utilizzando Aspose.Slides. Il seguente frammento di codice mostra come raggiungere questo obiettivo:

```csharp
// Istanziare un oggetto Presentazione
Presentation presentation = new Presentation();

// Accedi alla prima diapositiva
ISlide slide = presentation.Slides[0];

// Definire il percorso del file immagine
string imagePath = "path_to_your_image.jpg";

// Aggiungi un'immagine alla diapositiva
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// Salva la presentazione
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Applicazione dello spostamento di stiramento alle immagini

 Ora che abbiamo aggiunto un'immagine a una diapositiva, esploriamo come applicarvi l'offset di stiramento. L'offset di stiramento è controllato da due proprietà:`StretchX` E`StretchY`. Queste proprietà determinano l'offset dell'immagine all'interno della forma rispettivamente in orizzontale e in verticale.

Ecco come è possibile implementare l'offset allungamento utilizzando Aspose.Slides:

```csharp
// Accedi al formato di riempimento dell'immagine
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Applicare l'offset di stiramento
pictureFill.StretchX = 0.5; // Offset orizzontale del 50%
pictureFill.StretchY = -0.2; // Offset verticale del -20%
```

In questo esempio, abbiamo impostato un offset orizzontale del 50% e uno verticale del -20%. Il valore negativo per l'offset verticale sposta l'immagine verso l'alto all'interno della forma.

## Regolazione dei valori di offset dell'allungamento

 Trovare i valori di offset dell'allungamento perfetti potrebbe richiedere alcuni tentativi ed errori per ottenere l'effetto visivo desiderato. Regolare i valori di`StretchX` E`StretchY` per soddisfare le vostre preferenze di progettazione e allineamento. Sperimenta valori positivi e negativi per vedere come cambia il posizionamento dell'immagine.

## Utilizzo dell'offset stirato con forme diverse

 L'offset allungamento può essere applicato a vari tipi di forme, inclusi rettangoli, ellissi e altro. Il metodo di accesso al`PictureFillFormat` rimane coerente tra le forme. Sentiti libero di esplorare e sperimentare forme diverse per creare composizioni di diapositive uniche.

## Tecniche e suggerimenti avanzati

- Combina l'offset stiramento con altre funzionalità di formattazione per progetti complessi.
- Utilizza l'offset allungamento per enfatizzare parti specifiche di un'immagine all'interno di una forma.
-  Utilizza il`PictureFillFormat.TileAsTexture`proprietà per affiancare le immagini all'interno delle forme invece di allungarle.

## Conclusione

Incorporare l'offset allungato per il riempimento delle immagini nelle diapositive di presentazione utilizzando Aspose.Slides apre un mondo di possibilità creative. Con un controllo preciso sul posizionamento delle immagini, puoi migliorare l'impatto visivo delle tue presentazioni. Seguendo i passaggi descritti in questo articolo, hai imparato come sfruttare questa funzionalità in modo efficace.

## Domande frequenti

### Come posso scaricare Aspose.Slides per .NET?

 È possibile scaricare Aspose.Slides per .NET dal sito Web Aspose[Link per scaricare](https://releases.aspose.com/slides/net/).

### Posso utilizzare l'offset stretch con qualsiasi tipo di immagine?

Sì, l'offset allungamento può essere applicato a immagini di vari formati, inclusi JPG, PNG e altri.

###  Cosa succede se li imposto entrambi`StretchX` and `StretchY` to the same value?

L'impostazione di entrambe le proprietà sullo stesso valore mantiene le proporzioni dell'immagine spostandone la posizione all'interno della forma.

### L'offset di stiramento è compatibile con le animazioni?

Sì, l'offset allungato funziona perfettamente con le animazioni delle diapositive, consentendoti di creare presentazioni dinamiche.

### Come posso accedere alle opzioni avanzate di offset dello stiramento?

Esplora la documentazione di Aspose.Slides per informazioni approfondite sulle tecniche e sulle proprietà di stretch offset avanzate.