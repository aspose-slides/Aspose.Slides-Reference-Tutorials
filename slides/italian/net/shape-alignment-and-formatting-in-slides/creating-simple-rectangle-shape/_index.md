---
title: Creazione di forme rettangolari con Aspose.Slides per .NET
linktitle: Creazione di una forma rettangolare semplice nelle diapositive di presentazione utilizzando Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Esplora il mondo delle presentazioni PowerPoint dinamiche con Aspose.Slides per .NET. Scopri come creare forme rettangolari accattivanti nelle diapositive con questa guida passo passo.
type: docs
weight: 12
url: /it/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## introduzione
Se stai cercando di migliorare le tue applicazioni .NET con presentazioni PowerPoint dinamiche e visivamente accattivanti, Aspose.Slides per .NET è la soluzione giusta. In questo tutorial, ti guideremo attraverso il processo di creazione di una semplice forma rettangolare nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Visual Studio: assicurati di avere Visual Studio installato sul tuo computer di sviluppo.
-  Aspose.Slides per .NET: scarica e installa la libreria Aspose.Slides per .NET da[Qui](https://releases.aspose.com/slides/net/).
- Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale.
## Importa spazi dei nomi
Nel tuo progetto C#, inizia importando gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Passaggio 1: impostare il progetto
Inizia creando un nuovo progetto C# in Visual Studio. Assicurati che Aspose.Slides per .NET sia correttamente referenziato nel tuo progetto.
## Passaggio 2: inizializzare l'oggetto di presentazione
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Il tuo codice per i passaggi successivi verrà inserito qui.
}
```
## Passaggio 3: ottieni la prima diapositiva
```csharp
ISlide sld = pres.Slides[0];
```
## Passaggio 4: aggiungi la forma automatica rettangolare
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Questo codice aggiunge una forma rettangolare alle coordinate (50, 150) con una larghezza di 150 e un'altezza di 50.
## Passaggio 5: salva la presentazione
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Questo passaggio salva la presentazione con la forma rettangolare aggiunta nella directory specificata.
## Conclusione
Congratulazioni! Hai creato con successo una semplice forma rettangolare in una diapositiva di presentazione utilizzando Aspose.Slides per .NET. Questo è solo l'inizio: Aspose.Slides offre una vasta gamma di funzionalità per personalizzare e migliorare ulteriormente le tue presentazioni.
## Domande frequenti
### Posso utilizzare Aspose.Slides per .NET in ambienti Windows e Linux?
Sì, Aspose.Slides per .NET è indipendente dalla piattaforma e può essere utilizzato sia in ambienti Windows che Linux.
### È disponibile una prova gratuita per Aspose.Slides per .NET?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per .NET?
 Visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.
### Posso acquistare una licenza temporanea per Aspose.Slides per .NET?
 Sì, puoi acquistare una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare la documentazione per Aspose.Slides per .NET?
 Fare riferimento alla documentazione[Qui](https://reference.aspose.com/slides/net/).