---
"description": "Scopri come nascondere le forme nelle diapositive di PowerPoint utilizzando Aspose.Slides per .NET. Personalizza le presentazioni programmaticamente con questa guida passo passo."
"linktitle": "Nascondere le forme nelle diapositive della presentazione con Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Tutorial su come nascondere le forme in PowerPoint con Aspose.Slides .NET"
"url": "/it/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial su come nascondere le forme in PowerPoint con Aspose.Slides .NET

## Introduzione
Nel dinamico mondo delle presentazioni, la personalizzazione è fondamentale. Aspose.Slides per .NET offre una soluzione potente per la gestione programmatica delle presentazioni PowerPoint. Un requisito comune è la possibilità di nascondere forme specifiche all'interno di una diapositiva. Questo tutorial vi guiderà attraverso il processo di occultamento delle forme nelle diapositive di una presentazione utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides. Puoi scaricarla. [Qui](https://releases.aspose.com/slides/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo preferito per .NET.
- Conoscenza di base di C#: familiarizzare con C# poiché gli esempi di codice forniti sono in questo linguaggio.
## Importa spazi dei nomi
Per iniziare a lavorare con Aspose.Slides, importa gli spazi dei nomi necessari nel tuo progetto C#. Questo ti garantirà l'accesso alle classi e ai metodi richiesti.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Ora, scomponiamo il codice di esempio in più passaggi per una comprensione chiara e concisa.
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto C# e assicurati di includere la libreria Aspose.Slides.
## Passaggio 2: creare una presentazione
Istanziare il `Presentation` classe, che rappresenta il file PowerPoint. Aggiungi una diapositiva e ottieni un riferimento ad essa.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Passaggio 3: aggiungere forme alla diapositiva
Aggiungere forme automatiche alla diapositiva, come rettangoli e lune, con dimensioni specifiche.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Passaggio 4: nascondere le forme in base al testo alternativo
Specifica un testo alternativo e nascondi le forme che corrispondono a questo testo.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Passaggio 5: Salva la presentazione
Salvare la presentazione modificata sul disco in formato PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusione
Congratulazioni! Hai nascosto con successo le forme nella tua presentazione utilizzando Aspose.Slides per .NET. Questo apre un mondo di possibilità per la creazione di diapositive dinamiche e personalizzate tramite codice.
---
## Domande frequenti
### Aspose.Slides è compatibile con .NET Core?
Sì, Aspose.Slides supporta .NET Core, garantendo flessibilità nel tuo ambiente di sviluppo.
### Posso nascondere le forme in base a condizioni diverse dal testo alternativo?
Assolutamente! Puoi personalizzare la logica di occultamento in base a vari attributi come tipo di forma, colore o posizione.
### Dove posso trovare ulteriore documentazione su Aspose.Slides?
Esplora la documentazione [Qui](https://reference.aspose.com/slides/net/) per informazioni approfondite ed esempi.
### Sono disponibili licenze temporanee per Aspose.Slides?
Sì, puoi ottenere una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/) a scopo di test.
### Come posso ottenere il supporto della community per Aspose.Slides?
Unisciti alla community Aspose.Slides su [foro](https://forum.aspose.com/c/slides/11) per discussioni e assistenza.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}