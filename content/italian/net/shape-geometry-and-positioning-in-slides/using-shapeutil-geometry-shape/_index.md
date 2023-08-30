---
title: Utilizzo di ShapeUtil per la forma geometrica nelle diapositive della presentazione
linktitle: Utilizzo di ShapeUtil per la forma geometrica nelle diapositive della presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come migliorare le presentazioni di PowerPoint con Aspose.Slides. Esplora ShapeUtil per la manipolazione delle forme geometriche. Guida passo passo con il codice sorgente .NET. Ottimizza le presentazioni in modo efficace.
type: docs
weight: 17
url: /it/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
Quando si tratta di creare presentazioni visivamente accattivanti e informative, Aspose.Slides è un potente strumento che offre agli sviluppatori la capacità di manipolare vari aspetti delle presentazioni a livello di codice. Un aspetto essenziale delle presentazioni è l'uso delle forme, che svolgono un ruolo cruciale nel trasmettere le informazioni in modo efficace. In questo tutorial, approfondiremo l'utilizzo di ShapeUtil per la gestione delle forme geometriche nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Al termine di questa guida avrai acquisito una solida conoscenza di come lavorare con le forme geometriche e migliorare facilmente le tue presentazioni.

## Introduzione ad Aspose.Slides e ShapeUtil

Aspose.Slides è una potente libreria .NET che consente agli sviluppatori di creare, modificare e manipolare presentazioni PowerPoint a livello di codice. ShapeUtil fa parte della libreria Aspose.Slides che fornisce una serie di utilità per lavorare in modo specifico con le forme all'interno delle presentazioni.

## Impostazione dell'ambiente di sviluppo

Prima di iniziare, assicurati di avere la libreria Aspose.Slides installata nel tuo progetto .NET. Puoi usare NuGet per aggiungere facilmente la libreria al tuo progetto.

```csharp
// Installa Aspose.Slides tramite NuGet
Install-Package Aspose.Slides
```

## Creazione di una nuova presentazione

Iniziamo creando una nuova presentazione e aggiungendovi diapositive.

```csharp
// Crea una nuova presentazione
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

## Aggiunta di forme geometriche alle diapositive

Per aggiungere forme geometriche alle diapositive, puoi utilizzare la classe ShapeUtil.

```csharp
// Aggiungi una forma rettangolare alla diapositiva
IShape rectangle = ShapeUtil.AddRectangle(slide, 100, 100, 200, 150);
```

## Modifica delle proprietà delle forme geometriche

È possibile modificare varie proprietà delle forme geometriche, come posizione, dimensione e rotazione.

```csharp
// Modificare la posizione del rettangolo
rectangle.X = 300;
rectangle.Y = 200;

// Ridimensiona il rettangolo
rectangle.Width = 250;
rectangle.Height = 100;

// Ruota il rettangolo
rectangle.Rotation = 45;
```

## Disposizione e allineamento delle forme geometriche

ShapeUtil fornisce anche metodi per disporre e allineare le forme sulle diapositive.

```csharp
// Disporre le forme orizzontalmente
ShapeUtil.ArrangeHorizontally(slide.Shapes);

// Allinea le forme al centro
ShapeUtil.AlignToCenter(slide.Shapes);
```

## Raggruppamento e separazione di forme

Puoi raggruppare più forme insieme utilizzando ShapeUtil.

```csharp
// Forme di gruppo
IShape[] shapesToGroup = new IShape[] { shape1, shape2, shape3 };
IShape groupedShape = ShapeUtil.GroupShapes(slide, shapesToGroup);

// Separare le forme
ShapeUtil.UngroupShape(slide, groupedShape);
```

## Applicazione della formattazione alle forme geometriche

ShapeUtil ti consente di applicare la formattazione alle forme, inclusi gli stili di riempimento e di linea.

```csharp
// Applica il colore di riempimento
ShapeUtil.ApplyFillColor(shape, Color.Blue);

//Applicare il colore e lo stile della linea
ShapeUtil.ApplyLineColor(shape, Color.Black, LineStyle.Single);
```

## Aggiunta di testo alle forme geometriche

Puoi anche aggiungere testo alle forme geometriche utilizzando ShapeUtil.

```csharp
// Aggiungi testo alla forma
ShapeUtil.AddTextToShape(shape, "Hello, Aspose.Slides!", new Font("Arial", 12), Color.Black);
```

## Lavorare con i collegamenti ipertestuali nelle forme

ShapeUtil consente di aggiungere collegamenti ipertestuali alle forme.

```csharp
// Aggiungi collegamento ipertestuale alla forma
string url = "https://www.esempio.com";
ShapeUtil.AddHyperlinkToShape(shape, url);
```

## Gestione dell'ordine Z delle forme

ShapeUtil fornisce metodi per gestire l'ordine z delle forme.

```csharp
// Porta la forma in primo piano
ShapeUtil.BringToFront(shape);

// Invia la forma al retro
ShapeUtil.SendToBack(shape);
```

## Salvare ed esportare la presentazione

Dopo aver apportato tutte le modifiche necessarie, puoi salvare ed esportare la presentazione.

```csharp
// Salva la presentazione
presentation.Save("Presentation.pptx", SaveFormat.Pptx);
```

## Conclusione

In questo tutorial, abbiamo esplorato le funzionalità di Aspose.Slides e ShapeUtil per lavorare con forme geometriche nelle diapositive di presentazione utilizzando .NET. Abbiamo coperto il processo di creazione di una nuova presentazione, aggiunta di forme geometriche, modifica delle loro proprietà, applicazione della formattazione, aggiunta di testo, gestione dei collegamenti ipertestuali e altro ancora. Sfruttando le funzionalità di Aspose.Slides e ShapeUtil, puoi migliorare l'attrattiva visiva e l'efficacia delle tue presentazioni.

## Domande frequenti

### Come installo Aspose.Slides tramite NuGet?

Per installare Aspose.Slides tramite NuGet, utilizzare il comando seguente nella console di gestione pacchetti NuGet:

```csharp
Install-Package Aspose.Slides
```

### Posso aggiungere collegamenti ipertestuali alle forme utilizzando ShapeUtil?

 Sì, puoi aggiungere collegamenti ipertestuali alle forme utilizzando ShapeUtil. Utilizza il`AddHyperlinkToShape` metodo per associare un collegamento ipertestuale a una forma.

### È possibile raggruppare e separare le forme a livello di codice?

 Assolutamente! È possibile utilizzare i metodi ShapeUtil`GroupShapes` E`UngroupShape` per raggruppare e separare le forme a livello di codice.

### Come posso applicare la formattazione alle forme geometriche?

 Con ShapeUtil puoi applicare la formattazione alle forme geometriche utilizzando metodi come`ApplyFillColor` E`ApplyLineColor` per impostare i colori di riempimento e gli stili di linea.

### Qual è lo scopo dell'ordine Z nelle forme?

 L'ordine Z determina l'ordine di sovrapposizione delle forme su una diapositiva. Puoi utilizzare metodi ShapeUtil come`BringToFront` E`SendToBack` per gestire l'ordine Z delle forme.