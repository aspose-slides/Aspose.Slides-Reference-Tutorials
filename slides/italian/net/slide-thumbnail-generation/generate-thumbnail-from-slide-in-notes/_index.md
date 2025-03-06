---
title: Genera miniatura dalla diapositiva in Notes
linktitle: Genera miniatura dalla diapositiva in Notes
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come generare miniature dalle diapositive nella sezione note della presentazione utilizzando Aspose.Slides per .NET. Migliora i tuoi contenuti visivi!
weight: 12
url: /it/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera miniatura dalla diapositiva in Notes


Nel mondo delle presentazioni moderne, il contenuto visivo è il re. Creare diapositive accattivanti è essenziale per una comunicazione efficace. Un modo per migliorare le tue presentazioni è generare miniature dalle diapositive, soprattutto quando desideri enfatizzare dettagli specifici o condividere una panoramica. Aspose.Slides per .NET è un potente strumento che può aiutarti a raggiungere questo obiettivo senza problemi. In questa guida passo passo, ti guideremo attraverso il processo di generazione di miniature dalle diapositive nella sezione note di una presentazione utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di immergerci nei dettagli, dovresti avere i seguenti prerequisiti:

### 1. Aspose.Slides per .NET

 Assicurati di avere Aspose.Slides per .NET installato e configurato. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

### 2. Ambiente .NET

Dovresti avere un ambiente di sviluppo .NET pronto sul tuo sistema.

### 3. Un file di presentazione

 Avere un file di presentazione (ad esempio,`ThumbnailFromSlideInNotes.pptx`) da cui desideri generare le miniature.

Ora suddividiamo il processo in passaggi:

## Passaggio 1: importa gli spazi dei nomi

Innanzitutto, devi importare gli spazi dei nomi necessari per lavorare con Aspose.Slides. Aggiungi il seguente codice all'inizio dello script C#:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Passaggio 2: carica la presentazione

 Successivamente, dovrai caricare il file di presentazione che contiene le diapositive con le note. Utilizzare il codice seguente per istanziare a`Presentation` classe:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Il tuo codice va qui
}
```

## Passaggio 3: accedi alla diapositiva

Puoi scegliere per quale diapositiva della presentazione desideri generare una miniatura. In questo esempio, accederemo alla prima diapositiva:

```csharp
ISlide sld = pres.Slides[0];
```

## Passaggio 4: definire le dimensioni desiderate

Specifica le dimensioni (larghezza e altezza) per la miniatura che desideri generare. Ad esempio:

```csharp
int desiredX = 1200; // Larghezza
int desiredY = 800;  // Altezza
```

## Passaggio 5: calcolare i fattori di scala

Per garantire che la miniatura si adatti alle dimensioni desiderate, calcolare i fattori di scala come segue:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Passaggio 6: crea una miniatura

Ora crea una miniatura dell'immagine a grandezza naturale utilizzando i fattori di ridimensionamento calcolati:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Passaggio 7: salva la miniatura

Infine, salva la miniatura generata come immagine JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Questo è tutto! Hai generato con successo una miniatura da una diapositiva nella sezione note della presentazione utilizzando Aspose.Slides per .NET.

## Conclusione

Incorporare le miniature nelle tue presentazioni può migliorarne significativamente l'attrattiva visiva e l'efficacia. Aspose.Slides per .NET rende questo processo semplice, consentendoti di creare facilmente miniature personalizzate dalle tue diapositive.

## FAQ (domande frequenti)

### In quali formati posso salvare le miniature generate?
Puoi salvare le miniature in vari formati, inclusi JPEG, PNG e altri, a seconda delle tue esigenze.

### Posso generare miniature per più diapositive contemporaneamente?
Sì, puoi scorrere le diapositive della presentazione e generare miniature per ciascuna di esse.

### Aspose.Slides per .NET è compatibile con diversi framework .NET?
Sì, Aspose.Slides per .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Framework.

### Posso personalizzare l'aspetto delle miniature generate?
Assolutamente! Aspose.Slides per .NET fornisce opzioni per personalizzare l'aspetto delle miniature, come dimensioni, qualità e altro.

### Dove posso ottenere supporto o ulteriore assistenza con Aspose.Slides per .NET?
 Puoi trovare aiuto e interagire con la comunità Aspose su[Forum di supporto di Aspose](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
