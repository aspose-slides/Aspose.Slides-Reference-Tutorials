---
"date": "2025-04-15"
"description": "Scopri come aggiungere grafici a torta alle tue presentazioni in modo programmatico con Aspose.Slides per .NET, migliorando la visualizzazione dei dati senza sforzo."
"title": "Crea un grafico a torta in PowerPoint utilizzando Aspose.Slides per .NET"
"url": "/it/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e aggiungere un grafico a torta a una presentazione utilizzando Aspose.Slides per .NET
## Introduzione
Creare presentazioni accattivanti spesso non richiede solo testo; elementi visivi come i grafici possono migliorare significativamente l'impatto della narrazione dei dati. Se desideri aggiungere grafici a torta dinamici alle tue presentazioni PowerPoint tramite programmazione, **Aspose.Slides per .NET** è uno strumento potente che rende questo compito semplice ed efficiente. Questo tutorial ti guiderà nell'aggiunta di un grafico a torta a una diapositiva di una presentazione e nella sua configurazione con fonti dati esterne.

### Cosa imparerai
- Come creare una nuova presentazione utilizzando Aspose.Slides per .NET
- Aggiungere un grafico a torta alla prima diapositiva
- Impostazione di un URL di una cartella di lavoro esterna come origine dati per il grafico
- Salvataggio della presentazione in formato PPTX
Cominciamo a vedere come raggiungere questo obiettivo con facilità, partendo dai prerequisiti.
## Prerequisiti
Prima di iniziare, assicurati di avere pronto quanto segue:
- **Aspose.Slides per .NET** libreria installata. È necessaria una versione compatibile con .NET Framework o .NET Core/.NET 5+.
- Conoscenza di base della programmazione C# e familiarità con Visual Studio IDE.
- Un ambiente di sviluppo configurato sul tuo computer (Windows, macOS o Linux).
## Impostazione di Aspose.Slides per .NET
### Istruzioni per l'installazione
Aspose.Slides per .NET può essere aggiunto al tuo progetto utilizzando vari metodi:
**Interfaccia a riga di comando .NET**
```shell
dotnet add package Aspose.Slides
```
**Console del gestore dei pacchetti**
```powershell
Install-Package Aspose.Slides
```
**Interfaccia utente del gestore pacchetti NuGet**
1. Aprire Gestione pacchetti NuGet in Visual Studio.
2. Cerca "Aspose.Slides".
3. Installa la versione più recente.
### Acquisizione della licenza
Per utilizzare Aspose.Slides, puoi iniziare con una licenza di prova gratuita per esplorarne le funzionalità senza limitazioni. Per gli ambienti di produzione, valuta l'acquisto di una licenza commerciale o di una licenza temporanea per test più lunghi. Visita [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per maggiori dettagli.
### Inizializzazione di base
Per utilizzare Aspose.Slides nel tuo progetto, devi inizializzarlo con la tua licenza, se disponibile:
```csharp
// Inizializzare la libreria
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Guida all'implementazione
Ora che hai impostato tutto, esaminiamo passo dopo passo ogni funzionalità.
### Creare e aggiungere un grafico alla presentazione
#### Panoramica
Inizieremo creando una presentazione e aggiungendo un grafico a torta alla prima diapositiva.
#### Passaggi:
1. **Inizializza la presentazione**
   Inizia creando un'istanza di `Presentation` classe, che rappresenta il file PowerPoint.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Qui aggiungeremo il nostro grafico.
   }
   ```
2. **Aggiungi un grafico a torta**
   Utilizzare il `Shapes.AddChart` Metodo per inserire un grafico a torta in corrispondenza di coordinate specifiche sulla diapositiva.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Imposta cartella di lavoro esterna per i dati del grafico
#### Panoramica
Ora configuriamo il grafico a torta per utilizzare i dati da una cartella di lavoro esterna.
#### Passaggi:
1. **Dati del grafico di accesso**
   Recupera l'interfaccia dei dati del grafico in cui specificherai l'URL della fonte dati esterna.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Imposta URL cartella di lavoro esterna**
   Imposta l'URL per la tua origine dati utilizzando `SetExternalWorkbook`In questo esempio viene utilizzato un URL segnaposto, che deve essere sostituito con il percorso effettivo della sorgente dati.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://percorso/non/esiste", false);
   ```
### Salva la presentazione nel file
#### Panoramica
Infine, salva la presentazione in formato PPTX nella posizione desiderata.
#### Passaggi:
1. **Salva la presentazione**
   Utilizzare il `Save` metodo del `Presentation` classe per scrivere il file sul disco.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Applicazioni pratiche
- **Rapporti aziendali**: Genera automaticamente grafici per le revisioni trimestrali delle prestazioni.
- **Dashboard dei dati**: Integrazione con fonti dati per aggiornare report visivi in tempo reale.
- **Contenuto educativo**: Crea presentazioni dinamiche che estraggano i dati più recenti da studi esterni o documenti di ricerca.
Integrando Aspose.Slides puoi automatizzare e migliorare il processo di creazione delle tue presentazioni in vari ambiti.
## Considerazioni sulle prestazioni
Quando si lavora con grandi set di dati o numerosi grafici:
- Ottimizza l'utilizzo delle risorse gestendo efficacemente la memoria in .NET.
- Smaltire `Presentation` oggetti in modo corretto per liberare risorse.
- Ove possibile, utilizzare operazioni asincrone per migliorare la reattività dell'applicazione.
## Conclusione
Seguendo questo tutorial, hai imparato a creare presentazioni con grafici a torta in modo programmatico utilizzando Aspose.Slides per .NET. Ora hai gli strumenti per automatizzare la creazione di grafici e gestire in modo efficiente le fonti dati esterne.
### Prossimi passi
Esplora ulteriormente personalizzando gli stili dei grafici, aggiungendo altri tipi di grafici o integrando altri componenti Aspose come Aspose.Cells per funzionalità avanzate di manipolazione dei dati.
## Sezione FAQ
1. **Che cos'è Aspose.Slides?**  
   Una libreria robusta per la manipolazione programmatica delle presentazioni PowerPoint in .NET.
2. **Posso usare Aspose.Slides senza licenza?**  
   Sì, ma con delle limitazioni. Valuta la possibilità di ottenere una prova gratuita o di acquistare una licenza per usufruire di tutte le funzionalità.
3. **Come posso aggiornare dinamicamente i dati del grafico?**  
   Utilizzare cartelle di lavoro esterne e impostare i relativi URL in `SetExternalWorkbook` metodo.
4. **Aspose.Slides può essere utilizzato su più piattaforme?**  
   Sì, supporta .NET Framework e .NET Core/.NET 5+ su Windows, macOS e Linux.
5. **Quali altri tipi di grafici sono supportati?**  
   Oltre ai grafici a torta, con Aspose.Slides puoi creare grafici a barre, grafici a linee e altro ancora.
## Risorse
- [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Scarica l'ultima versione](https://releases.aspose.com/slides/net/)
- [Acquista licenza](https://purchase.aspose.com/buy)
- [Prova gratuita](https://releases.aspose.com/slides/net/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto](https://forum.aspose.com/c/slides/11)
Inizia subito a integrare Aspose.Slides nei tuoi progetti per migliorare e automatizzare le tue presentazioni PowerPoint!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}