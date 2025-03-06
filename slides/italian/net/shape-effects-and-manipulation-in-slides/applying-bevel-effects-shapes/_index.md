---
title: Padroneggiare gli effetti smussati in Aspose.Slides - Tutorial passo dopo passo
linktitle: Applicazione di effetti smussati alle forme nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Migliora le tue diapositive di presentazione con Aspose.Slides per .NET! Impara ad applicare accattivanti effetti smussati in questa guida passo passo.
type: docs
weight: 24
url: /it/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---
## introduzione
Nel dinamico mondo delle presentazioni, aggiungere fascino visivo alle diapositive può migliorare significativamente l'impatto del tuo messaggio. Aspose.Slides per .NET fornisce un potente toolkit per manipolare e abbellire le diapositive della presentazione a livello di codice. Una di queste caratteristiche intriganti è la possibilità di applicare effetti smussati alle forme, aggiungendo profondità e dimensione alle tue immagini.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides installata. Puoi scaricarlo da[sito web](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo .NET e acquisisci una conoscenza di base di C#.
- Directory dei documenti: crea una directory per i tuoi documenti in cui verranno salvati i file di presentazione generati.
## Importa spazi dei nomi
Nel codice C#, includi gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: configura la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assicurarsi che la directory dei documenti esista, creandola se non è già presente.
## Passaggio 2: crea un'istanza di presentazione
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
Inizializza un'istanza di presentazione e aggiungi una diapositiva con cui lavorare.
## Passaggio 3: aggiungi una forma alla diapositiva
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
Crea una forma automatica (ellisse in questo esempio) e personalizza le sue proprietà di riempimento e linea.
## Passaggio 4: imposta le proprietà ThreeDFormat
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
## Passaggio 5: salva la presentazione
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
Salva la presentazione con gli effetti smussati applicati in un file PPTX.
## Conclusione
Congratulazioni! Hai applicato con successo effetti smussati a una forma nella presentazione utilizzando Aspose.Slides per .NET. Sperimenta parametri diversi per liberare tutto il potenziale dei miglioramenti visivi nelle tue diapositive.
## Domande frequenti
### 1. Posso applicare effetti smussati ad altre forme?
Sì, puoi applicare effetti smussati a varie forme regolando di conseguenza il tipo di forma e le proprietà.
### 2. Come posso cambiare il colore della smussatura?
 Modifica il`SolidFillColor.Color` proprietà all'interno del`BevelTop` proprietà per cambiare il colore dello smusso.
### 3. Aspose.Slides è compatibile con l'ultimo framework .NET?
Sì, Aspose.Slides viene regolarmente aggiornato per garantire la compatibilità con gli ultimi framework .NET.
### 4. Posso applicare più effetti smussati a una singola forma?
Sebbene non sia comune, puoi sperimentare impilando più forme o manipolando le proprietà dello smusso per ottenere un effetto simile.
### 5. Ci sono altri effetti 3D disponibili in Aspose.Slides?
Assolutamente! Aspose.Slides offre una varietà di effetti 3D per aggiungere profondità e realismo agli elementi della tua presentazione.