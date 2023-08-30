---
title: Applicazione dell'effetto rotazione 3D sulle forme nelle diapositive della presentazione con Aspose.Slides
linktitle: Applicazione dell'effetto rotazione 3D sulle forme nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come applicare accattivanti effetti di rotazione 3D alle diapositive di presentazione utilizzando Aspose.Slides per .NET. Guida passo passo con codice sorgente per un impatto visivo straordinario.
type: docs
weight: 23
url: /it/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

Immagina di dare alla tua presentazione un impatto visivo straordinario aggiungendo effetti dinamici di rotazione 3D alle forme. Con Aspose.Slides per .NET, puoi facilmente ottenere questo effetto accattivante e far risaltare le tue diapositive. In questo tutorial ti guideremo passo dopo passo attraverso il processo di applicazione degli effetti di rotazione 3D alle forme nelle diapositive della presentazione. Ti forniremo il codice sorgente e spiegheremo ogni passaggio in dettaglio. Immergiamoci!

## Introduzione agli effetti di rotazione 3D

Gli effetti di rotazione 3D aggiungono profondità e realismo alle diapositive della tua presentazione. Ti consentono di far apparire le forme come se ruotassero nello spazio tridimensionale, creando un'esperienza visiva coinvolgente per il tuo pubblico.

## Configurazione dell'ambiente di sviluppo

 Prima di iniziare, assicurati di avere Aspose.Slides per .NET installato nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Creazione di una presentazione

Per iniziare, creiamo una nuova presentazione:

```csharp
// Inizializzare una presentazione
Presentation presentation = new Presentation();
```

## Aggiunta di forme alle diapositive

Ora aggiungiamo alcune forme alle nostre diapositive:

```csharp
// Accedi alla prima diapositiva
ISlide slide = presentation.Slides[0];

// Aggiungi una forma rettangolare
IShape shape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```

## Applicazione dell'effetto rotazione 3D

Per applicare un effetto di rotazione 3D alla forma, utilizzare il seguente codice:

```csharp
// Applica l'effetto di rotazione 3D alla forma
shape.ThreeDFormat.RotationX = 30;
shape.ThreeDFormat.RotationY = 45;
```

## Regolazione dell'angolo di rotazione e della prospettiva

È possibile regolare l'angolo di rotazione e la prospettiva per ottenere l'effetto desiderato:

```csharp
// Regola l'angolo di rotazione e la prospettiva
shape.ThreeDFormat.RotationX = 60;
shape.ThreeDFormat.RotationY = 30;
shape.ThreeDFormat.PresetCamera.PresetType = CameraPresetType.OrthographicFront;
```

## Regolazione fine delle impostazioni di rotazione

Per un controllo più preciso, puoi ottimizzare le impostazioni di rotazione:

```csharp
// Perfezionare le impostazioni di rotazione
shape.ThreeDFormat.RotationX = 45;
shape.ThreeDFormat.RotationY = 15;
shape.ThreeDFormat.RotationZ = 10;
```

## Aggiunta di animazione (facoltativo)

Per aggiungere animazione all'effetto di rotazione:

```csharp
// Aggiungi animazione all'effetto di rotazione
ITransition transition = slide.SlideShowTransition;
transition.AdvanceOnTime = true;
transition.AdvanceTime = 2; // secondi
```

## Salvare ed esportare la presentazione

Dopo aver applicato l'effetto di rotazione 3D e qualsiasi altra regolazione desiderata, salva ed esporta la presentazione:

```csharp
// Salva ed esporta la presentazione
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Conclusione

Congratulazioni! Hai imparato con successo come applicare gli effetti di rotazione 3D alle forme nelle diapositive della presentazione utilizzando Aspose.Slides per .NET. Questa tecnica può migliorare notevolmente l'attrattiva visiva delle tue presentazioni e coinvolgere il tuo pubblico.

## Domande frequenti

### Come posso regolare la velocità di rotazione dell'animazione?

 È possibile regolare la velocità di rotazione modificando il`AdvanceTime` proprietà nelle impostazioni di transizione.

### Posso applicare la rotazione 3D alle caselle di testo?

Sì, puoi applicare effetti di rotazione 3D alle caselle di testo o a qualsiasi altra forma nella presentazione.

### Aspose.Slides è compatibile con diverse versioni di PowerPoint?

Sì, Aspose.Slides è compatibile con varie versioni di PowerPoint e ti consente di creare presentazioni che possono essere aperte e visualizzate da diversi software PowerPoint.

### Posso applicare più effetti 3D a una singola forma?

Sì, puoi combinare più effetti 3D, come rotazione, profondità e illuminazione, per creare effetti visivi complessi per le tue forme.

### Aspose.Slides fornisce supporto per altri tipi di animazioni?

Sì, Aspose.Slides offre una vasta gamma di effetti di animazione che puoi applicare alle diapositive della tua presentazione per renderle più dinamiche e coinvolgenti.