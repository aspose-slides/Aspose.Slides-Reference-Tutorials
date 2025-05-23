---
"description": "Scopri come aggiungere forme creative e schizzi alle diapositive delle tue presentazioni utilizzando Aspose.Slides per .NET. Migliora l'impatto visivo senza sforzo!"
"linktitle": "Creazione di forme abbozzate nelle diapositive di una presentazione con Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Crea forme abbozzate straordinarie con Aspose.Slides"
"url": "/it/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea forme abbozzate straordinarie con Aspose.Slides

## Introduzione
Benvenuti alla nostra guida passo passo sulla creazione di forme abbozzate nelle slide delle presentazioni utilizzando Aspose.Slides per .NET. Se desiderate aggiungere un tocco di creatività alle vostre presentazioni, le forme abbozzate offrono un'estetica unica e a mano libera. In questo tutorial, vi guideremo attraverso il processo, suddividendolo in semplici passaggi per garantire un'esperienza fluida.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarla. [Qui](https://releases.aspose.com/slides/net/).
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
Inizia creando un nuovo progetto .NET o aprendone uno esistente. Assicurati di includere Aspose.Slides nei riferimenti del progetto.
## Passaggio 2: inizializzare Aspose.Slides
Inizializza Aspose.Slides aggiungendo il seguente frammento di codice. Questo imposta la presentazione e specifica i percorsi di output per il file di presentazione e l'immagine in miniatura.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Continua con i passaggi successivi...
}
```
## Passaggio 3: aggiungere la forma abbozzata
Ora aggiungiamo una forma abbozzata alla diapositiva. In questo esempio, aggiungeremo un rettangolo con un effetto schizzo a mano libera.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Trasforma la forma in uno schizzo di uno stile a mano libera
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Passaggio 4: Genera miniatura
Genera una miniatura della diapositiva per visualizzare la forma disegnata. Salva la miniatura come file PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Passaggio 5: Salva la presentazione
Salvare il file di presentazione con la forma disegnata.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Ecco fatto! Hai creato con successo una presentazione con forme abbozzate usando Aspose.Slides per .NET.
## Conclusione
Aggiungere forme abbozzate alle diapositive della presentazione può migliorare l'impatto visivo e coinvolgere il pubblico. Con Aspose.Slides per .NET, il processo diventa semplice, permettendoti di liberare la tua creatività senza sforzo.
## Domande frequenti
### 1. Posso personalizzare l'effetto schizzo?
Sì, Aspose.Slides per .NET offre diverse opzioni di personalizzazione per gli effetti di schizzo. Fare riferimento a [documentazione](https://reference.aspose.com/slides/net/) per informazioni dettagliate.
### 2. È disponibile una prova gratuita?
Certamente! Puoi provare la versione di prova gratuita di Aspose.Slides per .NET. [Qui](https://releases.aspose.com/).
### 3. Dove posso trovare supporto?
Per qualsiasi assistenza o domanda, visita il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Come posso acquistare Aspose.Slides per .NET?
Per acquistare Aspose.Slides per .NET, visitare il sito [pagina di acquisto](https://purchase.aspose.com/buy).
### 5. Offrite licenze temporanee?
Sì, sono disponibili licenze temporanee [Qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}