---
title: Padroneggiare le animazioni di PowerPoint con Aspose.Slides .NET
linktitle: Ripeti l'animazione sulla diapositiva
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Migliora le presentazioni PowerPoint utilizzando Aspose.Slides per .NET. Controlla le animazioni senza sforzo, affascina il tuo pubblico e lascia un'impressione duratura.
type: docs
weight: 12
url: /it/net/slide-animation-control/repeat-animation-on-slide/
---
## introduzione
Nel dinamico mondo delle presentazioni, la capacità di controllare le animazioni gioca un ruolo fondamentale nel coinvolgere e catturare l'attenzione del pubblico. Aspose.Slides per .NET consente agli sviluppatori di farsi carico dei tipi di animazione all'interno delle diapositive, consentendo una presentazione più interattiva e visivamente accattivante. In questo tutorial esploreremo come controllare i tipi di animazione su una diapositiva utilizzando Aspose.Slides per .NET, passo dopo passo.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1.  Aspose.Slides per .NET Library: scarica e installa la libreria da[Qui](https://releases.aspose.com/slides/net/).
2. Ambiente di sviluppo .NET: configura un ambiente di sviluppo .NET sul tuo computer.
## Importa spazi dei nomi
Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari per sfruttare le funzionalità fornite da Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Passaggio 1: impostare il progetto
Crea una nuova directory per il tuo progetto e crea un'istanza della classe Presentation per rappresentare il file di presentazione.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Il tuo codice va qui
}
```
## Passaggio 2: accedi alla sequenza degli effetti
Recupera la sequenza degli effetti per la prima diapositiva utilizzando la proprietà MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Passaggio 3: accedi al primo effetto
Ottieni il primo effetto della sequenza principale per manipolarne le proprietà.
```csharp
IEffect effect = effectsSequence[0];
```
## Passaggio 4: modifica le impostazioni di ripetizione
Modifica la proprietà Temporizzazione/Ripetizione dell'effetto su "Fino alla fine della diapositiva".
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Passaggio 5: salva la presentazione
Salva la presentazione modificata per visualizzare le modifiche.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Ripeti questi passaggi per effetti aggiuntivi o personalizzali in base alle tue esigenze di presentazione.
## Conclusione
Incorporare animazioni dinamiche nelle presentazioni di PowerPoint non è mai stato così facile con Aspose.Slides per .NET. Questa guida passo passo ti fornisce le conoscenze per controllare i tipi di animazione, assicurando che le tue diapositive lascino un'impressione duratura sul tuo pubblico.
## Domande frequenti
### Posso applicare queste animazioni a oggetti specifici all'interno di una diapositiva?
Sì, puoi prendere di mira oggetti specifici accedendo ai loro effetti individuali all'interno della sequenza.
### Aspose.Slides è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides fornisce supporto per un'ampia gamma di versioni di PowerPoint, garantendo la compatibilità sia con le versioni vecchie che con quelle nuove.
### Dove posso trovare ulteriori esempi e risorse?
 Esplorare la[documentazione](https://reference.aspose.com/slides/net/) per esempi esaustivi e spiegazioni dettagliate.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Visita[Qui](https://purchase.aspose.com/temporary-license/) per informazioni su come ottenere una licenza temporanea.
### Hai bisogno di aiuto o hai altre domande?
 Interagisci con la community di Aspose.Slides su[Forum di assistenza](https://forum.aspose.com/c/slides/11).