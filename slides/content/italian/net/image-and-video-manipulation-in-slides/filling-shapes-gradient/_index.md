---
title: Crea sfumature straordinarie in PowerPoint con Aspose.Slides
linktitle: Riempimento di forme con gradiente nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Migliora le tue presentazioni con Aspose.Slides per .NET! Impara il processo passo passo per riempire le forme con le sfumature. Scarica la prova gratis adesso!
type: docs
weight: 21
url: /it/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## introduzione
Creare diapositive di presentazione visivamente accattivanti è essenziale per catturare e mantenere l'attenzione del pubblico. In questo tutorial ti guideremo attraverso il processo di miglioramento delle tue diapositive riempiendo una forma ellittica con una sfumatura utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato sul tuo computer.
-  Aspose.Slides per la libreria .NET. Scaricalo[Qui](https://releases.aspose.com/slides/net/).
- Una directory di progetto per organizzare i tuoi file.
## Importa spazi dei nomi
Nel tuo progetto C#, includi gli spazi dei nomi richiesti per Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Passaggio 1: crea una presentazione
Inizia creando una nuova presentazione utilizzando la libreria Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Il tuo codice va qui...
}
```
## Passaggio 2: aggiungi una forma ellittica
Inserisci una forma ellittica nella prima diapositiva della presentazione:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Passaggio 3: applica la formattazione del gradiente
Specificare che la forma deve essere riempita con un gradiente e definire le caratteristiche del gradiente:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Passaggio 4: aggiungi interruzioni di gradiente
Definisci i colori e le posizioni delle interruzioni del gradiente:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Passaggio 5: salva la presentazione
Salva la tua presentazione con la forma con gradiente appena aggiunta:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Ripeti questi passaggi nel codice C#, assicurandoti che la sequenza e i valori dei parametri siano corretti. Ciò si tradurrà in un file di presentazione con una forma ellittica visivamente accattivante riempita con una sfumatura.
## Conclusione
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## Domande frequenti
### D: Posso applicare sfumature a forme diverse dalle ellissi?
R: Certamente! Aspose.Slides per .NET supporta il riempimento sfumato per varie forme come rettangoli, poligoni e altro.
### D: Dove posso trovare ulteriori esempi e documentazione dettagliata?
 R: Esplora il[Aspose.Slides per la documentazione .NET](https://reference.aspose.com/slides/net/) per guide ed esempi completi.
### D: È disponibile una prova gratuita per Aspose.Slides per .NET?
 R: Sì, puoi accedere a una prova gratuita[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Slides per .NET?
 R: Cerca assistenza e interagisci con la comunità sul[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### D: Posso acquistare una licenza temporanea per Aspose.Slides per .NET?
 R: Certamente puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).