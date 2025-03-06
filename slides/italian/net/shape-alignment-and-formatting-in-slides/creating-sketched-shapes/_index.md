---
title: Crea splendide forme di schizzo con Aspose.Slides
linktitle: Creazione di forme di schizzo nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come aggiungere forme di schizzo creative alle diapositive della presentazione utilizzando Aspose.Slides per .NET. Migliora l'attrattiva visiva senza sforzo!
weight: 13
url: /it/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Benvenuti nella nostra guida passo passo sulla creazione di forme di schizzo nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Se vuoi aggiungere un tocco di creatività alle tue presentazioni, le forme abbozzate forniscono un'estetica unica e disegnata a mano. In questo tutorial ti guideremo attraverso il processo, suddividendolo in semplici passaggi per garantire un'esperienza fluida.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides per .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo .NET con il tuo IDE preferito.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto .NET. Questo passaggio garantisce l'accesso alle classi e alle funzionalità necessarie per lavorare con Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Passaggio 1: impostare il progetto
Inizia creando un nuovo progetto .NET o aprendone uno esistente. Assicurati di includere Aspose.Slides nei riferimenti del tuo progetto.
## Passaggio 2: inizializzare Aspose.Slides
Inizializza Aspose.Slides aggiungendo il seguente frammento di codice. Ciò imposta la presentazione e specifica i percorsi di output per il file di presentazione e l'immagine in miniatura.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continua con i passaggi successivi...
}
```
## Passaggio 3: aggiungi la forma abbozzata
Ora aggiungiamo una forma abbozzata alla diapositiva. In questo esempio aggiungeremo un rettangolo con un effetto schizzo a mano libera.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Trasforma la forma in uno schizzo di uno stile a mano libera
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Passaggio 4: genera miniatura
Genera una miniatura della diapositiva per visualizzare la forma disegnata. Salva la miniatura come file PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Passaggio 5: salva la presentazione
Salva il file di presentazione con la forma abbozzata.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Questo è tutto! Hai creato con successo una presentazione con forme abbozzate utilizzando Aspose.Slides per .NET.
## Conclusione
L'aggiunta di forme di schizzo alle diapositive della presentazione può migliorare l'attrattiva visiva e coinvolgere il pubblico. Con Aspose.Slides per .NET, il processo diventa semplice, permettendoti di liberare la tua creatività senza sforzo.
## Domande frequenti
### 1. Posso personalizzare l'effetto abbozzato?
 Sì, Aspose.Slides per .NET offre varie opzioni di personalizzazione per gli effetti di schizzo. Fare riferimento al[documentazione](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
### 2. È disponibile una prova gratuita?
 Certamente! Puoi esplorare una prova gratuita di Aspose.Slides per .NET[Qui](https://releases.aspose.com/).
### 3. Dove posso ottenere supporto?
 Per qualsiasi assistenza o domanda, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Come posso acquistare Aspose.Slides per .NET?
 Per acquistare Aspose.Slides per .NET, visitare il sito[pagina di acquisto](https://purchase.aspose.com/buy).
### 5. Offrite licenze temporanee?
 Sì, sono disponibili licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
