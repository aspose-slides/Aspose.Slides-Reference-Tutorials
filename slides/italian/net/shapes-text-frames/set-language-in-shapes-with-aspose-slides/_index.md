---
"date": "2025-04-16"
"description": "Scopri come impostare gli attributi di lingua per il testo all'interno delle forme utilizzando Aspose.Slides per .NET. Questa guida illustra come aggiungere forme automatiche, impostare gli ID di lingua e salvare le presentazioni."
"title": "Come impostare la lingua nelle forme di PowerPoint utilizzando Aspose.Slides per .NET"
"url": "/it/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare la lingua nelle forme di PowerPoint utilizzando Aspose.Slides per .NET

Nel mondo delle presentazioni digitali, garantire che i contenuti siano accessibili e formattati correttamente in diverse lingue può essere una sfida. Con Aspose.Slides per .NET, è possibile impostare facilmente gli attributi di lingua per il testo all'interno delle forme nelle diapositive di PowerPoint. Questa funzionalità è particolarmente utile per la preparazione di documenti multilingue o per garantire la coerenza nelle comunicazioni globali.

**Cosa imparerai:**
- Aggiungere forme automatiche e inserire testo in esse.
- Impostazione dell'ID lingua per le parti di testo tramite Aspose.Slides.
- Salvataggio di presentazioni con configurazioni personalizzate.

Vediamo insieme come implementare questa funzionalità in modo semplice.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- **Librerie e dipendenze**: È necessario avere installato Aspose.Slides per .NET. Questa libreria è essenziale per la gestione delle presentazioni PowerPoint in C#.
  
- **Configurazione dell'ambiente**: È richiesto un ambiente di sviluppo con .NET Core o .NET Framework.

- **Prerequisiti di conoscenza**:Sarà utile avere familiarità con i concetti base della programmazione C# e comprendere i principi della programmazione orientata agli oggetti.

## Impostazione di Aspose.Slides per .NET

Per iniziare, è necessario installare la libreria Aspose.Slides. È possibile farlo utilizzando uno dei seguenti metodi:

**Interfaccia a riga di comando .NET**
```shell
dotnet add package Aspose.Slides
```

**Gestore dei pacchetti**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet**
Cerca "Aspose.Slides" e installa la versione più recente.

### Acquisizione della licenza

Puoi iniziare con una prova gratuita scaricando una licenza temporanea da [Qui](https://purchase.aspose.com/temporary-license/)Per un utilizzo continuativo, si consiglia di acquistare una licenza tramite [questo collegamento](https://purchase.aspose.com/buy).

Una volta pronta la configurazione, inizializza Aspose.Slides nel tuo progetto:

```csharp
using Aspose.Slides;
```

## Guida all'implementazione

Ora che abbiamo impostato tutto, implementiamo la funzionalità per impostare la lingua per il testo delle forme.

### Panoramica delle funzionalità: impostazione della lingua del testo della forma

Questa funzionalità consente di specificare la lingua del testo all'interno di una forma di PowerPoint. Impostando l'ID lingua, si garantisce che il controllo ortografico e altre funzionalità specifiche della lingua vengano applicati correttamente.

#### Passaggio 1: inizializzare la presentazione

Inizia creando un'istanza di `Presentation` classe.

```csharp
using (Presentation pres = new Presentation())
{
    // Il tuo codice qui
}
```

Questo inizializza un nuovo oggetto di presentazione PowerPoint che manipoleremo.

#### Passaggio 2: aggiungi forma automatica e cornice di testo

Aggiungi una forma rettangolare alla diapositiva e inserisci del testo al suo interno:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Qui, `AddAutoShape` Aggiunge un rettangolo alla prima diapositiva. I parametri ne definiscono posizione e dimensioni.

#### Passaggio 3: imposta l'ID della lingua

Imposta la lingua per la porzione di testo all'interno della forma:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

In questo modo l'inglese (Regno Unito) viene assegnato come lingua per il controllo ortografico.

#### Passaggio 4: salva la presentazione

Infine, salva la presentazione in un percorso specificato:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}