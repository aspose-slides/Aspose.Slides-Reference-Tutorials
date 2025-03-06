---
title: Crea facilmente la forma dell'ellisse con Aspose.Slides .NET
linktitle: Creazione di una forma ellittica semplice nelle diapositive di presentazione con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come creare straordinarie forme ellittiche nelle diapositive di presentazione utilizzando Aspose.Slides per .NET. Semplici passaggi per un design dinamico!
weight: 11
url: /it/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Nel dinamico mondo del design delle presentazioni, incorporare forme come le ellissi può aggiungere un tocco di creatività e professionalità. Aspose.Slides per .NET offre una potente soluzione per manipolare i file di presentazione a livello di codice. Questo tutorial ti guiderà attraverso il processo di creazione di una semplice forma ellittica nelle diapositive di presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarlo da[pagina dei comunicati](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura un ambiente di sviluppo .NET sul tuo computer.
## Importa spazi dei nomi
Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Questi spazi dei nomi forniscono le classi e i metodi essenziali necessari per lavorare con diapositive e forme di presentazione.
## Passaggio 1: impostare la presentazione
Inizia creando una nuova presentazione e accedendo alla prima diapositiva. Aggiungi il seguente codice per ottenere questo risultato:
```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
// Crea directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Istanziare la classe di presentazione
using (Presentation pres = new Presentation())
{
    // Ottieni la prima diapositiva
    ISlide sld = pres.Slides[0];
```
Questo codice inizializza una nuova presentazione e seleziona la prima diapositiva per un'ulteriore manipolazione.
## Passaggio 2: aggiungi la forma dell'ellisse
 Ora aggiungiamo una forma ellittica alla diapositiva utilizzando il comando`AddAutoShape` metodo:
```csharp
// Aggiungi forma automatica di tipo ellisse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Questa riga di codice crea una forma ellittica alle coordinate (50, 150) con una larghezza di 150 unità e un'altezza di 50 unità.
## Passaggio 3: salva la presentazione
Infine, salva la presentazione modificata su disco con un nome file specificato utilizzando il seguente codice:
```csharp
// Scrivi il file PPTX su disco
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Questo passaggio garantisce che le modifiche vengano mantenute e che sia possibile visualizzare la presentazione risultante con la forma ellittica appena aggiunta.
## Conclusione
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Domande frequenti
### Posso personalizzare ulteriormente la forma dell'ellisse?
Sì, puoi modificare varie proprietà della forma dell'ellisse, come colore, dimensione e posizione, per soddisfare i tuoi requisiti di progettazione specifici.
### Aspose.Slides è compatibile con gli ultimi framework .NET?
Sì, Aspose.Slides viene regolarmente aggiornato per garantire la compatibilità con gli ultimi framework .NET.
### Dove posso trovare altri tutorial ed esempi per Aspose.Slides?
 Visitare il[documentazione](https://reference.aspose.com/slides/net/) per guide ed esempi completi.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Segui il[collegamento della licenza temporanea](https://purchase.aspose.com/temporary-license/) per richiedere una licenza temporanea a scopo di test.
### Hai bisogno di assistenza o hai domande specifiche?
 Visitare il[Forum di supporto di Aspose.Slides](https://forum.aspose.com/c/slides/11) per ottenere aiuto dalla comunità e dagli esperti.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
