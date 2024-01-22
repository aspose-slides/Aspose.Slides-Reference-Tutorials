---
title: Tutorial sull'aggiunta di cornici con Aspose.Slides .NET
linktitle: Aggiunta di cornici con altezza relativa in scala in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Impara ad aggiungere cornici con altezza di scala relativa in Aspose.Slides per .NET. Segui questa guida passo passo per presentazioni senza interruzioni.
type: docs
weight: 17
url: /it/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## introduzione
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint nelle loro applicazioni .NET senza sforzo. In questo tutorial, approfondiremo il processo di aggiunta di cornici con altezza in scala relativa utilizzando Aspose.Slides per .NET. Segui questa guida passo passo per migliorare le tue capacità di creazione di presentazioni.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio o qualsiasi altro ambiente di sviluppo C# preferito installato.
- Libreria Aspose.Slides per .NET aggiunta al tuo progetto.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel codice C#. Questo passaggio garantisce l'accesso alle classi e alle funzionalità fornite dalla libreria Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: imposta il tuo progetto
Inizia creando un nuovo progetto C# nel tuo ambiente di sviluppo preferito. Assicurati di aggiungere la libreria Aspose.Slides per .NET al tuo progetto facendovi riferimento.
## Passaggio 2: carica la presentazione e l'immagine
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Carica immagine da aggiungere alla raccolta di immagini di presentazione
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
In questo passaggio creiamo un nuovo oggetto di presentazione e carichiamo l'immagine che vogliamo aggiungere alla presentazione.
## Passaggio 3: aggiungi la cornice alla diapositiva
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Ora aggiungi una cornice alla prima diapositiva della presentazione. Regola i parametri come tipo di forma, posizione e dimensioni in base alle tue esigenze.
## Passaggio 4: impostare la larghezza e l'altezza della scala relativa
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Impostare l'altezza e la larghezza della scala relativa per la cornice dell'immagine per ottenere l'effetto di ridimensionamento desiderato.
## Passaggio 5: salva la presentazione
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Infine, salva la presentazione con la cornice aggiunta nel formato di output specificato.
## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere cornici con altezza relativa in scala utilizzando Aspose.Slides per .NET. Sperimenta immagini, posizioni e scale diverse per creare presentazioni visivamente accattivanti su misura per le tue esigenze.
## Domande frequenti
### Posso utilizzare Aspose.Slides per .NET con altri linguaggi di programmazione?
Aspose.Slides supporta principalmente i linguaggi .NET, ma puoi esplorare altri prodotti Aspose per la compatibilità con piattaforme diverse.
### Dove posso trovare la documentazione dettagliata per Aspose.Slides per .NET?
 Fare riferimento al[documentazione](https://reference.aspose.com/slides/net/) per informazioni complete ed esempi.
### È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi ottenere un[prova gratuita](https://releases.aspose.com/) valutare le capacità della biblioteca.
### Come posso ottenere supporto per Aspose.Slides per .NET?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) chiedere assistenza alla comunità e agli esperti di Aspose.
### Dove posso acquistare Aspose.Slides per .NET?
 È possibile acquistare Aspose.Slides per .NET da[pagina di acquisto](https://purchase.aspose.com/buy).