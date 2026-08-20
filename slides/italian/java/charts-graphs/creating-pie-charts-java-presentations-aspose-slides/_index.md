---
date: '2026-08-01'
description: Scopri come utilizzare una licenza Aspose Slides per creare e personalizzare
  grafici a torta nelle presentazioni Java. Segui le istruzioni passo‑passo per configurare
  i dati del grafico a torta e aggiungere le diapositive del grafico in modo efficiente.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Scopri come utilizzare una licenza Aspose Slides per creare e personalizzare
  grafici a torta nelle presentazioni Java. Segui le istruzioni passo‑passo per configurare
  i dati del grafico a torta e aggiungere le diapositive del grafico in modo efficiente.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Crea grafici a torta in Java con una licenza Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Crea grafici a torta in Java con una licenza Aspose Slides
url: /it/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici a torta in presentazioni Java usando Aspose.Slides

## Introduzione

Se hai bisogno di produrre presentazioni dall'aspetto professionale, **una licenza Aspose Slides** ti offre la possibilità di generare e formattare i grafici in modo programmatico. In questa guida imparerai a creare un grafico a torta, configurarne i dati e incorporarlo in una presentazione Java — tutto senza dipendere da Microsoft PowerPoint. Ti guideremo attraverso la configurazione, il flusso di codice e i consigli delle migliori pratiche, così potrai fornire report visivi curati in pochi minuti.

**Cosa imparerai:**
- Configurare Aspose.Slides per Java con una licenza valida
- Passaggi per creare e personalizzare un grafico a torta
- Come configurare i dati del grafico a torta e aggiungere diapositive con grafici
- Problemi comuni e trucchi per le prestazioni

Iniziamo confermando che il tuo ambiente è pronto.

## Risposte rapide
- **Cosa consente la licenza Aspose Slides?** Creazione completa di grafici, esportazione in PDF/HTML e rimozione dei watermark.
- **Quale versione di Java è richiesta?** JDK 16 o successiva.
- **Ho bisogno di Maven o Gradle?** Entrambi funzionano; la libreria è disponibile per entrambi.
- **Quanti punti dati può contenere un grafico a torta?** Fino a 10 000 punti senza problemi di memoria.
- **Posso esportare la diapositiva come immagine?** Sì – PNG, JPEG, SVG e altri formati sono supportati.

## Prerequisiti
Prima di iniziare, verifica di avere:
- **Librerie richieste:** Aspose.Slides per Java (versione 25.4 o successiva) – questa versione supporta i formati di file più recenti e ottimizzazioni delle prestazioni.
- **Configurazione dell'ambiente:** JDK 16+ installato e configurato nel tuo IDE o sistema di build.
- **Conoscenze di base:** Familiarità con Java, Maven o Gradle e i concetti di programmazione orientata agli oggetti.

## Configurazione di Aspose.Slides per Java

Per utilizzare Aspose.Slides per Java, includilo nel tuo progetto. Ecco come aggiungere la dipendenza con gli strumenti di build più comuni:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Download diretto:** Puoi anche scaricare l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza

Aspose offre una prova gratuita che sblocca tutte le funzionalità, ma è necessaria una **licenza Aspose Slides valida** per l'uso in produzione, per rimuovere i watermark di valutazione e ottenere benefici di prestazioni. Le opzioni di acquisto sono elencate nella [pagina di acquisto](https://purchase.aspose.com/buy). Dopo aver ottenuto il file di licenza, caricalo una volta all'avvio dell'applicazione:

`License` carica e applica la tua licenza Aspose.Slides.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Guida all'implementazione

### Creare e aggiungere un grafico a torta alla presentazione

#### Panoramica
Questa sezione spiega come creare un grafico a torta, configurare la sua serie di dati e incorporare il grafico in una diapositiva. Vedrai il flusso completo dall'inizializzazione dell'oggetto presentazione al salvataggio del file finale.

#### Passo 1: Inizializzare la presentazione  
`Presentation` è l'oggetto di livello superiore di Aspose.Slides che rappresenta un file PowerPoint in memoria. Creare un'istanza ti fornisce un mazzo di diapositive vuoto pronto per la modifica.

```java
demo.Presentation pres = new demo.Presentation();
```  
Questa riga crea una nuova presentazione su cui verranno applicate tutte le modifiche successive.

