---
date: '2026-07-17'
description: Scopri come aggiungere un grafico a PowerPoint creando un grafico Pie
  of Pie con Aspose.Slides per Java. Include configurazione, codice, personalizzazione
  e salvataggio in PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Aggiungi un grafico a PowerPoint con Aspose.Slides per Java. Questa
  guida mostra come creare, personalizzare e salvare un grafico Pie of Pie in PPTX
  in pochi minuti.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Aggiungi un grafico a PowerPoint – Crea un grafico Pie of Pie in Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Aggiungi un grafico a PowerPoint – Crea un grafico Pie of Pie in Java con Aspose.Slides
url: /it/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aggiungi grafico a PowerPoint – Crea un grafico Pie of Pie in Java con Aspose.Slides

## Grafici e Diagrammi

### Introduzione

Nelle presentazioni moderne guidate dai dati, **aggiungere un grafico a PowerPoint** è spesso il modo più rapido per trasformare numeri grezzi in intuizioni visive. Un grafico a torta tradizionale funziona bene per un piccolo numero di categorie, ma quando alcune fette sono molto piccole diventano illeggibili. Un grafico *Pie of Pie* risolve questo problema estraendo quelle piccole fette in una torta secondaria, mantenendo il grafico principale pulito e i dettagli accessibili.

In questo tutorial imparerai a **aggiungere un grafico a PowerPoint** creando un grafico Pie of Pie con Aspose.Slides per Java. Vedremo la configurazione dell'ambiente, la creazione del grafico, la personalizzazione delle etichette, la regolazione della posizione della divisione e infine il salvataggio della presentazione come file PPTX. Alla fine sarai pronto a incorporare grafici sofisticati in qualsiasi presentazione.

## Risposte rapide
In Aspose.Slides, `Presentation` rappresenta un file PPTX, `ChartType.PieOfPie` seleziona il grafico Pie of Pie, `setShowValue(true)` mostra i valori sulle etichette e `save` scrive il file.

- **Qual è la classe principale per la manipolazione di PowerPoint?** `Presentation` – rappresenta un intero file PPTX in memoria.  
- **Quale tipo di grafico crea una torta secondaria per le piccole fette?** `ChartType.PieOfPie`.  
- **Come visualizzare i valori su ogni fetta?** Imposta `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Puoi salvare il file direttamente come PPTX?** Sì – chiama `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Hai bisogno di una licenza per lo sviluppo?** Una prova gratuita di 30 giorni è sufficiente per i test; una licenza permanente rimuove le filigrane di valutazione.

## Cos'è un grafico Pie of Pie?
Un **grafico Pie of Pie** è una visualizzazione a due livelli che isola una o più piccole fette in una torta separata e collegata, rendendole più facili da leggere. Aspose.Slides supporta questo tipo di grafico nativamente, consentendo di controllare la dimensione della divisione, la posizione e la formattazione delle etichette.

## Perché aggiungere un grafico a PowerPoint con Aspose.Slides?
Aspose.Slides può generare, modificare e renderizzare file PowerPoint senza la necessità di Microsoft Office installato. Supporta **oltre 50 formati di input e output**, elabora presentazioni con **fino a 500 diapositive** in meno di un secondo su hardware server tipico e offre **controllo API completo** su stile del grafico, etichette dati e layout—perfetto per pipeline di reporting automatizzate.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 16+** installato.  
- Un IDE come **IntelliJ IDEA**, **Eclipse** o **NetBeans**.  
- Maven o Gradle per la gestione delle dipendenze (vedi le sezioni sotto).  
- Conoscenza di base di Java e familiarità con la creazione di progetti.

## Configurazione di Aspose.Slides per Java

### Informazioni sull'installazione

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

**Download diretto:** Puoi scaricare l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Passaggi per l'acquisizione della licenza
- **Prova gratuita:** Inizia con una prova di 30 giorni per esplorare tutte le funzionalità.  
- **Licenza temporanea:** Richiedi una chiave temporanea per una valutazione estesa.  
- **Acquisto:** Ottieni una licenza permanente per l'uso in produzione per rimuovere le filigrane di valutazione.

### Inizializzazione e configurazione di base
`Presentation` è l'oggetto principale per creare file PowerPoint, e `Chart` rappresenta una forma di grafico all'interno di una diapositiva.

```java
Presentation presentation = new Presentation();
```  

