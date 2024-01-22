---
title: Migliora le presentazioni formatta forme rettangolari con Aspose.Slides
linktitle: Formattazione della forma rettangolare nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Impara a formattare forme rettangolari nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Migliora le tue diapositive con elementi visivi dinamici.
type: docs
weight: 12
url: /it/net/shape-geometry-and-positioning-in-slides/formatting-rectangle-shape/
---
## introduzione
Aspose.Slides per .NET è una potente libreria che facilita il lavoro con le presentazioni PowerPoint nell'ambiente .NET. Se desideri migliorare le tue presentazioni formattando dinamicamente le forme rettangolari, questo tutorial fa per te. In questa guida passo passo, ti guideremo attraverso il processo di formattazione di una forma rettangolare in una presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Un ambiente di sviluppo con Aspose.Slides per .NET installato.
- Conoscenza base del linguaggio di programmazione C#.
- Familiarità con la creazione e la manipolazione di presentazioni PowerPoint.
Ora iniziamo con il tutorial!
## Importa spazi dei nomi
Nel codice C#, devi importare gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Slides. Aggiungi i seguenti spazi dei nomi all'inizio del codice:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
```
## Passaggio 1: configura la directory dei documenti
 Inizia impostando la directory in cui desideri salvare il file di presentazione di PowerPoint. Sostituire`"Your Document Directory"` con il percorso effettivo della directory.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Passaggio 2: crea un oggetto di presentazione
 Istanziare il`Presentation`classe per rappresentare il file PPTX. Questa sarà la base per la tua presentazione PowerPoint.
```csharp
using (Presentation pres = new Presentation())
{
    // Il tuo codice va qui
}
```
## Passaggio 3: ottieni la prima diapositiva
Accedi alla prima diapositiva della presentazione, poiché sarà la tela in cui aggiungi e formatti la forma del rettangolo.
```csharp
ISlide sld = pres.Slides[0];
```
## Passaggio 4: aggiungi una forma rettangolare
 Usa il`Shapes` proprietà della diapositiva per aggiungere una forma automatica di tipo rettangolo. Specificare la posizione e le dimensioni del rettangolo.
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
## Passaggio 5: applica la formattazione alla forma rettangolare
Ora applichiamo un po' di formattazione alla forma del rettangolo. Imposta il colore di riempimento, il colore della linea e la larghezza della forma per personalizzarne l'aspetto.
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
## Passaggio 6: salva la presentazione
 Scrivi la presentazione modificata su disco utilizzando il file`Save` metodo, specificando il formato file come PPTX.
```csharp
pres.Save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Congratulazioni! Hai formattato con successo una forma rettangolare in una presentazione utilizzando Aspose.Slides per .NET.
## Conclusione
In questo tutorial, abbiamo trattato le basi per lavorare con forme rettangolari in Aspose.Slides per .NET. Hai imparato come impostare il tuo progetto, creare una presentazione, aggiungere una forma rettangolare e applicare la formattazione per migliorarne l'impatto visivo. Mentre continui a esplorare Aspose.Slides, scoprirai ancora più modi per migliorare le tue presentazioni PowerPoint.
## Domande frequenti
### Q1: posso utilizzare Aspose.Slides per .NET con altri linguaggi .NET?
Sì, Aspose.Slides supporta altri linguaggi .NET come VB.NET e F# oltre a C#.
### Q2: Dove posso trovare la documentazione per Aspose.Slides?
 Puoi fare riferimento alla documentazione[Qui](https://reference.aspose.com/slides/net/).
### Q3: Come posso ottenere supporto per Aspose.Slides?
 Per supporto e discussioni, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Q4: È disponibile una prova gratuita?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### Q5: Dove posso acquistare Aspose.Slides per .NET?
 È possibile acquistare Aspose.Slides per .NET[Qui](https://purchase.aspose.com/buy).