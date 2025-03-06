---
title: Genera miniatura nelle diapositive con dimensioni personalizzate
linktitle: Genera miniatura con dimensioni personalizzate
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come generare immagini in miniatura personalizzate dalle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Migliora l'esperienza utente e la funzionalità.
weight: 13
url: /it/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


La creazione di immagini in miniatura personalizzate delle presentazioni PowerPoint può essere una risorsa preziosa, sia che tu stia creando un'applicazione interattiva, migliorando l'esperienza utente o ottimizzando i contenuti per varie piattaforme. In questo tutorial, ti guideremo attraverso il processo di generazione di immagini in miniatura personalizzate da presentazioni PowerPoint utilizzando la libreria Aspose.Slides per .NET. Questa potente libreria consente di manipolare, convertire e migliorare i file PowerPoint a livello di codice nelle applicazioni .NET.

## Prerequisiti

Prima di immergerci nella generazione di immagini in miniatura personalizzate, assicurati di disporre dei seguenti prerequisiti:

### 1. Aspose.Slides per .NET

 È necessario che la libreria Aspose.Slides per .NET sia installata nel tuo progetto. Se non l'hai già fatto, puoi trovare la documentazione necessaria e i link per il download[Qui](https://reference.aspose.com/slides/net/).

### 2. Una presentazione di PowerPoint

Assicurati di avere la presentazione PowerPoint da cui desideri generare un'immagine in miniatura personalizzata. Questa presentazione dovrebbe essere accessibile all'interno della directory del progetto.

### 3. Ambiente di sviluppo

Per seguire questo tutorial, dovresti avere una conoscenza pratica della programmazione .NET utilizzando C# e un ambiente di sviluppo configurato, come Visual Studio.

Ora che abbiamo coperto i prerequisiti, suddividiamo il processo di generazione di miniature personalizzate in istruzioni dettagliate.

## Importa spazi dei nomi

Innanzitutto, devi includere gli spazi dei nomi richiesti nel codice C#. Questi spazi dei nomi ti consentono di lavorare con Aspose.Slides e manipolare presentazioni di PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Passaggio 1: caricare la presentazione

Per iniziare, carica la presentazione PowerPoint da cui desideri generare un'immagine in miniatura personalizzata. Ciò si ottiene utilizzando la libreria Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Crea un'istanza di una classe Presentation che rappresenta il file di presentazione
using (Presentation pres = new Presentation(srcFileName))
{
    // Il tuo codice per la generazione delle miniature andrà qui
}
```

## Passaggio 2: accedi alla diapositiva

All'interno della presentazione caricata, devi accedere alla diapositiva specifica da cui desideri generare l'immagine in miniatura personalizzata. Puoi scegliere la diapositiva in base al suo indice.

```csharp
// Accedi alla prima diapositiva (puoi modificare l'indice secondo necessità)
ISlide sld = pres.Slides[0];
```

## Passaggio 3: Definisci le dimensioni delle miniature personalizzate

Specifica le dimensioni desiderate per la tua immagine in miniatura personalizzata. Puoi definire la larghezza e l'altezza in pixel in base ai requisiti della tua applicazione.

```csharp
int desiredX = 1200; // Larghezza
int desiredY = 800;  // Altezza
```

## Passaggio 4: calcolare i fattori di scala

Per mantenere le proporzioni della diapositiva, calcola i fattori di scala per le dimensioni X e Y in base alle dimensioni della diapositiva e alle dimensioni desiderate.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Passaggio 5: genera l'immagine in miniatura

Crea un'immagine a grandezza naturale della diapositiva con le dimensioni personalizzate specificate e salvala su disco in formato JPEG.

```csharp
// Crea un'immagine a grandezza naturale
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Salva l'immagine su disco in formato JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Ora che hai seguito questi passaggi, dovresti aver generato con successo un'immagine in miniatura personalizzata dalla tua presentazione di PowerPoint.

## Conclusione

La generazione di immagini in miniatura personalizzate da presentazioni PowerPoint utilizzando Aspose.Slides per .NET è un'abilità preziosa che può migliorare l'esperienza utente e la funzionalità delle tue applicazioni. Seguendo i passaggi descritti in questo tutorial, puoi creare facilmente miniature personalizzate che soddisfano i tuoi requisiti specifici.

---

## FAQ (domande frequenti)

### Cos'è Aspose.Slides per .NET?
Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori di lavorare con presentazioni PowerPoint a livello di codice nelle applicazioni .NET.

### Dove posso trovare la documentazione per Aspose.Slides per .NET?
 Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/net/).

### Aspose.Slides per .NET è gratuito?
 Aspose.Slides per .NET è una libreria commerciale. È possibile trovare informazioni su prezzi e licenze[Qui](https://purchase.aspose.com/buy).

### Ho bisogno di competenze di programmazione avanzate per utilizzare Aspose.Slides per .NET?
Sebbene una certa conoscenza della programmazione .NET sia utile, Aspose.Slides per .NET fornisce un'API intuitiva che semplifica il lavoro con le presentazioni di PowerPoint.

### Il supporto tecnico è disponibile per Aspose.Slides per .NET?
 Sì, puoi accedere al supporto tecnico e ai forum della community[Qui](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
