---
title: Esporta forme in formato SVG dalla presentazione
linktitle: Esporta forme in formato SVG dalla presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come esportare forme da una presentazione di PowerPoint in formato SVG utilizzando Aspose.Slides per .NET. Guida passo passo con codice sorgente incluso. Estrai in modo efficiente forme per varie applicazioni.
type: docs
weight: 16
url: /it/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Questa guida ti guiderà attraverso il processo di esportazione di forme da una presentazione al formato SVG utilizzando la libreria Aspose.Slides per .NET. Aspose.Slides è una potente API che ti consente di lavorare con i file di Microsoft PowerPoint a livello di codice. In questo tutorial imparerai come estrarre forme da una presentazione e salvarle in formato SVG utilizzando C#.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Visual Studio installato
- Conoscenza di base della programmazione C#
-  Aspose.Slides per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

## Guida passo passo

Segui questi passaggi per esportare forme in formato SVG da una presentazione:

### 1. Crea un nuovo progetto

Apri Visual Studio e crea un nuovo progetto C#.

### 2. Aggiungi riferimento ad Aspose.Slides

Nel tuo progetto, fai clic con il pulsante destro del mouse su "Riferimenti" in Esplora soluzioni, quindi fai clic su "Aggiungi riferimento". Sfoglia e seleziona la DLL Aspose.Slides scaricata.

### 3. Carica la presentazione

```csharp
using Aspose.Slides;

// Carica la presentazione
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Iterare attraverso le forme

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Controlla se la forma è una forma di gruppo
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Esporta la forma in SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Esporta la forma in SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Salva i file SVG

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Salva le modifiche alla presentazione
```

## Domande frequenti

### Come posso installare Aspose.Slides per .NET?

 È possibile scaricare la libreria Aspose.Slides per .NET da[Qui](https://releases.aspose.com/slides/net/). Seguire le istruzioni di installazione fornite nella documentazione.

### Come posso caricare una presentazione di PowerPoint utilizzando Aspose.Slides?

 È possibile caricare una presentazione utilizzando il file`Presentation`costruttore di classi. Fornire il percorso del file PowerPoint come parametro.

### Come posso esportare una forma in formato SVG?

 Puoi usare il`WriteAsSvg` metodo su un`IShape` oggetto per esportarlo nel formato SVG. È necessario specificare il nome del file per l'output SVG.

## Conclusione

In questo tutorial hai imparato come esportare forme da una presentazione di PowerPoint in formato SVG utilizzando la libreria Aspose.Slides per .NET. Ciò può essere utile quando è necessario estrarre singole forme da utilizzare in altre applicazioni o piattaforme che supportano la grafica SVG. Aspose.Slides fornisce un modo semplice ed efficiente per raggiungere questo obiettivo a livello di programmazione.

 Per maggiori dettagli e funzionalità avanzate, fare riferimento a[Aspose.Slides per riferimento all'API .NET](https://reference.aspose.com/slides/net/).