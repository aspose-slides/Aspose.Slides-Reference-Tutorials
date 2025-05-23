---
"date": "2025-04-15"
"description": "Scopri come migliorare le tue presentazioni con i grafici a dispersione utilizzando Aspose.Slides per .NET. Segui questa guida completa per creare e personalizzare i grafici in modo efficace."
"title": "Aggiungere grafici a dispersione alle presentazioni utilizzando Aspose.Slides .NET&#58; una guida passo passo"
"url": "/it/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aggiungere grafici a dispersione alle presentazioni utilizzando Aspose.Slides .NET: una guida passo passo

## Introduzione
Desideri migliorare le tue presentazioni integrando i grafici a dispersione senza sforzo? Grazie alla potenza di Aspose.Slides per .NET, creare e personalizzare i grafici diventa un gioco da ragazzi. Questo tutorial ti guiderà nell'aggiunta di grafici a dispersione alle tue diapositive utilizzando Aspose.Slides per .NET. Padroneggiando queste tecniche, presenterai i dati in modo più efficace e creerai presentazioni visivamente accattivanti.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per .NET nel tuo progetto
- Creazione di una nuova presentazione e accesso alla sua prima diapositiva
- Aggiungere grafici a dispersione con linee morbide alle diapositive
- Cancellazione delle serie esistenti e aggiunta di nuove ai grafici
- Modifica dei punti dati e degli stili dei marcatori per una visualizzazione migliorata
- Salvataggio della presentazione in una directory specificata

Cominciamo esaminando i prerequisiti.

## Prerequisiti
Prima di implementare Aspose.Slides per .NET, assicurati di disporre di quanto segue:
- **Aspose.Slides per la libreria .NET**: Versione 23.7 o successiva.
- **Ambiente di sviluppo**: Visual Studio 2019 o versione successiva con .NET Framework 4.6.1+ o .NET Core/5+.
- **Conoscenza di base di C#**: Familiarità con la programmazione orientata agli oggetti in C#.

## Impostazione di Aspose.Slides per .NET
Per iniziare a utilizzare Aspose.Slides, è necessario installare la libreria nel progetto. Ecco come fare:

**Utilizzo della CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Utilizzo della console di Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**Interfaccia utente del gestore pacchetti NuGet:**
- Cerca "Aspose.Slides" e installa la versione più recente.

### Acquisizione della licenza
Puoi iniziare con una prova gratuita o richiedere una licenza temporanea per esplorare tutte le funzionalità. Per acquistarla, segui questi passaggi:
1. Visita [Acquista Aspose.Slides](https://purchase.aspose.com/buy) per acquistare una licenza completa.
2. Per una licenza temporanea, visitare [Pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, aggiungilo al tuo progetto utilizzando:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Guida all'implementazione
Suddivideremo l'implementazione in sezioni logiche in base alle funzionalità.

### Crea presentazione e aggiungi diapositiva
In questa sezione viene illustrato come creare una presentazione e accedere alla sua prima diapositiva.

#### Panoramica
Inizia creando un'istanza di `Presentation` classe, che rappresenta il file PowerPoint. L'accesso alle diapositive è semplice utilizzando questo modello a oggetti.

#### Fasi di implementazione
**Passaggio 1: inizializzare la presentazione**
```csharp
using Aspose.Slides;

// Crea una nuova presentazione
t Presentation pres = new Presentation();
```
Questo codice inizializza un nuovo documento di presentazione.

**Passaggio 2: accedi alla prima diapositiva**
```csharp
// Accedi alla prima diapositiva della presentazione
ISlide slide = pres.Slides[0];
```
Qui, `pres.Slides[0]` accede alla prima diapositiva. 

### Aggiungi grafico a dispersione alla diapositiva
Ora aggiungiamo un grafico a dispersione alla tua presentazione.

#### Panoramica
L'aggiunta di grafici può aiutarti a rappresentare visivamente i dati nelle presentazioni. Aspose.Slides semplifica l'integrazione di vari tipi di grafici, inclusi i grafici a dispersione.

#### Fasi di implementazione
**Passaggio 1: creare e aggiungere un grafico a dispersione**
```csharp
using Aspose.Slides.Charts;

// Crea e aggiungi un grafico a dispersione predefinito con linee morbide
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Questo frammento aggiunge un grafico a dispersione nella posizione e dimensione specificate.

### Cancella e aggiungi serie ai dati del grafico
#### Panoramica
Potrebbe essere necessario personalizzare il grafico cancellando le serie esistenti e aggiungendone di nuove. Questa sezione illustra questa funzionalità.

#### Fasi di implementazione
**Passaggio 1: cartella di lavoro dei dati del grafico di accesso**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Cancella tutte le serie preesistenti
chart.ChartData.Series.Clear();
```
Questo codice cancella i dati esistenti per ripartire da zero con una nuova serie.

**Passaggio 2: aggiungi una nuova serie**
```csharp
// Aggiungi una nuova serie denominata "Serie 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Aggiungi un'altra serie denominata "Serie 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Questi passaggi aggiungono due nuove serie al grafico.

### Modifica i punti dati della prima serie e lo stile del marcatore
#### Panoramica
Personalizza i punti dati e gli stili dei marcatori per una migliore visualizzazione dei tuoi grafici a dispersione.

#### Fasi di implementazione
**Passaggio 1: accesso e aggiunta di punti dati**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Aggiungi i punti dati (1, 3) e (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Passaggio 2: modifica lo stile del marcatore**
```csharp
// Cambia il tipo di serie e modifica lo stile del marcatore
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Modifica i punti dati della seconda serie e lo stile del marcatore
#### Panoramica
Allo stesso modo, personalizza la seconda serie in base alle tue esigenze di presentazione.

#### Fasi di implementazione
**Passaggio 1: accesso e aggiunta di più punti dati**
```csharp
// Accedi alla seconda serie di grafici
series = chart.ChartData.Series[1];

// Aggiungi più punti dati
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Passaggio 2: modifica lo stile del marcatore**
```csharp
// Cambia la dimensione del marcatore e il simbolo per la seconda serie
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Salva presentazione
Infine, salva la presentazione nella directory specificata.

#### Fasi di implementazione
**Passaggio 1: definire la directory**
Assicurati che la directory di output esista. In caso contrario, creala:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Salva la presentazione
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Questo codice salva il file della presentazione in una posizione specificata.

## Conclusione
Hai aggiunto correttamente i grafici a dispersione alle tue presentazioni utilizzando Aspose.Slides per .NET. Continua a esplorare le funzionalità e le personalizzazioni aggiuntive disponibili nella libreria per migliorare le tue competenze di visualizzazione dei dati.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}