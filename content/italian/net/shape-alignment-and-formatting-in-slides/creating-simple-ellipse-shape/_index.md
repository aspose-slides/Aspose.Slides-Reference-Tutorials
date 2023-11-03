---
title: Creazione di una forma ellittica semplice nelle diapositive di presentazione con Aspose.Slides
linktitle: Creazione di una forma ellittica semplice nelle diapositive di presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare una semplice forma ellittica nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Questa guida passo passo fornisce il codice sorgente e le istruzioni per aggiungere, personalizzare e salvare forme ellittiche.
type: docs
weight: 11
url: /it/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Introduzione alla creazione di una forma ellittica semplice nelle diapositive di presentazione

Se stai cercando di migliorare le diapositive della tua presentazione aggiungendo forme visivamente accattivanti, Aspose.Slides per .NET fornisce una potente soluzione per raggiungere questo obiettivo. In questa guida passo passo, ti guideremo attraverso il processo di creazione di una semplice forma ellittica nelle diapositive della presentazione utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio o qualsiasi altro ambiente di sviluppo .NET installato.
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Impostazione del tuo progetto

1. Crea un nuovo progetto di Visual Studio o aprine uno esistente.
2. Aggiungi un riferimento alla libreria Aspose.Slides per .NET nel tuo progetto.

## Creazione di una presentazione

Per iniziare, creiamo una nuova presentazione in cui aggiungeremo la nostra forma ellittica.

```csharp
using Aspose.Slides;

// Crea una nuova presentazione
Presentation presentation = new Presentation();
```

## Aggiunta di una forma ellittica

Ora che la presentazione è pronta, aggiungiamo una forma ellittica a una diapositiva.

```csharp
// Accedi alla prima diapositiva della presentazione
ISlide slide = presentation.Slides[0];

// Definire le dimensioni e la posizione dell'ellisse
float x = 100;   // Coordinata X
float y = 100;   // Coordinata Y
float width = 200;  // Larghezza
float height = 100; // Altezza

// Aggiungi la forma dell'ellisse alla diapositiva
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Personalizzazione dell'ellisse

È possibile personalizzare l'aspetto della forma dell'ellisse utilizzando varie proprietà.

```csharp
// Imposta il colore di riempimento dell'ellisse
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

//Imposta il colore e la larghezza del contorno
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Aggiungi una cornice di testo all'ellisse
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Salvataggio della presentazione

Dopo aver aggiunto e personalizzato la forma dell'ellisse, è ora di salvare la presentazione.

```csharp
// Salva la presentazione
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Conclusione

Congratulazioni! Hai creato con successo una semplice forma ellittica nelle diapositive della presentazione utilizzando Aspose.Slides per .NET. Questa guida ha trattato il processo di impostazione del progetto, creazione di una presentazione, aggiunta di una forma ellittica, personalizzazione dell'aspetto e salvataggio della presentazione finale.

## Domande frequenti

### Come posso modificare la posizione della forma dell'ellisse?

 È possibile modificare il`x` E`y` coordinate quando si aggiunge la forma dell'ellisse per regolarne la posizione sulla diapositiva.

### Posso cambiare il colore del contorno dell'ellisse?

 Sì, puoi impostare il colore del contorno utilizzando`LineFormat.FillFormat.SolidFillColor.Color` proprietà.

### È possibile aggiungere testo all'interno dell'ellisse?

 Assolutamente! Puoi aggiungere testo alla forma dell'ellisse utilizzando`TextFrame.Text` proprietà.

### Quali altre forme posso creare utilizzando Aspose.Slides per .NET?

Aspose.Slides per .NET supporta varie forme, inclusi rettangoli, linee, frecce e altro.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per .NET?

Per documentazione dettagliata ed esempi, fare riferimento a[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/).