#### Passo 2: Aggiungere un grafico a torta alla diapositiva  
`Chart` è la classe che incapsula gli oggetti grafico, inclusi i grafici a torta. Aggiungere un grafico a una diapositiva è una singola chiamata di metodo che specifica posizione e dimensione.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` e `yPosition` impostano l'angolo in alto a sinistra del grafico.  
- `width` e `height` definiscono l'area visiva del grafico sulla diapositiva.

#### Passo 3: Configurare i dati del grafico a torta  
`ChartData` contiene le serie di dati per un grafico.  
**Come configuro i dati del grafico a torta?**  
Fornisci prima una risposta concisa: usa la collezione `ChartData` per aggiungere una serie, quindi popola gli oggetti `ChartDataPoint` con valori numerici e nomi di categoria. Questo approccio consente di visualizzare fino a 10 000 fette mantenendo la formattazione delle etichette. Dopo aver impostato i dati, puoi personalizzare colori, legende e etichette dei dati per aderire alla guida di stile aziendale.

Ecco il codice che aggiunge due categorie e mostra le loro etichette:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Il frammento crea una serie di dati, inserisce due punti e abilita le etichette di categoria sul grafico.

#### Passo 4: Salvare la presentazione  
Infine, salva la presentazione in un formato di file a tua scelta (PPTX, PDF o PNG). Il metodo `save` rispetta la licenza attiva, garantendo che non compaiano watermark di prova.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Problemi comuni e soluzioni
- **Errore di licenza mancante:** Assicurati che il percorso del file di licenza sia corretto e che l'oggetto `License` sia istanziato prima di qualsiasi chiamata a Aspose.Slides.
- **Grafico vuoto:** Verifica che la serie `ChartData` contenga almeno un `ChartDataPoint`. Una serie vuota genera un'area grafico vuota.
- **Ritardo di prestazioni con grandi set di dati:** Usa `presentation.getSlides().removeAt(index)` per scartare diapositive inutilizzate e chiama `System.gc()` dopo elaborazioni intensive.

## Applicazioni pratiche
1. **Report aziendali:** Visualizza la quota di mercato o la distribuzione dei ricavi per regione con un unico grafico a torta.
2. **Presentazioni accademiche:** Mostra i risultati di sondaggi o esperimenti in un formato chiaro e digeribile.
3. **Dashboard di progetto:** Rappresenta le percentuali di completamento delle attività o l'allocazione delle risorse istantaneamente su una diapositiva.

Puoi anche combinare Aspose.Slides con JDBC per estrarre dati in tempo reale da un database, generando grafici aggiornati per briefing settimanali ai dirigenti.

## Considerazioni sulle prestazioni
Quando si gestiscono presentazioni che contengono molte immagini ad alta risoluzione o grandi set di dati:
- Rilascia gli oggetti tempestivamente usando `try‑with‑resources` o chiamate esplicite a `dispose()`.
- Abilita il caricamento pigro delle risorse delle diapositive per mantenere basso l'uso della memoria.
- Per l'elaborazione batch, riutilizza una singola istanza `Presentation` quando possibile per ridurre l'overhead della JVM.

## Conclusione
Ora disponi di un flusso di lavoro completo e pronto per la produzione per creare grafici a torta in Java usando una **licenza Aspose Slides**. Sperimenta con tipi di grafico aggiuntivi — barre, linee o ciambella — per arricchire ulteriormente le tue diapositive. Successivamente, esplora le capacità di esportazione dell'API per generare automaticamente report PDF o immagini PNG.

## Domande frequenti

**D: Come aggiungo più grafici a una singola diapositiva?**  
R: Chiama `slide.getShapes().addChart()` per ogni grafico, fornendo coordinate e dimensioni uniche per ogni istanza.

**D: Quali sono alcune alternative ad Aspose.Slides per Java?**  
R: Apache POI e JFreeChart sono alternative comuni, ma mancano delle opzioni di esportazione complete e del modello di licenza di Aspose.

**D: Posso convertire la mia presentazione in altri formati usando Aspose.Slides?**  
R: Sì — esporta in PDF, XPS, HTML, PNG, JPEG, SVG e altri con una singola chiamata `save`.

**D: Come gestisco la licenza per un grande team di sviluppo?**  
R: Acquista una licenza enterprise che copra più sviluppatori e server; contatta le vendite di Aspose per sconti su volume.

**D: Cosa succede se i dati del mio grafico si aggiornano frequentemente?**  
R: Integra Aspose.Slides con una fonte dati (ad esempio una query SQL) e ricostruisci il grafico a runtime; l'API supporta il binding dinamico dei dati.

## Risorse
- **Documentation:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase:** [Buy a License](https://purchase.aspose.com/buy)
- **Free Trial:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporary License:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-01  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Tutorial correlati

- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create and Customize Charts in Java Presentations Using Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [How to Create and Configure Presentations with Aspose.Slides Java: A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}