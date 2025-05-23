---
"date": "2025-04-16"
"description": "Scopri come aggiungere in modo efficiente segnaposto per contenuti, testo verticale, grafici e tabelle alle diapositive di PowerPoint utilizzando Aspose.Slides per .NET."
"title": "Come aggiungere segnaposto nelle diapositive .NET utilizzando Aspose.Slides"
"url": "/it/net/shapes-text-frames/add-placeholders-in-dotnet-slides-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere segnaposto nelle diapositive .NET con Aspose.Slides

## Introduzione

Stai cercando un modo efficiente per automatizzare l'aggiunta di segnaposto come contenuto, testo verticale, grafici e tabelle alle tue presentazioni? Con Aspose.Slides per .NET, questo processo diventa semplice. Questo tutorial ti guiderà nell'utilizzo di Aspose.Slides per semplificare l'aggiunta di segnaposto nelle diapositive di PowerPoint in un ambiente .NET.

In questa guida completa esploreremo:
- Impostazione di Aspose.Slides per .NET
- Istruzioni passo passo per aggiungere vari segnaposto
- Applicazioni pratiche di queste funzionalità
- Considerazioni sulle prestazioni per un utilizzo ottimale

## Prerequisiti

### Librerie e versioni richieste
Per seguire questo tutorial, assicurati di avere:
- Aspose.Slides per la libreria .NET versione 22.x o successiva.
- Un ambiente .NET compatibile (ad esempio, .NET Core 3.1 o successivo).

### Requisiti di configurazione dell'ambiente
Assicurati che il tuo ambiente di sviluppo sia configurato con Visual Studio o un altro IDE che supporti i progetti .NET.

### Prerequisiti di conoscenza
Una conoscenza di base del linguaggio C# e la familiarità con i concetti di programmazione .NET saranno utili ma non necessarie, poiché affronteremo tutti gli aspetti fondamentali durante il corso.

## Impostazione di Aspose.Slides per .NET
Per iniziare a utilizzare Aspose.Slides nel tuo progetto, devi installarlo. Ecco come fare:

**Utilizzo della CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Utilizzo della console di Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet:**
Cerca "Aspose.Slides" e installa la versione più recente.

