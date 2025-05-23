---
"description": "Esplora la potenza di Aspose.Slides per .NET, collegando le forme senza sforzo nelle tue presentazioni. Migliora le tue diapositive con connettori dinamici."
"linktitle": "Collegamento di forme tramite connettori nella presentazione"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Collega le forme senza soluzione di continuità in .NET"
"url": "/it/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Collega le forme senza soluzione di continuità in .NET

## Introduzione
Nel dinamico mondo delle presentazioni, la possibilità di collegare le forme tramite connettori aggiunge un tocco di raffinatezza alle diapositive. Aspose.Slides per .NET consente agli sviluppatori di raggiungere questo obiettivo in modo semplice e intuitivo. Questo tutorial vi guiderà attraverso il processo, analizzando ogni passaggio per garantirvi una chiara comprensione.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
- Conoscenza di base di C# e .NET Framework.
- Aspose.Slides per .NET installato. In caso contrario, scaricalo. [Qui](https://releases.aspose.com/slides/net/).
- Impostazione di un ambiente di sviluppo.
## Importa spazi dei nomi
Nel codice C#, inizia importando gli spazi dei nomi necessari:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Impostare la directory dei documenti
Iniziamo definendo la directory per il documento:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Istanziare la classe di presentazione
Crea un'istanza della classe Presentation per rappresentare il tuo file PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Accesso alla raccolta di forme per la diapositiva selezionata
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Aggiungi forme alla diapositiva
Aggiungi le forme necessarie alla diapositiva, come Ellisse e Rettangolo:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Aggiungi forma connettore
Includi una forma connettore nella raccolta forme della diapositiva:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Collega le forme con il connettore
Specificare le forme da collegare tramite il connettore:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Reindirizza il connettore
Chiama il metodo reroute per impostare automaticamente il percorso più breve tra le forme:
```csharp
connector.Reroute();
```
## 7. Salva la presentazione
Salva la presentazione per visualizzare le forme collegate:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusione
Congratulazioni! Hai collegato correttamente le forme utilizzando i connettori nelle diapositive della presentazione con Aspose.Slides per .NET. Migliora le tue presentazioni con questa funzionalità avanzata e conquista il tuo pubblico.
## Domande frequenti
### Aspose.Slides per .NET è compatibile con l'ultimo framework .NET?
Sì, Aspose.Slides per .NET viene aggiornato regolarmente per garantire la compatibilità con le ultime versioni del framework .NET.
### Posso collegare più di due forme utilizzando un singolo connettore?
Certamente, puoi connettere più forme estendendo la logica del connettore nel tuo codice.
### Ci sono delle limitazioni riguardo alle forme che posso collegare?
Aspose.Slides per .NET supporta la connessione di varie forme, tra cui forme base, forme intelligenti e forme personalizzate.
### Come posso personalizzare l'aspetto del connettore?
Esplora la documentazione di Aspose.Slides per scoprire metodi per personalizzare l'aspetto del connettore, come lo stile e il colore della linea.
### Esiste un forum della community per il supporto di Aspose.Slides?
Sì, puoi trovare assistenza e condividere le tue esperienze nel [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}