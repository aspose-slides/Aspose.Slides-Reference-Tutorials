---
"description": "Scopri come creare splendide forme ellittiche nelle slide delle tue presentazioni utilizzando Aspose.Slides per .NET. Semplici passaggi per un design dinamico!"
"linktitle": "Creazione di una semplice forma ellittica nelle diapositive di una presentazione con Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Crea facilmente la forma ellittica con Aspose.Slides .NET"
"url": "/it/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea facilmente la forma ellittica con Aspose.Slides .NET

## Introduzione
Nel dinamico mondo della progettazione di presentazioni, l'integrazione di forme come l'ellisse può aggiungere un tocco di creatività e professionalità. Aspose.Slides per .NET offre una soluzione potente per la manipolazione programmatica dei file di presentazione. Questo tutorial vi guiderà attraverso il processo di creazione di una semplice forma ellittica nelle slide di una presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarla da [pagina delle release](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo .NET sul tuo computer.
## Importa spazi dei nomi
Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Questi namespace forniscono le classi e i metodi essenziali richiesti per lavorare con diapositive e forme di presentazioni.
## Passaggio 1: impostare la presentazione
Inizia creando una nuova presentazione e accedendo alla prima diapositiva. Aggiungi il seguente codice per ottenere questo risultato:
```csharp
// Percorso verso la directory dei documenti.
string dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Crea un'istanza della classe Presentazione
using (Presentation pres = new Presentation())
{
    // Ottieni la prima diapositiva
    ISlide sld = pres.Slides[0];
```
Questo codice inizializza una nuova presentazione e seleziona la prima diapositiva per ulteriori manipolazioni.
## Passaggio 2: aggiungere la forma ellittica
Ora aggiungiamo una forma ellittica alla diapositiva utilizzando `AddAutoShape` metodo:
```csharp
// Aggiungi forma automatica di tipo ellisse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Questa riga di codice crea una forma ellittica alle coordinate (50, 150) con una larghezza di 150 unità e un'altezza di 50 unità.
## Passaggio 3: salva la presentazione
Infine, salva la presentazione modificata sul disco con un nome file specificato utilizzando il seguente codice:
```csharp
// Scrivi il file PPTX sul disco
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Questo passaggio garantisce che le modifiche vengano mantenute e che sia possibile visualizzare la presentazione risultante con la forma ellittica appena aggiunta.
## Conclusione
Congratulazioni! Hai creato con successo una semplice forma ellittica in una diapositiva di una presentazione utilizzando Aspose.Slides per .NET. Questo tutorial fornisce le nozioni fondamentali su come lavorare con le forme, impostare le presentazioni e salvare i file modificati.
---
## Domande frequenti
### Posso personalizzare ulteriormente la forma dell'ellisse?
Sì, puoi modificare varie proprietà della forma ellittica, come colore, dimensione e posizione, per soddisfare specifici requisiti di progettazione.
### Aspose.Slides è compatibile con gli ultimi framework .NET?
Sì, Aspose.Slides viene aggiornato regolarmente per garantire la compatibilità con i framework .NET più recenti.
### Dove posso trovare altri tutorial ed esempi per Aspose.Slides?
Visita il [documentazione](https://reference.aspose.com/slides/net/) per guide ed esempi completi.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
Segui il [collegamento di licenza temporaneo](https://purchase.aspose.com/temporary-license/) per richiedere una licenza temporanea per scopi di prova.
### Hai bisogno di assistenza o hai domande specifiche?
Visita il [Forum di supporto di Aspose.Slides](https://forum.aspose.com/c/slides/11) per ricevere aiuto dalla comunità e dagli esperti.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}