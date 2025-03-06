---
title: Esporta forme in formato SVG dalla presentazione
linktitle: Esporta forme in formato SVG dalla presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come esportare forme da una presentazione di PowerPoint in formato SVG utilizzando Aspose.Slides per .NET. Guida passo passo con codice sorgente incluso. Estrai in modo efficiente forme per varie applicazioni.
weight: 16
url: /it/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Nel mondo digitale di oggi, le presentazioni svolgono un ruolo cruciale nel trasmettere le informazioni in modo efficace. Tuttavia, a volte dobbiamo esportare forme specifiche dalle nostre presentazioni in formati diversi per vari scopi. Uno di questi formati è SVG (Scalable Vector Graphics), noto per la sua scalabilità e adattabilità. In questo tutorial ti guideremo attraverso il processo di esportazione di forme in formato SVG da una presentazione utilizzando Aspose.Slides per .NET.

## 1. Introduzione

Le presentazioni spesso contengono importanti elementi visivi come grafici, diagrammi e illustrazioni. L'esportazione di questi elementi nel formato SVG può essere utile per applicazioni basate sul Web, stampa o ulteriori modifiche nel software di grafica vettoriale. Aspose.Slides per .NET è una potente libreria che ti consente di automatizzare attività come questa.

## 2. Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Un ambiente di sviluppo con Aspose.Slides per .NET installato.
- Una presentazione PowerPoint (PPTX) contenente la forma che desideri esportare.
- Conoscenza base della programmazione C#.

## 3. Configurazione dell'ambiente

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati di aver fatto riferimento alla libreria Aspose.Slides per .NET nel tuo progetto.

## 4. Caricamento della presentazione

Nel codice C#, devi specificare la directory della presentazione e la directory di output per il file SVG. Ecco un esempio:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string outSvgFileName = outPath + "SingleShape.svg";

using (Presentation pres = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // Il tuo codice per esportare la forma verrà inserito qui.
}
```

## 5. Esportazione di una forma in SVG

 All'interno del`using` blocco, puoi accedere alle forme nella presentazione ed esportarle in formato SVG. Qui stiamo esportando la prima forma sulla prima diapositiva:

```csharp
using (Stream stream = new FileStream(outSvgFileName, FileMode.Create, FileAccess.Write))
{
    pres.Slides[0].Shapes[0].WriteAsSvg(stream);
}
```

Puoi personalizzare questo codice per esportare forme diverse o applicare trasformazioni aggiuntive secondo necessità.

## 6. Conclusione

In questo tutorial, abbiamo esaminato il processo di esportazione di forme in formato SVG da una presentazione di PowerPoint utilizzando Aspose.Slides per .NET. Questa potente libreria semplifica l'attività, consentendoti di automatizzare il processo di esportazione e migliorare il flusso di lavoro.

## 7. Domande frequenti

### Q1: Cos'è il formato SVG?

Scalable Vector Graphics (SVG) è un formato di immagine vettoriale basato su XML ampiamente utilizzato per la sua scalabilità e compatibilità con i browser Web.

### Q2: Posso esportare più forme contemporaneamente?

Sì, puoi scorrere le forme nella presentazione ed esportarle una per una.

### Q3: Aspose.Slides per .NET è una libreria a pagamento?

Sì, Aspose.Slides per .NET è una libreria commerciale con una versione di prova gratuita disponibile.

### Q4: Esistono limitazioni all'esportazione di forme con Aspose.Slides?

La possibilità di esportare forme può variare a seconda della complessità della forma e delle funzionalità supportate dalla libreria.

### Q5: Dove posso ottenere supporto per Aspose.Slides per .NET?

 Puoi visitare il[Forum Aspose.Slides](https://forum.aspose.com/) per supporto e discussioni nella comunità.

Ora che hai imparato come esportare forme nel formato SVG, puoi migliorare le tue presentazioni e renderle più versatili per scopi diversi. Buona programmazione!

 Per maggiori dettagli e funzionalità avanzate, fare riferimento a[Aspose.Slides per riferimento all'API .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
