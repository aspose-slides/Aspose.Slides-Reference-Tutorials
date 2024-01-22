---
title: Aspose.Slides collega le forme senza problemi in .NET
linktitle: Connessione di forme utilizzando i connettori nella presentazione
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Esplora la potenza di Aspose.Slides per .NET, collegando facilmente le forme nelle tue presentazioni. Migliora le tue diapositive con connettori dinamici.
type: docs
weight: 29
url: /it/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## introduzione
Nel mondo dinamico delle presentazioni, la possibilità di collegare le forme utilizzando i connettori aggiunge un livello di sofisticatezza alle tue diapositive. Aspose.Slides per .NET consente agli sviluppatori di raggiungere questo obiettivo senza problemi. Questo tutorial ti guiderà attraverso il processo, suddividendo ogni passaggio per garantire una chiara comprensione.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Conoscenza base di C# e framework .NET.
-  Aspose.Slides per .NET installato. In caso contrario, scaricalo[Qui](https://releases.aspose.com/slides/net/).
- Un ambiente di sviluppo creato.
## Importa spazi dei nomi
Nel codice C#, inizia importando gli spazi dei nomi necessari:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Configurare la directory dei documenti
Inizia definendo la directory per il tuo documento:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Istanziare la lezione di presentazione
Crea un'istanza della classe Presentation per rappresentare il tuo file PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Accesso alla raccolta di forme per la diapositiva selezionata
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Aggiungi forme alla diapositiva
Aggiungi le forme necessarie alla tua diapositiva, come Ellisse e Rettangolo:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Aggiungi forma connettore
Includi una forma connettore nella raccolta forme della diapositiva:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Connetti forme con connettore
Specificare le forme da connettere tramite il connettore:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Reindirizza connettore
Chiama il metodo di reindirizzamento per impostare il percorso più breve automatico tra le forme:
```csharp
connector.Reroute();
```
## 7. Salva presentazione
Salva la presentazione per visualizzare le forme connesse:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusione
Congratulazioni! Hai collegato con successo le forme utilizzando i connettori nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Migliora le tue presentazioni con questa funzionalità avanzata e affascina il tuo pubblico.
## Domande frequenti
### Aspose.Slides per .NET è compatibile con l'ultimo framework .NET?
Sì, Aspose.Slides per .NET viene regolarmente aggiornato per garantire la compatibilità con le ultime versioni di .NET framework.
### Posso connettere più di due forme utilizzando un unico connettore?
Assolutamente, puoi connettere più forme estendendo la logica del connettore nel tuo codice.
### Esistono limitazioni sulle forme che posso connettere?
Aspose.Slides per .NET supporta la connessione di varie forme, incluse forme base, arte intelligente e forme personalizzate.
### Come posso personalizzare l'aspetto del connettore?
Esplora la documentazione di Aspose.Slides per i metodi per personalizzare l'aspetto del connettore, come lo stile e il colore della linea.
### Esiste un forum della community per il supporto di Aspose.Slides?
 Sì, puoi trovare assistenza e condividere le tue esperienze nel[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).