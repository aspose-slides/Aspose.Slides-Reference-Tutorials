---
title: Esporta file multimediali in HTML dalla presentazione
linktitle: Esporta file multimediali in HTML dalla presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Ottimizza la condivisione delle presentazioni con Aspose.Slides per .NET! Scopri come esportare file multimediali in HTML dalla tua presentazione in questa guida passo passo.
weight: 15
url: /it/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esporta file multimediali in HTML dalla presentazione


In questo tutorial ti guideremo attraverso il processo di esportazione di file multimediali in HTML da una presentazione utilizzando Aspose.Slides per .NET. Aspose.Slides è una potente API che ti consente di lavorare con le presentazioni di PowerPoint a livello di codice. Al termine di questa guida sarai in grado di convertire facilmente le tue presentazioni in formato HTML. Quindi iniziamo!

## 1. Introduzione

Le presentazioni di PowerPoint spesso contengono elementi multimediali come video e potrebbe essere necessario esportare queste presentazioni in formato HTML per la compatibilità web. Aspose.Slides per .NET fornisce un modo conveniente per eseguire questa attività a livello di codice.

## 2. Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

-  Aspose.Slides per .NET: dovresti avere la libreria Aspose.Slides per .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## 3. Caricamento di una presentazione

Per iniziare, devi caricare la presentazione PowerPoint che desideri convertire in HTML. Dovrai anche specificare la directory di output in cui verrà salvato il file HTML. Ecco il codice per caricare una presentazione:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Caricamento di una presentazione
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Il tuo codice qui
}
```

## 4. Impostazione delle opzioni HTML

Ora impostiamo le opzioni HTML per la conversione. Configureremo un controller HTML, un formattatore HTML e il formato dell'immagine della diapositiva. Questo codice garantirà che il tuo file HTML contenga i componenti necessari per la visualizzazione di elementi multimediali.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.esempio.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Impostazione delle opzioni HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Salvataggio del file HTML

 Con le opzioni HTML configurate, ora puoi salvare il file HTML. IL`Save` dell'oggetto di presentazione genererà il file HTML con elementi multimediali incorporati.

```csharp
// Salvataggio del file
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Conclusione

Congratulazioni! Hai esportato con successo file multimediali in HTML da una presentazione di PowerPoint utilizzando Aspose.Slides per .NET. Ciò ti consente di condividere facilmente le tue presentazioni online e di garantire che gli elementi multimediali vengano visualizzati correttamente.

## 7. Domande frequenti

### Q1: Aspose.Slides per .NET è una libreria gratuita?
 A1: Aspose.Slides per .NET è una libreria commerciale, ma puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/) per provarlo.

### Q2: Posso personalizzare ulteriormente l'output HTML?
R2: Sì, puoi personalizzare l'output HTML modificando le opzioni HTML nel codice.

### Q3: Aspose.Slides per .NET supporta altri formati di esportazione?
A3: Sì, Aspose.Slides per .NET supporta vari formati di esportazione, inclusi PDF, formati di immagine e altro.

### Q4: Dove posso ottenere supporto per Aspose.Slides per .NET?
 R4: Puoi trovare supporto e porre domande sui forum Aspose[Qui](https://forum.aspose.com/).

### Q5: Come posso acquistare una licenza per Aspose.Slides per .NET?
 A5: È possibile acquistare una licenza da[questo link](https://purchase.aspose.com/buy).

Ora che hai completato questo tutorial, hai le competenze per esportare file multimediali in HTML da presentazioni PowerPoint utilizzando Aspose.Slides per .NET. Divertiti a condividere online le tue presentazioni ricche di contenuti multimediali!
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
