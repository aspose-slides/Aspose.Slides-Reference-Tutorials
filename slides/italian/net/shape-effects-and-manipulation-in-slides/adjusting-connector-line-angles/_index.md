---
title: Regola gli angoli della linea del connettore in PowerPoint con Aspose.Slides
linktitle: Regolazione degli angoli della linea del connettore nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come regolare gli angoli della linea del connettore nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Migliora le tue presentazioni con precisione e facilità.
weight: 28
url: /it/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
La creazione di diapositive di presentazione visivamente accattivanti spesso comporta modifiche precise alle linee di connessione. In questo tutorial, esploreremo come regolare gli angoli della linea del connettore nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Aspose.Slides è una potente libreria che consente agli sviluppatori di lavorare con file PowerPoint a livello di programmazione, fornendo ampie funzionalità per creare, modificare e manipolare presentazioni.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio o qualsiasi altro ambiente di sviluppo C# installato.
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).
- Un file di presentazione PowerPoint con le linee di connessione che desideri modificare.
## Importa spazi dei nomi
Per iniziare, assicurati di includere gli spazi dei nomi necessari nel codice C#:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Passaggio 1: imposta il tuo progetto
Creare un nuovo progetto C# in Visual Studio e installare il pacchetto NuGet Aspose.Slides. Imposta la struttura del progetto con un riferimento alla libreria Aspose.Slides.
## Passaggio 2: carica la presentazione
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 Carica il file di presentazione di PowerPoint nel file`Presentation`oggetto. Sostituisci "La tua directory dei documenti" con il percorso effettivo del tuo file.
## Passaggio 3: accedi alla diapositiva e alle forme
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Accedi alla prima diapositiva della presentazione e inizializza una variabile per rappresentare le forme sulla diapositiva.
## Passaggio 4: scorrere le forme
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Codice per la gestione delle linee dei connettori
}
```
Passa attraverso ogni forma sulla diapositiva per identificare ed elaborare le linee di connessione.
## Passaggio 5: regolare gli angoli della linea del connettore
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Codice per la gestione delle forme
}
else if (shape is Connector)
{
    // Codice per la gestione dei connettori
}
Console.WriteLine(dir);
```
 Identificare se la forma è una forma automatica o un connettore e regolare gli angoli della linea del connettore utilizzando l'oggetto fornito`getDirection` metodo.
##  Passaggio 6: definire il`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Codice per il calcolo della direzione
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 Implementare il`getDirection` metodo per calcolare l'angolo della linea del connettore in base alle sue dimensioni e al suo orientamento.
## Conclusione
Con questi passaggi, puoi regolare a livello di codice gli angoli della linea del connettore nella presentazione di PowerPoint utilizzando Aspose.Slides per .NET. Questo tutorial fornisce una base per migliorare l'attrattiva visiva delle tue diapositive.
## Domande frequenti
### Aspose.Slides è adatto sia per applicazioni Windows che web?
Sì, Aspose.Slides può essere utilizzato sia in applicazioni Windows che web.
### Posso scaricare una prova gratuita di Aspose.Slides prima dell'acquisto?
 Sì, puoi scaricare una versione di prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione completa per Aspose.Slides per .NET?
 La documentazione è disponibile[Qui](https://reference.aspose.com/slides/net/).
### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Esiste un forum di supporto per Aspose.Slides?
 Sì, puoi visitare il forum di supporto[Qui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
