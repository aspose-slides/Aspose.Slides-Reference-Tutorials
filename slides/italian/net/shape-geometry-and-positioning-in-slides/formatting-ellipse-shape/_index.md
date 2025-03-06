---
title: Esercitazione sulla formattazione delle forme ellittiche con Aspose.Slides per .NET
linktitle: Formattazione della forma ellittica nelle diapositive con Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Crea straordinarie forme ellittiche in PowerPoint utilizzando Aspose.Slides per .NET. Segui la nostra guida passo passo per presentazioni professionali.
weight: 11
url: /it/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Migliorare le tue presentazioni PowerPoint con forme visivamente accattivanti è fondamentale per affascinare il tuo pubblico. Una di queste forme è l'ellisse, che può aggiungere un tocco di eleganza e professionalità alle tue diapositive. In questo tutorial ti guideremo attraverso il processo di formattazione delle forme ellittiche in PowerPoint utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato sul tuo computer.
-  Aspose.Slides per la libreria .NET, da cui è possibile scaricare[Qui](https://releases.aspose.com/slides/net/).
- Assicurati di disporre delle autorizzazioni necessarie per creare e salvare file sul tuo sistema.
## Importa spazi dei nomi
Per iniziare, devi importare gli spazi dei nomi richiesti nel tuo progetto C#. Ciò garantisce l'accesso alle classi e ai metodi necessari per lavorare con Aspose.Slides.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
Ora, suddividiamo l'esempio in più passaggi per una guida completa sulla formattazione delle forme ellittiche in PowerPoint utilizzando Aspose.Slides per .NET.
## Passaggio 1: imposta il tuo progetto
 Crea un nuovo progetto C# in Visual Studio e aggiungi un riferimento alla libreria Aspose.Slides. Se non l'hai ancora scaricato, puoi trovare il link per il download[Qui](https://releases.aspose.com/slides/net/).
## Passaggio 2: definire la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assicurarsi che la directory specificata esista o crearla in caso contrario.
## Passaggio 3: istanziare la lezione di presentazione
```csharp
using (Presentation pres = new Presentation())
{
    // Il tuo codice per la formattazione della forma ellittica va qui
}
```
 Crea un'istanza di`Presentation` classe, che rappresenta il file PowerPoint.
## Passaggio 4: ottieni la prima diapositiva
```csharp
ISlide sld = pres.Slides[0];
```
Accedi alla prima diapositiva della tua presentazione.
## Passaggio 5: aggiungi la forma automatica dell'ellisse
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Inserisci una forma ellittica sulla diapositiva, specificandone la posizione e le dimensioni.
## Passaggio 6: formattare la forma dell'ellisse
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
Applicare la formattazione alla forma dell'ellisse, impostando il colore di riempimento e le proprietà della linea.
## Passaggio 7: salva la presentazione
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
Salva la presentazione modificata su disco.
Segui questi passaggi meticolosamente e avrai una forma ellittica splendidamente formattata nella tua presentazione PowerPoint.
## Conclusione
Incorporare forme visivamente accattivanti, come le ellissi, può migliorare significativamente il fascino estetico delle tue presentazioni PowerPoint. Aspose.Slides per .NET rende questo processo fluido, consentendoti di creare diapositive dall'aspetto professionale senza sforzo.

## Domande frequenti
### Aspose.Slides è compatibile con le ultime versioni di PowerPoint?
Aspose.Slides garantisce la compatibilità con varie versioni di PowerPoint, comprese quelle più recenti. Fare riferimento al[documentazione](https://reference.aspose.com/slides/net/) per dettagli specifici.
### Posso scaricare una versione di prova gratuita di Aspose.Slides per .NET?
 Sì, puoi esplorare una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Visita[questo link](https://purchase.aspose.com/temporary-license/) acquisire una licenza temporanea.
### Dove posso trovare supporto per le query relative ad Aspose.Slides?
 Chiedi assistenza alla comunità presso il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Esiste un'opzione di acquisto diretto per Aspose.Slides per .NET?
 Sì, puoi acquistare direttamente la libreria[Qui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