### Acquisizione della licenza
Per provare Aspose.Slides, puoi optare per una prova gratuita o acquistare una licenza temporanea. Per l'uso in produzione, valuta l'acquisto di una licenza completa. Visita [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per saperne di più sulle opzioni di licenza.

#### Inizializzazione di base
Inizializza il tuo progetto creando un'istanza di `Presentation` classe:
```csharp
using Aspose.Slides;
// ...
var presentation = new Presentation();
```

## Guida all'implementazione

### Aggiungi segnaposto di contenuto
L'aggiunta di un segnaposto di contenuto consente di inserire testo, immagini e altri contenuti multimediali nelle diapositive. Ecco come farlo utilizzando Aspose.Slides per .NET.

#### Panoramica
Questa sezione ti guiderà attraverso il processo di aggiunta di un segnaposto di contenuto su un layout di diapositiva vuoto utilizzando Aspose.Slides per .NET.

#### Fasi di implementazione
**1. Imposta il tuo progetto**
Per prima cosa, creiamo un nuovo progetto C# e installiamo la libreria Aspose.Slides come accennato in precedenza.

**2. Inizializza la presentazione**
Crea un'istanza di `Presentation` per lavorare con le diapositive:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "content_placeholder.pptx");

using (var pres = new Presentation())
{
    // Il codice verrà aggiunto qui.
}
```
**3. Accedi alla diapositiva del layout**
Recupera la diapositiva con layout vuoto in cui aggiungerai il tuo segnaposto:
```csharp
// Ottenere la diapositiva con layout vuoto.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
Questo passaggio consente di accedere a un layout vuoto predefinito, ideale per progetti personalizzati.

**4. Aggiungi segnaposto di contenuto**
Utilizzare il `PlaceholderManager` per inserire un segnaposto di contenuto con coordinate e dimensioni specificate:
```csharp
// Ottenere il gestore segnaposto della diapositiva di layout.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Aggiunta di un segnaposto di contenuto nella posizione (10, 10) con dimensione (300x200).
placeholderManager.AddContentPlaceholder(10, 10, 300, 200);
```
I parametri definiscono la posizione `(x, y)` e dimensioni `(width x height)` del segnaposto.

**5. Salva la presentazione**
Infine, salva il file della presentazione:
```csharp
// Salvataggio della presentazione con segnaposto di contenuto aggiunto.
pres.Save(outFilePath, SaveFormat.Pptx);
```
In questo modo il layout modificato viene salvato in una directory specificata.

### Aggiungi segnaposto di testo verticale
I segnaposto di testo verticali sono perfetti per le barre laterali o per elementi di design unici che richiedono modifiche all'orientamento del testo.

#### Panoramica
In questa sezione imparerai come aggiungere un segnaposto di testo verticale per migliorare l'estetica della tua diapositiva.

#### Fasi di implementazione
**1. Inizializza la presentazione**
Crea una nuova istanza di `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "vertical_text_placeholder.pptx");

using (var pres = new Presentation())
{
    // Il codice verrà aggiunto qui.
}
```
**2. Accedi alla diapositiva del layout**
Recupera la diapositiva con layout vuoto:
```csharp
// Ottenere la diapositiva con layout vuoto.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Aggiungi segnaposto di testo verticale**
Aggiungi un segnaposto di testo verticale utilizzando `PlaceholderManager`:
```csharp
// Ottenere il gestore segnaposto della diapositiva di layout.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Aggiunta di un segnaposto di testo verticale nella posizione (350, 10) con dimensione (200x300).
placeholderManager.AddVerticalTextPlaceholder(350, 10, 200, 300);
```
**4. Salva la presentazione**
Salva la tua presentazione:
```csharp
// Salvataggio della presentazione con l'aggiunta del segnaposto di testo verticale.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Aggiungi segnaposto grafico
I grafici sono fondamentali per la rappresentazione dei dati nelle presentazioni. Ecco come aggiungere un segnaposto per grafici utilizzando Aspose.Slides.

#### Panoramica
Questa sezione ti aiuterà a integrare un segnaposto per grafico nelle diapositive di PowerPoint utilizzando Aspose.Slides.

#### Fasi di implementazione
**1. Inizializza la presentazione**
Crea un'istanza di `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "chart_placeholder.pptx");

using (var pres = new Presentation())
{
    // Il codice verrà aggiunto qui.
}
```
**2. Accedi alla diapositiva del layout**
Recupera la diapositiva con layout vuoto:
```csharp
// Ottenere la diapositiva con layout vuoto.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Aggiungi segnaposto grafico**
Utilizzo `PlaceholderManager` per aggiungere un segnaposto al grafico:
```csharp
// Ottenere il gestore segnaposto della diapositiva di layout.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Aggiunta di un segnaposto del grafico nella posizione (10, 350) con dimensione (300x300).
placeholderManager.AddChartPlaceholder(10, 350, 300, 300);
```
**4. Salva la presentazione**
Salva la tua presentazione:
```csharp
// Salvataggio della presentazione con segnaposto grafico aggiunto.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Aggiungi segnaposto tabella
Le tabelle organizzano i dati in modo efficace e vengono spesso utilizzate nelle presentazioni per motivi di chiarezza.

#### Panoramica
Impara ad aggiungere un segnaposto di tabella per strutturare ordinatamente le informazioni nelle tue diapositive utilizzando Aspose.Slides.

#### Fasi di implementazione
**1. Inizializza la presentazione**
Crea un'istanza di `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "table_placeholder.pptx");

using (var pres = new Presentation())
{
    // Il codice verrà aggiunto qui.
}
```
**2. Accedi alla diapositiva del layout**
Recupera la diapositiva con layout vuoto:
```csharp
// Ottenere la diapositiva con layout vuoto.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Aggiungi segnaposto tabella**
Utilizzo `PlaceholderManager` per aggiungere un segnaposto alla tabella:
```csharp
// Ottenere il gestore segnaposto della diapositiva di layout.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Aggiunta di un segnaposto per la tabella nella posizione (350, 350) con dimensione (300x200).
placeholderManager.AddTablePlaceholder(350, 350, 300, 200);
```
**4. Salva la presentazione**
Salva la tua presentazione:
```csharp
// Salvataggio della presentazione con aggiunta del segnaposto della tabella.
pres.Save(outFilePath, SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}