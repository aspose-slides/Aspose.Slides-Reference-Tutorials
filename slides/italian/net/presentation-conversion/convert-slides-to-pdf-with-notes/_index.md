---
"description": "Converti facilmente le slide delle presentazioni con le note del relatore in PDF utilizzando Aspose.Slides per .NET. Mantieni contenuti e contesto impeccabili."
"linktitle": "Converti le diapositive in PDF con Note"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Converti le diapositive in PDF con Note"
"url": "/it/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converti le diapositive in PDF con Note


# Scrivi una guida passo passo sulla conversione di diapositive in PDF con note utilizzando Aspose.Slides per .NET

Stai cercando un modo affidabile per convertire le tue diapositive di PowerPoint in formato PDF, conservando tutte le note importanti? Non cercare oltre! In questo tutorial completo, ti guideremo passo dopo passo attraverso l'utilizzo di Aspose.Slides per .NET per raggiungere questo obiettivo.

## 1. Introduzione

Convertire le diapositive di PowerPoint in PDF con note può essere uno strumento prezioso per condividere le presentazioni, garantendo al contempo la conservazione di contesto e commenti importanti. Aspose.Slides per .NET offre una soluzione potente per questo compito.

## 2. Impostazione dell'ambiente

Prima di immergerci nel processo di codifica, assicurati di aver configurato l'ambiente necessario. Avrai bisogno di:

- Visual Studio o il tuo ambiente di sviluppo .NET preferito.
- Libreria Aspose.Slides per .NET installata.
- Una presentazione PowerPoint con le note che vuoi convertire.

## 3. Caricamento della presentazione

Nel codice C#, devi caricare la presentazione PowerPoint che vuoi convertire. Ecco come fare:

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

Potresti voler adattare le dimensioni della diapositiva al tuo PDF. Aspose.Slides per .NET ti permette di farlo facilmente:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configurazione delle opzioni PDF

Per controllare il modo in cui le tue note verranno visualizzate nel PDF, puoi configurare le opzioni PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Salvataggio in formato PDF con Note

Infine, puoi salvare la presentazione in formato PDF con note:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusion

Congratulazioni! Hai convertito con successo le tue diapositive di PowerPoint in formato PDF, conservando tutte le note importanti. Aspose.Slides per .NET rende questo processo semplice ed efficiente.

## 9. Domande frequenti

### D1: Posso personalizzare il layout delle note nel PDF?

Sì, puoi personalizzare il layout delle note utilizzando `INotesCommentsLayoutingOptions` nelle opzioni PDF.

### D2: Aspose.Slides per .NET supporta altri formati di output oltre al PDF?

Sì, Aspose.Slides per .NET supporta vari formati di output, tra cui PPTX, DOCX e altri.

### D3: È disponibile una versione di prova di Aspose.Slides per .NET?

Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET su [https://releases.aspose.com/](https://releases.aspose.com/).

### D4: Dove posso ottenere supporto per Aspose.Slides per .NET?

Puoi trovare supporto e discussioni della comunità su [https://forum.aspose.com/](https://forum.aspose.com/).

### D5: Posso acquistare una licenza temporanea per Aspose.Slides per .NET?

Sì, puoi acquistare una licenza temporanea su [https://purchase.aspose.com/licenza-temporanea/](https://purchase.aspose.com/temporary-license/).

In conclusione, utilizzando Aspose.Slides per .NET, è possibile convertire facilmente le diapositive di PowerPoint in formato PDF, mantenendo intatte le note. È uno strumento prezioso per i professionisti che devono condividere presentazioni con colleghi e clienti, garantendo al contempo che il contesto importante non venga perso.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}