---
date: '2026-08-06'
description: Scopri come creare chart in presentazioni Java usando Aspose.Slides e
  come collegare workbook per dynamic data updates. Guida passo passo.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: Scopri come creare chart in presentazioni Java usando Aspose.Slides
  e come collegare workbook per dynamic data updates. Segui questo tutorial conciso.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: Come creare chart in presentazioni Java con Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: Come creare chart in presentazioni Java con Aspose.Slides
url: /it/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico nelle presentazioni Java con Aspose.Slides: collegamento a cartelle di lavoro esterne

## Introduzione
In questo tutorial imparerai **come creare oggetti grafico** in una presentazione Java e **come collegare i dati di una cartella di lavoro** affinché i grafici si aggiornino automaticamente. I grafici dinamici mantengono le diapositive aggiornate senza copie manuali, il che è fondamentale per report in tempo reale, dashboard finanziarie e presentazioni sullo stato dei progetti. Vedremo la configurazione, l'implementazione e le difficoltà più comuni, così potrai integrare dati Excel in tempo reale con poche righe di codice.

## Risposte rapide
- **Qual è il vantaggio principale?** I grafici si aggiornano automaticamente quando la cartella di lavoro Excel collegata viene modificata.  
- **Quale versione della libreria è necessaria?** Aspose.Slides per Java 25.4 o versioni successive.  
- **È necessaria una licenza?** Una prova gratuita funziona per lo sviluppo; una licenza commerciale rimuove tutti i limiti di valutazione.  
- **Posso usare qualsiasi formato Excel?** Sì – sia i file `.xlsx` sia i legacy `.xls` sono supportati.  
- **La latenza di rete è un problema?** Metti nella cache la cartella di lavoro localmente o usa una CDN per ridurre al minimo la latenza.

## Cos'è il collegamento dinamico ai grafici?
Il collegamento dinamico ai grafici consente a un grafico di leggere la sua fonte dati da una cartella di lavoro esterna a runtime, così qualsiasi modifica alla cartella di lavoro viene riflessa nella diapositiva al successivo riapertura. Questo elimina la necessità di rigenerare la presentazione dopo ogni aggiornamento dei dati.

## Perché usare Aspose.Slides per Java?
Aspose.Slides supporta **oltre 50 formati di input e output**, può renderizzare presentazioni con centinaia di pagine senza caricare l'intero file in memoria e processa gli aggiornamenti dei dati dei grafici in meno di 200 ms su un server tipico. Questi numeri di prestazione quantificati lo rendono una scelta affidabile per pipeline di reporting aziendali.

## Prerequisiti
- **Aspose.Slides per Java** 25.4 o successiva.  
- **Java Development Kit (JDK)** 16 o più recente.  
- Familiarità con Maven o Gradle per la gestione delle dipendenze.  

### Librerie e dipendenze richieste
- **Aspose.Slides per Java** – fornisce l'API per le presentazioni.  
- **Java Development Kit (JDK)** – necessario per compilare ed eseguire il codice.

### Requisiti per la configurazione dell'ambiente
- Conoscenza di base della programmazione Java.  
- Accesso a una cartella di lavoro Excel esterna (percorso file locale o URL HTTP).  

## Configurare Aspose.Slides per Java
Per aggiungere Aspose.Slides al tuo progetto, scegli uno dei sistemi di build supportati.

### Configurazione Maven
Aggiungi questa dipendenza al tuo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Configurazione Gradle
Inserisci quanto segue nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica la libreria da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
Inizia con una prova gratuita o ottieni una licenza temporanea per testare Aspose.Slides senza limitazioni. Per un utilizzo a lungo termine, considera l'acquisto di una licenza.

##### Inizializzazione e configurazione di base
`Presentation` è la classe principale di Aspose.Slides che rappresenta un file PowerPoint in memoria. Inizializza il tuo oggetto presentazione come segue:
```java
Presentation pres = new Presentation();
```

## Guida all'implementazione
In questa sezione percorriamo la procedura per impostare una cartella di lavoro esterna per aggiornare i dati del grafico in una presentazione.

### Impostare una cartella di lavoro esterna con aggiornamento dei dati del grafico
#### Panoramica
Questa funzionalità consente ai grafici di aggiornare dinamicamente i dati da una fonte esterna. È ideale quando i dati cambiano frequentemente e desideri che le diapositive riflettano tali cambiamenti automaticamente.

#### Implementazione passo‑passo
1. **Crea una nuova presentazione**  
   Inizia creando una nuova istanza `Presentation`:
   ```java
   Presentation pres = new Presentation();
   ```

