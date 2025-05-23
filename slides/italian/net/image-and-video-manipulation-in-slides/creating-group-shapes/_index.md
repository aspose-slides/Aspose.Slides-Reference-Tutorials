---
"description": "Scopri come creare forme di gruppo in PowerPoint con Aspose.Slides per .NET. Segui la nostra guida passo passo per presentazioni visivamente accattivanti."
"linktitle": "Creazione di forme di gruppo nelle diapositive di una presentazione con Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Creazione di forme di gruppo in .NET"
"url": "/it/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Creazione di forme di gruppo in .NET

## Introduzione
Se desideri migliorare l'aspetto visivo delle diapositive della tua presentazione e organizzare i contenuti in modo più efficiente, integrare le forme di gruppo è una soluzione efficace. Aspose.Slides per .NET offre un modo semplice per creare e manipolare forme di gruppo nelle tue presentazioni PowerPoint. In questo tutorial, illustreremo il processo di creazione di forme di gruppo utilizzando Aspose.Slides, suddividendolo in semplici passaggi.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides. Puoi scaricarla da [sito web](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configurare un ambiente di lavoro con un IDE compatibile con .NET, come Visual Studio.
- Conoscenza di base di C#: familiarizzare con le basi del linguaggio di programmazione C#.
## Importa spazi dei nomi
Nel tuo progetto C#, inizia importando gli spazi dei nomi necessari:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: creare un'istanza della classe di presentazione

Crea un'istanza di `Presentation` classe e specifica la directory in cui sono archiviati i tuoi documenti:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continuare con i seguenti passaggi all'interno di questo blocco di utilizzo
}
```

## Passaggio 2: accedi alla prima diapositiva

Recupera la prima diapositiva dalla presentazione:

```csharp
ISlide sld = pres.Slides[0];
```

## Passaggio 3: accesso alla raccolta di forme

Accedi alla raccolta di forme nella diapositiva:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Passaggio 4: aggiunta di una forma di gruppo

Aggiungere una forma di gruppo alla diapositiva:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Passaggio 5: aggiunta di forme all'interno della forma del gruppo

Popolare la forma del gruppo con forme individuali:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Passaggio 6: aggiunta della cornice di forma del gruppo

Definisci la cornice per l'intera forma del gruppo:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Passaggio 7: Salva la presentazione

Salva la presentazione modificata nella directory specificata:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Ripeti questi passaggi nella tua applicazione C# per creare correttamente forme di gruppo nelle diapositive della presentazione utilizzando Aspose.Slides.

## Conclusione
In questo tutorial abbiamo esplorato il processo di creazione di forme di gruppo con Aspose.Slides per .NET. Seguendo questi passaggi, puoi migliorare l'aspetto visivo e l'organizzazione delle tue presentazioni PowerPoint.
## Domande frequenti
### Aspose.Slides è compatibile con l'ultima versione di .NET?
Sì, Aspose.Slides viene aggiornato regolarmente per supportare le ultime versioni di .NET. Controlla il [documentazione](https://reference.aspose.com/slides/net/) per dettagli sulla compatibilità.
### Posso provare Aspose.Slides prima di acquistarlo?
Assolutamente! Puoi scaricare una versione di prova gratuita. [Qui](https://releases.aspose.com/).
### Dove posso trovare supporto per le query relative ad Aspose.Slides?
Visita Aspose.Slides [foro](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
Puoi ottenere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso acquistare una licenza completa per Aspose.Slides?
Puoi acquistare una licenza da [pagina di acquisto](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}