---
"description": "Migliora le tue slide di presentazione con Aspose.Slides per .NET! Impara ad applicare accattivanti effetti smussati con questa guida passo passo."
"linktitle": "Applicazione di effetti smussati alle forme nelle diapositive di una presentazione utilizzando Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Padroneggiare gli effetti smussati in Aspose.Slides - Tutorial passo passo"
"url": "/it/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare gli effetti smussati in Aspose.Slides - Tutorial passo passo

## Introduzione
Nel dinamico mondo delle presentazioni, aggiungere un tocco visivo alle diapositive può migliorare significativamente l'impatto del messaggio. Aspose.Slides per .NET offre un potente toolkit per manipolare e abbellire le diapositive delle presentazioni tramite codice. Una di queste interessanti funzionalità è la possibilità di applicare effetti di smusso alle forme, aggiungendo profondità e dimensione agli elementi visivi.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides. Puoi scaricarla da [sito web](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo .NET e acquisisci una conoscenza di base di C#.
- Directory dei documenti: crea una directory per i tuoi documenti in cui verranno salvati i file della presentazione generati.
## Importa spazi dei nomi
Nel codice C# includi gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assicurarsi che la directory del documento esista, creandola se non è già presente.
## Passaggio 2: creare un'istanza di presentazione
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
Inizializza un'istanza di presentazione e aggiungi una diapositiva con cui lavorare.
## Passaggio 3: aggiungere una forma alla diapositiva
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
Crea una forma automatica (un'ellisse in questo esempio) e personalizzane le proprietà di riempimento e linea.
## Passaggio 4: impostare le proprietà ThreeDFormat
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
Specificare le proprietà tridimensionali, tra cui tipo di smussatura, altezza, larghezza, tipo di telecamera, tipo di luce e direzione.
## Passaggio 5: Salva la presentazione
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
Salvare la presentazione con gli effetti smussati applicati in un file PPTX.
## Conclusione
Congratulazioni! Hai applicato con successo effetti di smusso a una forma nella tua presentazione utilizzando Aspose.Slides per .NET. Sperimenta diversi parametri per sfruttare appieno il potenziale dei miglioramenti visivi nelle tue diapositive.
## Domande frequenti
### 1. Posso applicare effetti smussati ad altre forme?
Sì, è possibile applicare effetti smussati a varie forme modificando di conseguenza il tipo e le proprietà della forma.
### 2. Come posso cambiare il colore della smussatura?
Modificare il `SolidFillColor.Color` proprietà all'interno del `BevelTop` proprietà per cambiare il colore della smussatura.
### 3. Aspose.Slides è compatibile con l'ultimo framework .NET?
Sì, Aspose.Slides viene aggiornato regolarmente per garantire la compatibilità con i framework .NET più recenti.
### 4. Posso applicare più effetti smussatura a una singola forma?
Anche se non è una pratica comune, è possibile sperimentare l'impilatura di più forme o la manipolazione delle proprietà della smussatura per ottenere un effetto simile.
### 5. Ci sono altri effetti 3D disponibili in Aspose.Slides?
Assolutamente sì! Aspose.Slides offre una varietà di effetti 3D per aggiungere profondità e realismo agli elementi della tua presentazione.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}