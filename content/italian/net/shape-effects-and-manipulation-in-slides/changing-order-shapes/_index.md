---
title: Rimodellamento delle diapositive della presentazione con Aspose.Slides per .NET
linktitle: Modifica dell'ordine delle forme nelle diapositive della presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come rimodellare le diapositive della presentazione utilizzando Aspose.Slides per .NET. Segui questa guida passo passo per riordinare le forme e migliorare l'attrattiva visiva.
type: docs
weight: 26
url: /it/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## introduzione
Creare diapositive di presentazione visivamente accattivanti è un aspetto cruciale di una comunicazione efficace. Aspose.Slides per .NET consente agli sviluppatori di manipolare le diapositive a livello di codice, offrendo un'ampia gamma di funzionalità. In questo tutorial, approfondiremo il processo di modifica dell'ordine delle forme nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides integrata nel tuo progetto .NET. In caso contrario, puoi scaricarlo da[pagina dei comunicati](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo funzionante con Visual Studio o qualsiasi altro strumento di sviluppo .NET.
- Comprensione di base di C#: familiarizza con le basi del linguaggio di programmazione C#.
## Importa spazi dei nomi
Nel tuo progetto C#, includi gli spazi dei nomi necessari per accedere alla funzionalità Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto in Visual Studio o nel tuo ambiente di sviluppo .NET preferito. Assicurati che Aspose.Slides per .NET sia referenziato nel tuo progetto.
## Passaggio 2: carica la presentazione
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Passaggio 3: accedi alla diapositiva e alle forme
```csharp
ISlide slide = presentation.Slides[0];
```
## Passaggio 4: aggiungi una nuova forma
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Passaggio 5: modifica il testo nella forma
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Passaggio 6: aggiungi un'altra forma
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Passaggio 7: modificare l'ordine delle forme
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Passaggio 8: salva la presentazione modificata
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Questo completa la guida passo passo per modificare l'ordine delle forme nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Conclusione
Aspose.Slides per .NET semplifica il compito di manipolare le diapositive di presentazione a livello di codice. Seguendo questo tutorial, hai imparato come riordinare le forme, permettendoti di migliorare l'attrattiva visiva delle tue presentazioni.
## Domande frequenti
### D: Posso utilizzare Aspose.Slides per .NET in ambienti Windows e Linux?
R: Sì, Aspose.Slides per .NET è compatibile con ambienti Windows e Linux.
### D: Esistono considerazioni sulla licenza per l'utilizzo di Aspose.Slides in un progetto commerciale?
 R: Sì, puoi trovare i dettagli della licenza e le opzioni di acquisto su[Pagina di acquisto di Aspose.Slides](https://purchase.aspose.com/buy).
### D: È disponibile una prova gratuita per Aspose.Slides per .NET?
 R: Sì, puoi esplorare le funzionalità con[prova gratuita](https://releases.aspose.com/) disponibile sul sito Web Aspose.Slides.
### D: Dove posso trovare supporto o porre domande relative ad Aspose.Slides per .NET?
 R: Visita il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per ottenere supporto e interagire con la comunità.
### D: Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?
 R: Puoi acquisire a[licenza temporanea](https://purchase.aspose.com/temporary-license/) a fini di valutazione.