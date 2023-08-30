---
title: Riempimento di forme con gradiente nelle diapositive della presentazione utilizzando Aspose.Slides
linktitle: Riempimento di forme con gradiente nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le diapositive della tua presentazione con sfumature accattivanti utilizzando Aspose.Slides per .NET. Segui questa guida passo passo con il codice sorgente completo per riempire le forme con sfumature, da lineari a radiali, aggiungendo profondità e dimensione.
type: docs
weight: 21
url: /it/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

## Introduzione ad Aspose.Slides per .NET

Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint a livello di codice. Offre un'ampia gamma di funzionalità per lavorare con diapositive, forme, testo, immagini e altro ancora. In questa guida, ci concentreremo su come utilizzare Aspose.Slides per applicare sfumature alle forme all'interno di una presentazione.

## Aggiunta di forme alle diapositive

Prima di approfondire i gradienti, iniziamo aggiungendo forme alle diapositive utilizzando Aspose.Slides. Ecco un esempio base di aggiunta di una forma rettangolare a una diapositiva:

```csharp
// Aggiungi una nuova forma rettangolare alla diapositiva
var slide = presentation.Slides[0];
var rectangle = slide.Shapes.AddRectangle(100, 100, 200, 150);
```

## Comprendere i gradienti

Le sfumature sono fusioni graduali di due o più colori che creano una transizione graduale tra loro. Possono essere lineari o radiali e aggiungono profondità e dimensione alle forme.

## Riempimento di forme con gradienti lineari

 Per riempire una forma con un gradiente lineare utilizzando Aspose.Slides, è necessario creare un file`LinearGradientFill` oggetto e applicarlo alla forma. Ecco un esempio:

```csharp
// Crea un riempimento sfumato lineare
var gradientFill = new LinearGradientFill();
gradientFill.Angle = 45; // Imposta l'angolo del gradiente

// Aggiungi interruzioni di gradiente
gradientFill.GradientStops.Add(0, Color.Blue);
gradientFill.GradientStops.Add(1, Color.White);

// Applica il riempimento sfumato alla forma
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
rectangle.FillFormat.GradientFormat.LinearGradientFormat = gradientFill;
```

## Applicazione di gradienti radiali alle forme

Le sfumature radiali creano una miscela circolare di colori, che si irradia da un punto centrale. Ecco come è possibile applicare un riempimento sfumato radiale utilizzando Aspose.Slides:

```csharp
// Crea un riempimento sfumato radiale
var gradientFill = new RadialGradientFill();

// Aggiungi interruzioni di gradiente
gradientFill.GradientStops.Add(0, Color.Green);
gradientFill.GradientStops.Add(1, Color.Yellow);

// Applica il riempimento sfumato alla forma
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Radial;
rectangle.FillFormat.GradientFormat.RadialGradientFormat = gradientFill;
```

## Combinazione di gradienti con trasparenza

È possibile migliorare l'impatto visivo delle sfumature applicando la trasparenza alla forma. Ciò crea un'elegante miscela di colori e consente allo sfondo di trasparire leggermente.

```csharp
// Applicare la trasparenza alla forma
rectangle.FillFormat.Transparency = 0.5; //Regola il livello di trasparenza
```

## Lavorare con più interruzioni di gradiente

Le interruzioni della sfumatura definiscono i colori e le posizioni all'interno di una sfumatura. Aggiungendo più interruzioni di gradiente, puoi creare gradienti più complessi e visivamente accattivanti.

```csharp
// Aggiungi più interruzioni di gradiente
gradientFill.GradientStops.Add(0, Color.Red);
gradientFill.GradientStops.Add(0.5, Color.Yellow);
gradientFill.GradientStops.Add(1, Color.Blue);
```

## Aggiunta del codice sorgente al tuo progetto

 Per utilizzare Aspose.Slides per .NET, devi aggiungere la libreria al tuo progetto. È possibile scaricare la libreria dal sito:[Scarica Aspose.Slides per .NET](https://releases.aspose.com/slides/net/).

## Compilazione ed esecuzione del progetto

Dopo aver aggiunto la libreria Aspose.Slides al tuo progetto, puoi iniziare a scrivere codice per creare e manipolare le diapositive della presentazione. Assicurati di includere gli spazi dei nomi necessari:

```csharp
using Aspose.Slides;
using Aspose.Slides.Fill;
```

## Personalizzazioni ed effetti aggiuntivi

 Aspose.Slides offre varie opzioni di personalizzazione ed effetti che puoi applicare a forme e sfumature. Esplora la documentazione per funzionalità più avanzate:[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).

## Esportazione della presentazione

Dopo aver applicato gradienti e personalizzazioni alla tua presentazione, puoi salvarla in vari formati, come PPTX o PDF:

```csharp
// Salva la presentazione in un file
presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione

Riempire le forme con sfumature può aumentare l'attrattiva visiva delle diapositive della presentazione, rendendole più coinvolgenti e visivamente impressionanti. Aspose.Slides per .NET fornisce gli strumenti necessari per applicare facilmente le sfumature, consentendoti di creare presentazioni straordinarie che affascinano il tuo pubblico.

## Domande frequenti

### Come posso scaricare Aspose.Slides per .NET?

 È possibile scaricare la libreria Aspose.Slides per .NET dalla pagina delle versioni:[Scarica Aspose.Slides per .NET](https://releases.aspose.com/slides/net/).

### Posso applicare la trasparenza alle forme con riempimento sfumato?

 Sì, puoi applicare la trasparenza alle forme riempite con sfumature utilizzando`Transparency` proprietà del`FillFormat`.

### I gradienti radiali sono migliori dei gradienti lineari?

La scelta tra gradienti radiali e lineari dipende dal design e dall'effetto che si desidera ottenere. I gradienti radiali creano una fusione circolare, mentre i gradienti lineari creano una transizione lineare uniforme tra i colori.

### Posso personalizzare la posizione delle interruzioni del gradiente?

Sì, puoi personalizzare la posizione e il colore delle interruzioni del gradiente all'interno di un riempimento gradiente. Ciò ti consente di creare effetti sfumati unici e complessi.

### Aspose.Slides è adatto per altre manipolazioni di PowerPoint?

Sì, Aspose.Slides offre un'ampia gamma di funzionalità per lavorare con presentazioni PowerPoint, inclusa l'aggiunta di diapositive, testo, immagini, animazioni e altro ancora.