---
"date": "2025-04-15"
"description": "Scopri come creare e personalizzare facilmente grafici a ciambella nelle presentazioni di PowerPoint utilizzando Aspose.Slides per .NET. Migliora la tua presentazione visiva dei dati con questa guida completa."
"title": "Come creare un grafico ad anello in PowerPoint utilizzando Aspose.Slides per .NET&#58; una guida passo passo"
"url": "/it/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico ad anello in PowerPoint utilizzando Aspose.Slides per .NET: una guida passo passo

## Introduzione

Arricchire le presentazioni PowerPoint con grafici a ciambella visivamente accattivanti può migliorare significativamente il modo in cui si presentano i dati. Aspose.Slides per .NET offre un modo efficiente per creare e personalizzare questi grafici. Questo tutorial vi guiderà attraverso i passaggi necessari per utilizzare Aspose.Slides per .NET e aggiungere un grafico a ciambella personalizzabile, inclusa la regolazione delle dimensioni dei fori, alle vostre diapositive di PowerPoint.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per .NET
- Passaggi per aggiungere un grafico a ciambella alla diapositiva
- Tecniche per configurare la dimensione del foro del grafico a ciambella
- Applicazioni pratiche e considerazioni sulle prestazioni

Cominciamo a vedere cosa ti serve prima di iniziare!

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti requisiti:

### Librerie e versioni richieste
- Aspose.Slides per .NET (ultima versione)
- Visual Studio o qualsiasi IDE compatibile che supporti lo sviluppo .NET

### Requisiti di configurazione dell'ambiente
- Un ambiente Windows con .NET Framework installato
- Conoscenza di base della programmazione C#

## Impostazione di Aspose.Slides per .NET

Per iniziare, è necessario installare la libreria Aspose.Slides. Ecco come farlo utilizzando diversi metodi:

**Utilizzo della CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Utilizzo della console di Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet:**
Cerca "Aspose.Slides" e installa la versione più recente direttamente tramite l'interfaccia NuGet del tuo IDE.

### Fasi di acquisizione della licenza
1. **Prova gratuita:** Inizia scaricando una versione di prova gratuita per valutarne le funzionalità.
2. **Licenza temporanea:** Se hai bisogno di più tempo, richiedi una licenza temporanea ad Aspose.
3. **Acquistare:** Per un utilizzo a lungo termine, si consiglia di acquistare la versione completa.

Una volta installato, inizializza il tuo progetto con questa configurazione di base:
```csharp
using Aspose.Slides;

// Inizializza un nuovo oggetto Presentazione
Presentation presentation = new Presentation();
```

## Guida all'implementazione

Analizziamo nel dettaglio il processo di creazione di un grafico a ciambella utilizzando Aspose.Slides per .NET in passaggi gestibili.

### Crea un grafico a ciambella

#### Panoramica
Inizieremo aggiungendo un grafico a ciambella alla diapositiva di PowerPoint, impostandone la posizione e le dimensioni.

**Aggiunta del grafico:**
```csharp
using Aspose.Slides.Charts;

// Accedi alla prima diapositiva della presentazione (per impostazione predefinita, ne viene creata una)
ISlide slide = presentation.Slides[0];

// Aggiungere un grafico a ciambella alla diapositiva nella posizione (50, 50) con larghezza e altezza di 400 unità
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parametri:** `ChartType.Doughnut`, posizione x: 50, posizione y: 50, larghezza: 400, altezza: 400.

### Imposta la dimensione del foro

#### Panoramica
Ora configureremo la dimensione del foro del grafico a ciambella per renderlo visivamente accattivante.

**Configurazione della dimensione del foro:**
```csharp
// Imposta la dimensione del foro per il grafico a ciambella al 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Configurazione chiave:** `DoughnutHoleSize` Determina la quantità di centro "tagliata". Un valore compreso tra 0 e 100 rappresenta la percentuale.

### Salva la tua presentazione

Infine, salva le modifiche in un nuovo file PowerPoint:
```csharp
// Definisci il percorso in cui verrà salvata la presentazione
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Salva la presentazione modificata in formato PPTX
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Nota:** Sostituire `YOUR_OUTPUT_DIRECTORY` con la posizione desiderata per il file.

### Suggerimenti per la risoluzione dei problemi

- Assicurarsi che Aspose.Slides sia installato e importato correttamente.
- Prima di salvare la presentazione, verificare che il percorso della directory di output esista.

## Applicazioni pratiche

I grafici ad anello creati con Aspose.Slides per .NET possono essere utilizzati in vari scenari:

1. **Rapporti aziendali:** Illustrare dati finanziari come allocazioni di budget o distribuzioni delle vendite.
2. **Analisi di marketing:** Visualizza le percentuali di quota di mercato tra diversi marchi.
3. **Materiale didattico:** Da utilizzare per spiegare concetti statistici in modo visivamente coinvolgente.

Integra Aspose.Slides con altri sistemi per la generazione e la distribuzione automatizzata di report negli ambienti aziendali.

## Considerazioni sulle prestazioni

Quando si lavora con presentazioni di grandi dimensioni o con numerosi grafici, tenere a mente i seguenti suggerimenti:

- Ottimizzare l'elaborazione dei dati prima di aggiungerli alle diapositive.
- Riutilizzare gli oggetti di presentazione ove possibile per risparmiare memoria.
- Aggiorna regolarmente la tua libreria Aspose.Slides per beneficiare dei miglioramenti delle prestazioni.

## Conclusione

Hai imparato a creare e personalizzare un grafico a ciambella utilizzando Aspose.Slides per .NET. Questo strumento versatile migliora l'aspetto visivo delle tue presentazioni, rendendo i dati più facili da comprendere a colpo d'occhio.

**Prossimi passi:**
Esplora altri tipi di grafici disponibili in Aspose.Slides o approfondisci funzionalità avanzate come le animazioni.

Pronti a provarlo? Andate alla sezione risorse qui sotto e iniziate a sperimentare!

## Sezione FAQ

1. **A cosa serve Aspose.Slides per .NET?**  
   È una libreria per creare, modificare e convertire le presentazioni di PowerPoint a livello di programmazione.

2. **Come posso cambiare il colore degli spicchi di ciambella?**  
   Utilizzo `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` per regolare le proprietà di riempimento.

3. **Posso creare più grafici in una presentazione?**  
   Sì, puoi aggiungere tutti i grafici di cui hai bisogno ripetendo i passaggi per la creazione dei grafici su diapositive o posizioni diverse.

4. **Come posso ottenere la licenza di Aspose.Slides per .NET per uso commerciale?**  
   Per utilizzarlo a fini commerciali, acquista una licenza tramite il sito Web ufficiale di Aspose.

5. **Cosa devo fare se la mia presentazione non viene salvata correttamente?**  
   Controlla i permessi del percorso del file e assicurati che i riferimenti al progetto siano aggiornati.

## Risorse

- [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Scarica Aspose.Slides per .NET](https://releases.aspose.com/slides/net/)
- [Acquista una licenza](https://purchase.aspose.com/buy)
- [Versione di prova gratuita](https://releases.aspose.com/slides/net/)
- [Richiesta di licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}