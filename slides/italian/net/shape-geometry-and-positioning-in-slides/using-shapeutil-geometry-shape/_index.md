---
title: Padroneggiare le forme geometriche con ShapeUtil - Aspose.Slides .NET
linktitle: Utilizzo di ShapeUtil per la forma geometrica nelle diapositive della presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Esplora la potenza di Aspose.Slides per .NET con ShapeUtil per forme geometriche dinamiche. Crea presentazioni accattivanti senza sforzo. Scarica ora! Scopri come migliorare le presentazioni di PowerPoint con Aspose.Slides. Esplora ShapeUtil per la manipolazione delle forme geometriche. Guida passo passo con il codice sorgente .NET. Ottimizza le presentazioni in modo efficace.
weight: 17
url: /it/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare le forme geometriche con ShapeUtil - Aspose.Slides .NET

## introduzione
Creare diapositive di presentazione visivamente accattivanti e dinamiche è un'abilità essenziale e Aspose.Slides per .NET fornisce un potente toolkit per raggiungere questo obiettivo. In questo tutorial esploreremo l'uso di ShapeUtil per gestire le forme geometriche nelle diapositive di presentazione. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato con Aspose.Slides, questa guida ti guiderà attraverso il processo di utilizzo di ShapeUtil per migliorare le tue presentazioni.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza di base della programmazione C# e .NET.
-  Aspose.Slides installato per la libreria .NET. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).
- Un ambiente di sviluppo configurato per eseguire applicazioni .NET.
## Importa spazi dei nomi
Nel codice C#, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Slides. Aggiungi quanto segue all'inizio dello script:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
Ora suddividiamo l'esempio fornito in più passaggi per creare una guida passo passo per l'utilizzo di ShapeUtil per le forme geometriche nelle diapositive della presentazione.
## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assicurati di sostituire "La tua directory dei documenti" con il percorso effettivo in cui desideri salvare la presentazione.
## Passaggio 2: definire il nome del file di output
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
Specificare il nome del file di output desiderato, inclusa l'estensione del file.
## Passaggio 3: crea una presentazione
```csharp
using (Presentation pres = new Presentation())
```
Inizializza un nuovo oggetto di presentazione utilizzando la libreria Aspose.Slides.
## Passaggio 4: aggiungi una forma geometrica
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
Aggiungi una forma rettangolare alla prima diapositiva della presentazione.
## Passaggio 5: ottieni il percorso geometrico originale
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
Recupera il percorso geometrico della forma e imposta la modalità di riempimento.
## Passaggio 6: crea un percorso grafico con testo
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
Genera un percorso grafico con il testo da aggiungere alla forma.
## Passaggio 7: converti il percorso grafico in percorso geometrico
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
Utilizza ShapeUtil per convertire il percorso grafico in un percorso geometrico e impostare la modalità di riempimento.
## Passaggio 8: imposta i percorsi geometrici combinati sulla forma
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
Combina il nuovo percorso geometrico con il percorso originale e impostalo sulla forma.
## Passaggio 9: salva la presentazione
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Salva la presentazione modificata con la nuova forma geometrica.
## Conclusione
Congratulazioni! Hai esplorato con successo l'uso di ShapeUtil per gestire le forme geometriche nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Questa potente funzionalità ti consente di creare facilmente presentazioni dinamiche e coinvolgenti.
## Domande frequenti
### Posso utilizzare Aspose.Slides per .NET con altri linguaggi di programmazione?
Aspose.Slides supporta principalmente i linguaggi .NET. Tuttavia, Aspose fornisce librerie simili per altre piattaforme e linguaggi.
### Dove posso trovare la documentazione dettagliata per Aspose.Slides per .NET?
 La documentazione è disponibile[Qui](https://reference.aspose.com/slides/net/).
### È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi trovare la prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per .NET?
 Visita il forum di supporto della comunità[Qui](https://forum.aspose.com/c/slides/11).
### Posso acquistare una licenza temporanea per Aspose.Slides per .NET?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
