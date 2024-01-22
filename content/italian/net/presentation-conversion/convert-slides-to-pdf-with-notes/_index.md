---
title: Converti diapositive in PDF con Note
linktitle: Converti diapositive in PDF con Note
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Converti facilmente diapositive di presentazione con note del relatore in PDF utilizzando Aspose.Slides per .NET. Conserva contenuto e contesto senza problemi.
type: docs
weight: 18
url: /it/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

# Scrivi una guida tutorial passo passo sulla conversione di diapositive in PDF con note utilizzando Aspose.Slides per .NET

Stai cercando un modo affidabile per convertire le tue diapositive PowerPoint in formato PDF preservando tutte le note importanti? Non guardare oltre! In questo tutorial completo, ti guideremo attraverso il processo di utilizzo di Aspose.Slides per .NET per realizzare questa attività passo dopo passo.

## 1. Introduzione

La conversione di diapositive PowerPoint in PDF con note può essere uno strumento prezioso per condividere presentazioni garantendo al contempo la conservazione del contesto e dei commenti importanti. Aspose.Slides per .NET fornisce una potente soluzione per questo compito.

## 2. Configurazione dell'ambiente

Prima di immergerci nel processo di codifica, assicurati di avere configurato l'ambiente necessario. Avrai bisogno:

- Visual Studio o il tuo ambiente di sviluppo .NET preferito.
- Aspose.Slides per la libreria .NET installata.
- Una presentazione PowerPoint con le note che desideri convertire.

## 3. Caricamento della presentazione

Nel codice C# devi caricare la presentazione PowerPoint che desideri convertire. Ecco come puoi farlo:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Clonazione della diapositiva

Per assicurarti che il tuo PDF includa tutte le diapositive necessarie con le note, puoi clonarle dalla presentazione originale. Ecco come:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Regolazione delle dimensioni della diapositiva

Potresti voler regolare le dimensioni della diapositiva per adattarla al tuo PDF. Aspose.Slides per .NET ti consente di farlo con facilità:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configurazione delle opzioni PDF

Per controllare come verranno visualizzate le note nel PDF, puoi configurare le opzioni PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Salvataggio in formato PDF con Notes

Infine, puoi salvare la presentazione come PDF con le note:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusione

Congratulazioni! Hai convertito con successo le tue diapositive PowerPoint in un formato PDF preservando tutte le note importanti. Aspose.Slides per .NET rende questo processo semplice ed efficiente.

## 9. Domande frequenti

### Q1: Posso personalizzare il layout delle note nel PDF?

 Sì, puoi personalizzare il layout delle note utilizzando il file`INotesCommentsLayoutingOptions` nelle opzioni PDF.

### Q2: Aspose.Slides per .NET supporta altri formati di output oltre al PDF?

Sì, Aspose.Slides per .NET supporta vari formati di output, inclusi PPTX, DOCX e altri.

### Q3: È disponibile una versione di prova per Aspose.Slides per .NET?

 Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET su[https://releases.aspose.com/](https://releases.aspose.com/).

### Q4: Dove posso ottenere supporto per Aspose.Slides per .NET?

 Puoi trovare supporto e discussioni della community su[https://forum.aspose.com/](https://forum.aspose.com/).

### Q5: posso acquistare una licenza temporanea per Aspose.Slides per .NET?

 Sì, puoi acquistare una licenza temporanea su[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

In conclusione, utilizzando Aspose.Slides per .NET, puoi convertire facilmente le diapositive di PowerPoint in formato PDF con le note intatte. È uno strumento prezioso per i professionisti che hanno bisogno di condividere presentazioni con colleghi e clienti garantendo al tempo stesso che il contesto importante non vada perso.