---
title: Creazione di una forma rettangolare semplice nelle diapositive di presentazione utilizzando Aspose.Slides
linktitle: Creazione di una forma rettangolare semplice nelle diapositive di presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare una semplice forma rettangolare nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Questa guida passo passo fornisce il codice sorgente e le istruzioni per aggiungere, personalizzare e migliorare le tue presentazioni a livello di codice.
type: docs
weight: 12
url: /it/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di lavorare con presentazioni PowerPoint a livello di codice. Fornisce un'ampia gamma di funzionalità per creare, manipolare e gestire elementi di presentazione, tra cui diapositive, forme, testo, immagini e altro ancora. In questa guida, ci concentreremo sulla creazione di una semplice forma rettangolare all'interno di una diapositiva di presentazione utilizzando le funzionalità di Aspose.Slides per .NET.

## Impostazione dell'ambiente di sviluppo

Prima di immergerci nel codice, impostiamo il nostro ambiente di sviluppo. Segui questi passi:

1.  Scarica Aspose.Slides per .NET: visita il[pagina di download](https://releases.aspose.com/slides/net/) e seleziona la versione compatibile con il tuo progetto.

2. Installa Aspose.Slides: dopo il download, installa Aspose.Slides aggiungendo il riferimento DLL al tuo progetto.

3. Crea un nuovo progetto: crea un nuovo progetto .NET utilizzando l'ambiente di sviluppo preferito (Visual Studio, ad esempio).

## Creazione di una nuova presentazione

Iniziamo creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides per .NET.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Crea una nuova presentazione
        Presentation presentation = new Presentation();

        // Aggiungi una diapositiva vuota alla presentazione
        Slide slide = presentation.Slides.AddEmptySlide();

        // Il tuo codice per aggiungere la forma del rettangolo andrà qui

        // Salva la presentazione
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## Aggiunta di una forma rettangolare alla diapositiva

Ora che abbiamo pronta la diapositiva della presentazione, procediamo ad aggiungervi una forma rettangolare.

```csharp
// Aggiungi una forma rettangolare alla diapositiva
double x = 100; // Coordinata X della forma
double y = 100; // Coordinata Y della forma
double width = 200; // Larghezza della forma
double height = 100; // Altezza della forma

slide.Shapes.AddRectangle(x, y, width, height);
```

## Personalizzazione della forma rettangolare

Puoi personalizzare vari aspetti della forma del rettangolo, come il colore di riempimento, lo stile del bordo e altro.

```csharp
// Ottieni la forma aggiunta (rettangolo)
IShape rectangle = slide.Shapes[0];

// Personalizza il colore di riempimento
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// Personalizza il bordo
rectangle.LineFormat.Width = 2; // Larghezza del bordo
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // Stile del bordo
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // Colore del bordo
```

## Salvataggio della presentazione

Dopo aver aggiunto e personalizzato la forma del rettangolo, è ora di salvare la presentazione.

```csharp
// Salva la presentazione
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## Conclusione

In questa guida, abbiamo esplorato come creare una semplice forma rettangolare all'interno di una diapositiva di presentazione utilizzando Aspose.Slides per .NET. Abbiamo coperto i passaggi fondamentali per impostare l'ambiente di sviluppo, creare una nuova presentazione, aggiungere una forma rettangolare, personalizzarne l'aspetto e salvare la presentazione finale. Con Aspose.Slides per .NET, puoi facilmente automatizzare e migliorare le tue presentazioni PowerPoint, aggiungendo uno strato di dinamismo e interattività.

## Domande frequenti

### Come installo Aspose.Slides per .NET?

Per installare Aspose.Slides per .NET, attenersi alla seguente procedura:

1.  Visitare il[pagina di download](https://releases.aspose.com/slides/net/).
2. Scegli la versione compatibile con il tuo progetto.
3. Aggiungi il riferimento DLL Aspose.Slides al tuo progetto .NET.

### Posso personalizzare il colore di riempimento della forma rettangolare?

 Sì, puoi personalizzare il colore di riempimento della forma rettangolare utilizzando`FillFormat` proprietà. Accedi semplicemente alla forma`FillFormat` e impostare quello desiderato`SolidFillColor`.

### Come posso salvare la presentazione dopo aver aggiunto la forma rettangolare?

È possibile salvare la presentazione utilizzando il file`Save` metodo del`Presentation` classe. Fornire il nome del file desiderato e il formato di salvataggio desiderato (ad esempio`SaveFormat.Pptx`).

### Aspose.Slides per .NET è adatto solo per forme rettangolari?

No, Aspose.Slides per .NET supporta un'ampia gamma di forme ed elementi di presentazione. Puoi creare e manipolare forme come rettangoli, cerchi, frecce e altro.

### Dove posso trovare ulteriore documentazione su Aspose.Slides per .NET?

 È possibile trovare documentazione dettagliata e riferimenti API per Aspose.Slides per .NET su[pagina della documentazione](https://reference.aspose.com/slides/net/).