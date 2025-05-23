---
"description": "Scopri come regolare gli angoli delle linee di collegamento nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Migliora le tue presentazioni con precisione e semplicità."
"linktitle": "Regolazione degli angoli delle linee di collegamento nelle diapositive della presentazione utilizzando Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Regola gli angoli delle linee di collegamento in PowerPoint con Aspose.Slides"
"url": "/it/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Regola gli angoli delle linee di collegamento in PowerPoint con Aspose.Slides

## Introduzione
Creare slide di presentazione visivamente accattivanti spesso richiede regolazioni precise delle linee di collegamento. In questo tutorial, esploreremo come regolare gli angoli delle linee di collegamento nelle slide di una presentazione utilizzando Aspose.Slides per .NET. Aspose.Slides è una potente libreria che consente agli sviluppatori di lavorare con i file di PowerPoint a livello di codice, offrendo ampie funzionalità per la creazione, la modifica e la manipolazione di presentazioni.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Conoscenza di base del linguaggio di programmazione C#.
- Visual Studio o qualsiasi altro ambiente di sviluppo C# installato.
- Libreria Aspose.Slides per .NET. Puoi scaricarla. [Qui](https://releases.aspose.com/slides/net/).
- Un file di presentazione PowerPoint con linee di collegamento che si desidera modificare.
## Importa spazi dei nomi
Per iniziare, assicurati di includere gli spazi dei nomi necessari nel codice C#:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto C# in Visual Studio e installa il pacchetto NuGet Aspose.Slides. Imposta la struttura del progetto con un riferimento alla libreria Aspose.Slides.
## Passaggio 2: caricare la presentazione
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
Carica il file della presentazione di PowerPoint nel `Presentation` oggetto. Sostituisci "Directory dei tuoi documenti" con il percorso effettivo del tuo file.
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
    // Codice per la gestione delle linee di collegamento
}
```
Passa attraverso ogni forma sulla diapositiva per identificare ed elaborare le linee di collegamento.
## Passaggio 5: regolare gli angoli della linea di collegamento
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Codice per la gestione delle forme automatiche
}
else if (shape is Connector)
{
    // Codice per la gestione dei connettori
}
Console.WriteLine(dir);
```
Identifica se la forma è una forma automatica o un connettore e regola gli angoli della linea di collegamento utilizzando lo strumento fornito `getDirection` metodo.
## Passaggio 6: definire il `getDirection` Metodo
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
Implementare il `getDirection` Metodo per calcolare l'angolo della linea di collegamento in base alle sue dimensioni e al suo orientamento.
## Conclusione
Con questi passaggi, puoi regolare a livello di codice gli angoli delle linee di collegamento nella tua presentazione PowerPoint utilizzando Aspose.Slides per .NET. Questo tutorial fornisce le basi per migliorare l'aspetto visivo delle tue diapositive.
## Domande frequenti
### Aspose.Slides è adatto sia per Windows che per applicazioni web?
Sì, Aspose.Slides può essere utilizzato sia in Windows che nelle applicazioni web.
### Posso scaricare una prova gratuita di Aspose.Slides prima di acquistarlo?
Sì, puoi scaricare una versione di prova gratuita [Qui](https://releases.aspose.com/).
### Dove posso trovare una documentazione completa per Aspose.Slides per .NET?
La documentazione è disponibile [Qui](https://reference.aspose.com/slides/net/).
### Come posso ottenere una licenza temporanea per Aspose.Slides?
Puoi ottenere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).
### Esiste un forum di supporto per Aspose.Slides?
Sì, puoi visitare il forum di supporto [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}