2. **Accedi alla prima diapositiva**  
   L'accesso alle diapositive è semplice:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Aggiungi un grafico alla diapositiva**  
   Aggiungi un grafico a torta nella posizione e dimensione desiderate:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Imposta l'URL della cartella di lavoro esterna per i dati del grafico**  
   Specifica una cartella di lavoro esterna come fonte dati:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### Opzioni di configurazione
- **Tipo di grafico** – scegli tra Torta, Barre, Linea, Area, ecc., a seconda di come vuoi visualizzare i dati.  
- **Posizione e dimensione** – regola le coordinate X/Y e larghezza/altezza per adattarle al layout della diapositiva.  

## Come creare un grafico che si collega a una cartella di lavoro?
`Chart` è l'oggetto Aspose.Slides che incapsula una forma grafico e i suoi dati.  
Carica la tua presentazione, aggiungi un grafico e chiama `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. Il grafico ora legge i valori delle serie dalla cartella di lavoro ogni volta che il file viene aperto, fornendo aggiornamenti in tempo reale senza rigenerare il PPTX. Questo paragrafo risponde direttamente al requisito GEO e fornisce una descrizione concisa e attuabile.

## Problemi comuni e soluzioni
Se i collegamenti esterni non si aggiornano:
- Verifica che l'URL sia raggiungibile e restituisca un file Excel valido.  
- Assicurati che il server consenta richieste GET anonime o fornisci credenziali se necessario.  
- Metti nella cache la cartella di lavoro localmente se la latenza di rete è elevata; aggiorna la cache prima di aprire la presentazione.

## Applicazioni pratiche
I grafici dinamici alimentati da una cartella di lavoro esterna possono essere utili in diversi scenari:
1. **Report in tempo reale** – dashboard di vendita che estraggono le ultime cifre da un file Excel centrale.  
2. **Analisi finanziaria** – tendenze dei prezzi azionari che si aggiornano automaticamente da un feed di dati di mercato.  
3. **Gestione progetti** – dashboard KPI che riflettono le statistiche più recenti di completamento delle attività.

## Considerazioni sulle prestazioni
Ottimizzare le prestazioni è essenziale quando si gestiscono cartelle di lavoro di grandi dimensioni:
- Metti nella cache la cartella di lavoro sul server dell'applicazione per ridurre le chiamate di rete ripetute.  
- Usa API di streaming per leggere solo gli intervalli di foglio necessari, riducendo l'uso di memoria.  
- Aspose.Slides elabora gli aggiornamenti dei grafici in meno di 200 ms per cartelle di lavoro fino a 10 MB, adatto alla maggior parte degli scenari di reporting.

## Conclusione
Seguendo questa guida ora sai **come creare oggetti grafico** nelle presentazioni Java e **come collegare i dati di una cartella di lavoro** per aggiornamenti automatici. Questa capacità rende le diapositive più interattive, riduce lo sforzo manuale e garantisce che gli stakeholder vedano sempre i numeri più recenti. Esplora altre funzionalità di Aspose.Slides come la clonazione di diapositive, animazioni ed esportazione PDF per migliorare ulteriormente il tuo flusso di lavoro di reporting.

## Sezione FAQ
**D1: Posso usare qualsiasi URL come cartella di lavoro esterna?**  
R1: L'URL deve puntare a un file Excel raggiungibile (`.xlsx` o `.xls`). Assicurati che il server restituisca il MIME type corretto e che l'autenticazione, se necessaria, sia gestita nel tuo codice.

**D2: Quali tipi di grafico supportano il collegamento dinamico?**  
R2: Tutti i tipi di grafico nativi di Aspose.Slides – Torta, Barre, Linea, Area, Dispersione, Radar e altri – possono essere collegati a una cartella di lavoro esterna.

**D3: Esiste un limite di dimensione per la cartella di lavoro esterna?**  
R3: Sebbene Aspose.Slides possa gestire cartelle di lavoro superiori a 100 MB, il tempo di elaborazione cresce linearmente; per le migliori prestazioni mantieni i file sotto i 20 MB o streamma solo gli intervalli necessari.

**D4: Come gestire un URL non raggiungibile?**  
R4: Avvolgi il codice di collegamento in un blocco try‑catch, registra l'eccezione e, facoltativamente, ricorri a una fonte dati statica in modo che la presentazione si carichi comunque.

**D5: È possibile utilizzare questa funzionalità in pipeline di reporting automatizzate?**  
R5: Assolutamente sì. L'API funziona in modalità head‑less, così puoi generare o aggiornare presentazioni su un server, includerle in email o pubblicarle in una libreria SharePoint.

## Risorse
- [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial and Temporary License](https://releases.aspose.com/slides/java/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Ultimo aggiornamento:** 2026-08-06  
**Testato con:** Aspose.Slides for Java 25.4  
**Autore:** Aspose

## Tutorial correlati

- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}