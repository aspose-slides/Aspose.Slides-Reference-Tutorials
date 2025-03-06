---
title: Creazione di geometria personalizzata in C# con Aspose.Slides per .NET
linktitle: Creazione di geometria personalizzata in forma geometrica utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Impara a creare geometrie personalizzate in Aspose.Slides per .NET. Migliora le tue presentazioni con forme uniche. Guida dettagliata per gli sviluppatori C#.
weight: 15
url: /it/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creazione di geometria personalizzata in C# con Aspose.Slides per .NET

## introduzione
Nel dinamico mondo delle presentazioni, l'aggiunta di forme e geometrie uniche può elevare i tuoi contenuti, rendendoli più coinvolgenti e visivamente accattivanti. Aspose.Slides per .NET fornisce una potente soluzione per creare geometrie personalizzate all'interno di forme, consentendoti di liberarti dai progetti convenzionali. Questo tutorial ti guiderà attraverso il processo di creazione di geometria personalizzata in GeometryShape utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza di base del linguaggio di programmazione C#.
- Aspose.Slides per la libreria .NET installata nel tuo ambiente di sviluppo.
- Configurazione di Visual Studio o di qualsiasi ambiente di sviluppo C# preferito.
## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nel tuo progetto C#:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto C# nel tuo ambiente di sviluppo preferito. Assicurarsi che Aspose.Slides per .NET sia installato correttamente.
## Passaggio 2: definire la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Passaggio 3: impostare il raggio della stella esterna e interna
```csharp
float R = 100, r = 50; // Raggio della stella esterna ed interna
```
## Passaggio 4: crea il percorso della geometria stellare
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Passaggio 5: crea una presentazione
```csharp
using (Presentation pres = new Presentation())
{
    // Crea una nuova forma
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Imposta il nuovo percorso geometrico sulla forma
    shape.SetGeometryPath(starPath);
    // Salva la presentazione
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Passaggio 6: definire il metodo CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Conclusione
Congratulazioni! Hai imparato con successo come creare geometria personalizzata in GeometryShape utilizzando Aspose.Slides per .NET. Questo apre un mondo di possibilità per creare presentazioni uniche e visivamente sorprendenti.
## Domande frequenti
### 1. Posso utilizzare Aspose.Slides per .NET con altri linguaggi di programmazione?
Sì, Aspose.Slides supporta vari linguaggi di programmazione, ma questo tutorial si concentra su C#.
### 2. Dove posso trovare la documentazione per Aspose.Slides per .NET?
 Visitare il[documentazione](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
### 3. È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi esplorare a[prova gratuita](https://releases.aspose.com/) per sperimentare le funzionalità.
### 4. Come posso ottenere supporto per Aspose.Slides per .NET?
 Cerca assistenza e interagisci con la comunità presso il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Dove posso acquistare Aspose.Slides per .NET?
 È possibile acquistare Aspose.Slides per .NET[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
