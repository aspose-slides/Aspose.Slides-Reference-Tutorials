---
title: Padroneggiare la rotazione 3D nelle presentazioni con Aspose.Slides per .NET
linktitle: Applicazione dell'effetto di rotazione 3D alle forme nelle diapositive della presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Migliora le tue presentazioni con Aspose.Slides per .NET! Impara ad applicare gli effetti di rotazione 3D alle forme in questo tutorial. Crea presentazioni dinamiche e visivamente sorprendenti.
type: docs
weight: 23
url: /it/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## introduzione
Creare diapositive di presentazione coinvolgenti e dinamiche è un aspetto chiave di una comunicazione efficace. Aspose.Slides per .NET fornisce un potente set di strumenti per migliorare le tue presentazioni, inclusa la possibilità di applicare effetti di rotazione 3D alle forme. In questo tutorial, esamineremo il processo di applicazione di un effetto di rotazione 3D alle forme nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Slides per .NET: assicurati di avere la libreria Aspose.Slides per .NET installata. Puoi scaricarlo da[sito web](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo .NET, come Visual Studio, per scrivere ed eseguire il tuo codice.
## Importa spazi dei nomi
Nel tuo progetto .NET, importa gli spazi dei nomi necessari per sfruttare la funzionalità di Aspose.Slides. Includi i seguenti spazi dei nomi all'inizio del codice:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto nel tuo ambiente di sviluppo .NET preferito. Assicurati di aver aggiunto il riferimento Aspose.Slides al tuo progetto.
## Passaggio 2: inizializza la presentazione
Crea un'istanza di una classe di presentazione per iniziare a lavorare con le diapositive:
```csharp
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungi forma automatica
Aggiungi una forma alla diapositiva, specificandone il tipo, la posizione e le dimensioni:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Passaggio 4: imposta l'effetto di rotazione 3D
Configura l'effetto di rotazione 3D per la forma automatica:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Passaggio 5: salva la presentazione
Salva la presentazione modificata con l'effetto di rotazione 3D applicato:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Passaggio 6: ripetere per altre forme
Se disponi di forme aggiuntive, ripeti i passaggi da 3 a 5 per ciascuna forma.
## Conclusione
L'aggiunta di effetti di rotazione 3D alle forme nelle diapositive della presentazione può migliorarne significativamente l'attrattiva visiva. Con Aspose.Slides per .NET, questo processo diventa semplice, consentendoti di creare presentazioni accattivanti.
## Domande frequenti
### Posso applicare la rotazione 3D alle caselle di testo in Aspose.Slides per .NET?
Sì, puoi applicare effetti di rotazione 3D a varie forme, comprese le caselle di testo, utilizzando Aspose.Slides.
### È disponibile una versione di prova di Aspose.Slides per .NET?
 Sì, puoi accedere alla versione di prova[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per .NET?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.
### Posso acquistare una licenza temporanea per Aspose.Slides per .NET?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare la documentazione dettagliata per Aspose.Slides per .NET?
 La documentazione è disponibile[Qui](https://reference.aspose.com/slides/net/).