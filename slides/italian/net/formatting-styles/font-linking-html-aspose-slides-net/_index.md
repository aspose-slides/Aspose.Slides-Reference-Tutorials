---
"date": "2025-04-15"
"description": "Scopri come garantire un rendering coerente dei font durante la conversione di presentazioni in HTML utilizzando Aspose.Slides per .NET incorporando direttamente i font."
"title": "Come collegare i font in HTML usando Aspose.Slides per .NET&#58; una guida passo passo"
"url": "/it/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come collegare i font in HTML utilizzando Aspose.Slides per .NET

## Introduzione

Convertire le presentazioni in HTML mantenendo coerente il rendering dei font sulle diverse piattaforme può rivelarsi una sfida. **Aspose.Slides per .NET** offre una soluzione completa consentendo di collegare tutti i font utilizzati in una presentazione direttamente all'interno dell'output HTML tramite file di font incorporati.

In questo tutorial esploreremo come implementare il collegamento dei font utilizzando Aspose.Slides per .NET e garantire la coerenza del design su diverse piattaforme. 

**Cosa imparerai:**
- Configurazione dell'ambiente con Aspose.Slides per .NET
- Collegamento dei font nella conversione HTML
- Scrittura di controller personalizzati per l'incorporamento dei font
- Applicazioni pratiche e considerazioni sulle prestazioni

Analizziamo nel dettaglio i passaggi necessari per raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

### Librerie e dipendenze richieste
- **Aspose.Slides per .NET** libreria: il componente principale per la nostra implementazione.

### Requisiti di configurazione dell'ambiente
- Un ambiente di sviluppo con installato .NET Framework o .NET Core.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione C#.
- Familiarità con HTML e CSS, in particolare con `@font-face` regola.

## Impostazione di Aspose.Slides per .NET

Per utilizzare Aspose.Slides nel tuo progetto .NET, devi installare la libreria. Ecco diversi metodi:

### Utilizzo di .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Utilizzo della console di Package Manager
```powershell
Install-Package Aspose.Slides
```

### Tramite l'interfaccia utente del gestore pacchetti NuGet
- Apri il progetto in Visual Studio.
- Andare a "Gestore pacchetti NuGet".
- Cerca "Aspose.Slides" e installa la versione più recente.

### Fasi di acquisizione della licenza
È possibile ottenere una licenza di prova gratuita per testare tutte le funzionalità senza limitazioni seguendo questi passaggi:
1. **Prova gratuita**: Scarica una licenza temporanea [Qui](https://releases.aspose.com/slides/net/).
2. **Licenza temporanea**: Richiedi un accesso esteso [Qui](https://purchase.aspose.com/temporary-license/).
3. **Acquistare**: Per la piena funzionalità, acquista una licenza [Qui](https://purchase.aspose.com/buy).

### Inizializzazione e configurazione di base
```csharp
// Crea un'istanza della classe License
easpose.slides.License license = new aspose.slides.License();

// Applicare la licenza dal percorso del file
license.SetLicense("Aspose.Slides.lic");
```

## Guida all'implementazione

Ora, implementiamo il collegamento dei font nella conversione HTML utilizzando **Aspose.Slides per .NET**.

### Panoramica delle funzionalità: collegamento dei font nella conversione HTML
Questa funzionalità garantisce che tutti i font utilizzati in una presentazione siano collegati direttamente al file HTML risultante, incorporando i file dei font. Questo metodo fornisce una soluzione affidabile per mantenere la coerenza del design su diversi browser e piattaforme.

#### Passaggio 1: creare il controller personalizzato
Crea una classe controller personalizzata `LinkAllFontsHtmlController` che eredita da `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Imposta la directory in cui verranno archiviati i file dei font
    }
}
```
#### Passaggio 2: implementare il metodo di scrittura dei font
IL `WriteFont` Il metodo scrive i dati del font in un file e genera il codice HTML corrispondente per l'incorporamento:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Determina il nome del font da utilizzare, preferendo font sostitutivi, se disponibili.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Crea un percorso per il file del font .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Scrive i dati del font nel percorso file specificato.
    File.WriteAllBytes(path, fontData);

    // Genera un blocco di stile HTML incorporando il font utilizzando la regola @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}