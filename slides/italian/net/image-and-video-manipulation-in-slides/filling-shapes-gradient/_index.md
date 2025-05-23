---
"description": "Migliora le tue presentazioni con Aspose.Slides per .NET! Scopri la procedura passo passo per riempire le forme con i gradienti. Scarica subito la tua prova gratuita!"
"linktitle": "Riempimento di forme con gradiente nelle diapositive di una presentazione utilizzando Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Crea sfumature straordinarie in PowerPoint con Aspose.Slides"
"url": "/it/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea sfumature straordinarie in PowerPoint con Aspose.Slides

## Introduzione
Creare slide di presentazione visivamente accattivanti è fondamentale per catturare e mantenere l'attenzione del pubblico. In questo tutorial, ti guideremo attraverso il processo di miglioramento delle tue slide riempiendo un'ellisse con un gradiente utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza di base del linguaggio di programmazione C#.
- Visual Studio installato sul computer.
- Scarica la libreria Aspose.Slides per .NET. [Qui](https://releases.aspose.com/slides/net/).
- Una directory di progetto per organizzare i tuoi file.
## Importa spazi dei nomi
Nel tuo progetto C#, includi gli spazi dei nomi richiesti per Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Passaggio 1: creare una presentazione
Inizia creando una nuova presentazione utilizzando la libreria Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Inserisci qui il tuo codice...
}
```
## Passaggio 2: aggiungere una forma ellittica
Inserisci una forma ellittica nella prima diapositiva della presentazione:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Passaggio 3: applicare la formattazione sfumata
Specificare che la forma deve essere riempita con un gradiente e definire le caratteristiche del gradiente:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Passaggio 4: aggiungere interruzioni di sfumatura
Definisci i colori e le posizioni delle interruzioni del gradiente:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Passaggio 5: Salva la presentazione
Salva la presentazione con la forma sfumata appena aggiunta:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Ripeti questi passaggi nel codice C#, assicurandoti che la sequenza e i valori dei parametri siano corretti. Il risultato sarà un file di presentazione con una forma ellittica visivamente accattivante, riempita con un gradiente.
## Conclusione
Con Aspose.Slides per .NET, puoi migliorare facilmente l'estetica visiva delle tue presentazioni. Seguendo questa guida, hai imparato a riempire le forme con sfumature, conferendo alle tue diapositive un aspetto professionale e accattivante.
---
## Domande frequenti
### D: Posso applicare sfumature a forme diverse dalle ellissi?
R: Certamente! Aspose.Slides per .NET supporta il riempimento sfumato per varie forme come rettangoli, poligoni e altro ancora.
### D: Dove posso trovare ulteriori esempi e documentazione dettagliata?
A: Esplora il [Documentazione di Aspose.Slides per .NET](https://reference.aspose.com/slides/net/) per guide ed esempi completi.
### D: È disponibile una versione di prova gratuita di Aspose.Slides per .NET?
A: Sì, puoi accedere a una prova gratuita [Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Slides per .NET?
A: Cerca assistenza e interagisci con la comunità su [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).
### D: Posso acquistare una licenza temporanea per Aspose.Slides per .NET?
A: Certamente, puoi ottenere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}