---
title: Creazione di forme di schizzo nelle diapositive della presentazione con Aspose.Slides
linktitle: Creazione di forme di schizzo nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare accattivanti diapositive di presentazione con forme abbozzate utilizzando Aspose.Slides per .NET. Segui questa guida passo passo con il codice sorgente completo per aggiungere elementi personalizzati e creativi alle tue diapositive.
type: docs
weight: 13
url: /it/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Introduzione alla creazione di forme di schizzo nelle diapositive della presentazione

Le diapositive di presentazione sono un potente strumento per trasmettere visivamente le informazioni. A volte, potresti voler aggiungere un tocco personale alle tue diapositive incorporando forme di schizzo, che possono rendere le tue presentazioni più coinvolgenti e creative. In questa guida passo passo, esploreremo come ottenere questo risultato utilizzando la libreria Aspose.Slides per .NET. Al termine di questo tutorial sarai in grado di creare diapositive di presentazione con forme abbozzate che risaltano. Immergiamoci!

## Impostazione del progetto

 Prima di iniziare, assicurati di avere l'ambiente di sviluppo .NET configurato sul tuo computer. È possibile scaricare l'ultima versione di Aspose.Slides dal sito Web[Qui](https://releases.aspose.com/slides/net/). Una volta scaricata, installa la libreria nel tuo progetto.

## Creazione di una nuova presentazione

Iniziamo creando una nuova presentazione utilizzando Aspose.Slides. Ecco come puoi farlo:

```csharp
using Aspose.Slides;

// Crea una nuova presentazione
Presentation presentation = new Presentation();
```

## Aggiunta di forme di schizzo

Per aggiungere forme di schizzo alle diapositive, puoi utilizzare forme a mano libera disponibili in Aspose.Slides. Queste forme possono essere personalizzate per assomigliare a schizzi disegnati a mano. Ecco un esempio di come aggiungere un rettangolo disegnato a una diapositiva:

```csharp
// Accedi alla prima diapositiva
ISlide slide = presentation.Slides[0];

// Definire i punti per il rettangolo schizzato
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Aggiungi una forma a mano libera alla diapositiva
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Personalizza l'aspetto della forma disegnata
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Personalizzazione delle forme abbozzate

È possibile personalizzare ulteriormente le forme di schizzo regolandone i colori, gli stili di linea e altre proprietà. Sperimenta diverse impostazioni per ottenere l'effetto disegnato a mano desiderato.

## Salvare ed esportare la presentazione

Dopo aver aggiunto le forme di schizzo alla presentazione, puoi salvarla ed esportarla in vari formati, come PPTX o PDF. Ecco come puoi farlo:

```csharp
// Salva la presentazione in un file
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo esplorato come creare diapositive di presentazione con forme di schizzo utilizzando Aspose.Slides per .NET. Aggiungendo forme di schizzo alle tue diapositive, puoi aggiungere un tocco creativo e personalizzato alle tue presentazioni, rendendole più coinvolgenti per il tuo pubblico. Sentiti libero di sperimentare diverse forme e opzioni di personalizzazione per creare diapositive visivamente accattivanti che lasciano un impatto duraturo.

## Domande frequenti

### Come posso scaricare Aspose.Slides per .NET?

 È possibile scaricare l'ultima versione di Aspose.Slides per .NET dalla pagina delle versioni[Qui](https://releases.aspose.com/slides/net/).

### Posso personalizzare l'aspetto delle forme disegnate?

Sì, puoi personalizzare l'aspetto delle forme di schizzo regolandone i colori, gli stili di linea e altre proprietà utilizzando Aspose.Slides.

### Aspose.Slides è adatto sia ai principianti che agli sviluppatori esperti?

Sì, Aspose.Slides fornisce un'API intuitiva adatta sia ai principianti che agli sviluppatori esperti. Offre una documentazione completa per aiutarti a iniziare.

### Posso esportare la mia presentazione con forme di schizzo in PDF?

Assolutamente! Puoi esportare la tua presentazione con forme di schizzo in vari formati, incluso PDF, utilizzando le opzioni di esportazione fornite da Aspose.Slides.

### Come posso aggiungere altri tipi di forme di schizzo, come cerchi o linee?

 Puoi aggiungere altri tipi di forme di schizzo, come cerchi o linee, modificando i punti e il tipo di forma nel file`AddFreeform` metodo. Sperimenta diverse configurazioni di punti per creare le forme che desideri.