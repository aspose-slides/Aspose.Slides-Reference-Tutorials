---
title: Animazioni di forme semplificate con Aspose.Slides
linktitle: Applicazione di animazioni alle forme nelle diapositive della presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Crea presentazioni straordinarie con Aspose.Slides per .NET. Scopri come applicare le animazioni alle forme in questa guida passo passo. Migliora le tue diapositive ora!
weight: 21
url: /it/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Animazioni di forme semplificate con Aspose.Slides

## introduzione
Nel mondo delle presentazioni dinamiche, l'aggiunta di animazioni alle forme può migliorare significativamente l'attrattiva visiva e il coinvolgimento delle tue diapositive. Aspose.Slides per .NET fornisce un potente toolkit per raggiungere questo obiettivo senza problemi. In questo tutorial ti guideremo attraverso il processo di applicazione delle animazioni alle forme utilizzando Aspose.Slides, consentendoti di creare presentazioni accattivanti che lasciano un'impressione duratura.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere a disposizione quanto segue:
1.  Aspose.Slides per .NET: assicurati di avere la libreria installata e pronta per l'uso. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).
2. Ambiente di sviluppo: imposta il tuo ambiente di sviluppo preferito con le configurazioni necessarie.
3. Directory documenti: crea una directory in cui archiviare i file di presentazione.
## Importa spazi dei nomi
Nella tua applicazione .NET, inizia importando gli spazi dei nomi richiesti:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## Passaggio 1: crea una presentazione
 Inizia creando una nuova presentazione utilizzando il file`Presentation` classe:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Il tuo codice per creare una presentazione va qui.
}
```
## Passaggio 2: aggiungi forma animata
Ora aggiungiamo una forma animata alla prima diapositiva della presentazione:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## Passaggio 3: applica l'effetto animazione
Aggiungi l'effetto di animazione "PathFootball" alla forma creata:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Passaggio 4: crea il pulsante di attivazione
Crea un pulsante che attiverà l'animazione:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Passaggio 5: definire il percorso utente personalizzato
Definire un percorso utente personalizzato per l'animazione:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// Salva la presentazione come PPTX su disco
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
Questo completa la guida passo passo per applicare animazioni alle forme utilizzando Aspose.Slides per .NET.
## Conclusione
Incorporare animazioni nelle tue presentazioni aggiunge un elemento dinamico che cattura l'attenzione del tuo pubblico. Con Aspose.Slides, hai uno strumento robusto per integrare perfettamente questi effetti ed elevare le tue presentazioni al livello successivo.
## Domande frequenti
### Posso applicare più animazioni a una singola forma?
Sì, Aspose.Slides ti consente di aggiungere più effetti di animazione a una singola forma, fornendo flessibilità nella creazione di animazioni complesse.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides garantisce la compatibilità con varie versioni di PowerPoint, assicurando che le tue presentazioni funzionino perfettamente su diverse piattaforme.
### Dove posso trovare risorse aggiuntive e supporto per Aspose.Slides?
 Esplorare la[documentazione](https://reference.aspose.com/slides/net/) e cercare assistenza in[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Ho bisogno di una licenza per Aspose.Slides per utilizzare la libreria?
 Sì, puoi acquisire una licenza[Qui](https://purchase.aspose.com/buy) per sbloccare tutto il potenziale di Aspose.Slides.
### Posso provare Aspose.Slides prima dell'acquisto?
 Certamente! Utilizza il[prova gratuita](https://releases.aspose.com/) per sperimentare le capacità di Aspose.Slides prima di prendere un impegno.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
