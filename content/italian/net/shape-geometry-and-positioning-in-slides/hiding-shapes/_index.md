---
title: Nascondi forme in PowerPoint con Aspose.Slides .NET Tutorial
linktitle: Nascondere le forme nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come nascondere le forme nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Personalizza le presentazioni a livello di codice con questa guida passo passo.
type: docs
weight: 21
url: /it/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## introduzione
Nel mondo dinamico delle presentazioni, la personalizzazione è fondamentale. Aspose.Slides per .NET fornisce una potente soluzione per manipolare le presentazioni di PowerPoint a livello di codice. Un requisito comune è la possibilità di nascondere forme specifiche all'interno di una diapositiva. Questo tutorial ti guiderà attraverso il processo di nascondere le forme nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides installata. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo preferito per .NET.
- Conoscenza di base di C#: familiarizza con C# poiché gli esempi di codice forniti sono in questo linguaggio.
## Importa spazi dei nomi
Per iniziare a lavorare con Aspose.Slides, importa gli spazi dei nomi necessari nel tuo progetto C#. Ciò garantisce l'accesso alle classi e ai metodi richiesti.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Ora suddividiamo il codice di esempio in più passaggi per una comprensione chiara e concisa.
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto C# e assicurati di includere la libreria Aspose.Slides.
## Passaggio 2: crea una presentazione
 Istanziare il`Presentation` classe, che rappresenta il file PowerPoint. Aggiungi una diapositiva e ottieni un riferimento ad essa.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Passaggio 3: aggiungi forme alla diapositiva
Aggiungi forme automatiche alla diapositiva, come rettangoli e lune, con dimensioni specifiche.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Passaggio 4: nascondi le forme in base al testo alternativo
Specifica un testo alternativo e nascondi le forme che corrispondono a questo testo.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Passaggio 5: salva la presentazione
Salva la presentazione modificata su disco in formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusione
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Domande frequenti
### Aspose.Slides è compatibile con .NET Core?
Sì, Aspose.Slides supporta .NET Core, fornendo flessibilità nel tuo ambiente di sviluppo.
### Posso nascondere forme in base a condizioni diverse dal testo alternativo?
Assolutamente! Puoi personalizzare la logica di occultamento in base a vari attributi come tipo di forma, colore o posizione.
### Dove posso trovare ulteriore documentazione Aspose.Slides?
 Esplora la documentazione[Qui](https://reference.aspose.com/slides/net/) per approfondimenti ed esempi.
### Sono disponibili licenze temporanee per Aspose.Slides?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) a scopo di test.
### Come posso ottenere il supporto della community per Aspose.Slides?
 Unisciti alla community di Aspose.Slides su[Forum](https://forum.aspose.com/c/slides/11) per discussioni e assistenza.