Questo crea una presentazione vuota pronta per diapositive e grafici.

## Guida all'implementazione

### Come aggiungere un grafico a PowerPoint usando Aspose.Slides per Java?

Carica una nuova `Presentation`, aggiungi una diapositiva e inserisci un `Chart` di tipo `PieOfPie`. La catena di chiamate API è concisa: crea il grafico, popola i dati della serie, regola la visibilità delle etichette, configura la dimensione della torta secondaria e infine salva. L'intero processo tipicamente rientra in meno di 20 righe di codice, rendendolo ideale per la generazione automatica di report.

### Creazione di un grafico 'Pie of Pie'

#### Panoramica
Costruiremo un grafico Pie of Pie sulla prima diapositiva, separeremo le fette più piccole e etichetteremo ogni segmento con il suo valore.

#### Passo 1: Crea un'istanza della classe Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Questo inizializza il contenitore per tutte le diapositive e i grafici successivi.

#### Passo 2: Aggiungi un grafico 'Pie of Pie' sulla prima diapositiva
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Qui specifichiamo `ChartType.PieOfPie` e definiamo la posizione del grafico (X, Y) e le dimensioni (larghezza, altezza) sulla tela della diapositiva.

#### Passo 3: Imposta le etichette dei dati per mostrare i valori per la serie
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Abilitare `showValue` fa sì che ogni fetta mostri il suo valore numerico, fondamentale per una rapida interpretazione dei dati.

#### Passo 4: Configura la dimensione del secondo grafico a torta e la divisione per percentuale
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Queste opzioni ti permettono di decidere quanta parte del grafico è destinata alla torta secondaria e quali fette vengono spostate in base a una soglia percentuale.

#### Passo 5: Salva la presentazione su disco in formato PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Suggerimento:** Usa un percorso assoluto o `Paths.get()` di Java per evitare separatori specifici della piattaforma.

## Problemi comuni e soluzioni

`License` carica un file di licenza per rimuovere le restrizioni di valutazione.

- **Avviso di licenza mancante:** Se vedi “Evaluation Only” sul grafico, assicurati di aver applicato un file di licenza valido tramite `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Divisione della fetta errata:** Verifica che la proprietà `splitBy` sia impostata su `SplitBy.Percentage` e che `secondPieSize` sia un valore compreso tra 0 e 100.  
- **Dati non visualizzati:** Conferma che la serie del grafico contenga almeno un punto dati; altrimenti il grafico verrà visualizzato vuoto.

## Domande frequenti

`IChart` rappresenta un oggetto grafico che può essere aggiunto a una diapositiva.

**D: Posso generare più grafici in una singola presentazione?**  
R: Sì, istanzia un nuovo `IChart` per ogni diapositiva o posizione; l'API consente un numero illimitato di oggetti grafico per file.

`SaveFormat.Pdf` specifica il formato di output PDF per il salvataggio.

**D: Aspose.Slides supporta il salvataggio anche in PDF?**  
R: Assolutamente – chiama `presentation.save("output.pdf", SaveFormat.Pdf)` per esportare lo stesso deck di diapositive in PDF.

`IPortion` rappresenta una singola fetta di un grafico a torta.

**D: Qual è il numero massimo di punti dati che un grafico Pie of Pie può gestire?**  
R: La libreria supporta fino a **10.000** punti dati per serie, limitati solo dalla memoria disponibile.

**D: È possibile personalizzare i colori delle singole fette?**  
R: Sì, accedi a ciascun `IPortion` tramite `chart.getChartData().getSeries().get_Item(0).getPortions()` e imposta `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**D: Come incorporare il PPTX generato in un'applicazione web?**  
R: Dopo aver salvato il file, trasmettilo direttamente al client usando `HttpServletResponse` con `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusione

Ora disponi di una ricetta completa e pronta per la produzione per **aggiungere un grafico a PowerPoint** creando un grafico Pie of Pie con Aspose.Slides per Java. Sperimenta con diverse soglie di divisione, formati delle etichette e combinazioni di colori per allinearle alle linee guida del tuo brand. Successivamente, esplora altri tipi di grafico—come barre impilate o radar—per arricchire ulteriormente le tue presentazioni automatizzate.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [Crea grafico dinamico Java – Tutorial sui grafici PowerPoint per Aspose.Slides](/slides/java/charts-graphs/)
- [Come aggiungere un grafico a torta PowerPoint con Aspose.Slides per Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}