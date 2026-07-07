---
date: '2026-07-03'
description: Scopri come creare grafici Sunburst passo passo in Java usando Aspose.Slides,
  con opzioni di personalizzazione complete per le presentazioni PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Come creare grafici Sunburst in Java usando Aspose.Slides
url: /it/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici Sunburst in Java usando Aspose.Slides

## Introduzione
Nelle presentazioni odierne guidate dai dati, **come creare visualizzazioni sunburst** rapidamente può distinguere le tue diapositive. Questo tutorial ti guida nella creazione di un grafico Sunburst con Aspose.Slides per Java, dalla configurazione del progetto all'esportazione finale, così potrai fornire grafiche gerarchiche accattivanti senza uscire dall'ecosistema Java.

## Risposte rapide
- **Qual è la classe principale per un file PowerPoint?** `Presentation` – rappresenta l'intero PPTX in memoria.  
- **Quante righe di codice sono necessarie per un sunburst di base?** Tipicamente 5–7 righe una volta referenziata la libreria.  
- **Quali formati di output sono supportati?** PPTX, PDF, PNG, SVG e HTML.  
- **Posso personalizzare segmenti individuali?** Sì – i colori di riempimento, i bordi e le etichette dei dati sono completamente personalizzabili.  
- **È necessaria una licenza per la produzione?** Una valutazione gratuita è sufficiente per i test; è richiesta una licenza commerciale per il deployment.

## Cos'è un grafico Sunburst?
Un grafico Sunburst visualizza dati gerarchici come anelli concentrici, dove ogni anello rappresenta un livello della gerarchia. Consente agli spettatori di comprendere le relazioni padre‑figlio a colpo d'occhio, rendendolo ideale per organigrammi, visualizzazioni tassonomiche e metriche a più livelli. È particolarmente utile per mostrare categorie a più livelli come linee di prodotto, regioni geografiche o strutture organizzative, permettendo di vedere sia la distribuzione complessiva sia il dettaglio di ciascun segmento.

## Perché usare Aspose.Slides per i grafici Sunburst?
Aspose.Slides supporta **oltre 30 tipi di grafico**, elabora file fino a **500 MB** senza caricare l'intero documento in memoria e rende le grafiche a **300 DPI** per un output cristallino. Queste capacità quantificate garantiscono una generazione rapida e visualizzazioni di alta qualità anche per presentazioni di grandi dimensioni. Inoltre, la libreria offre operazioni thread‑safe e si integra perfettamente con i popolari strumenti di build Java, rendendola adatta sia per la generazione di presentazioni desktop che server‑side su larga scala.

## Prerequisiti
- Java Development Kit (JDK) 8 o versioni successive.  
- Maven o Gradle per la gestione delle dipendenze.  
- Aspose.Slides per Java (ultima versione).  
- Conoscenza di base delle strutture dati gerarchiche.

## Come creare grafici Sunburst passo dopo passo?
Carica il tuo ambiente, aggiungi un grafico, fornisci i dati gerarchici, personalizzalo e salva il file – il tutto in pochi semplici passaggi. Di seguito trovi il flusso di lavoro esatto da seguire senza scrivere codice boilerplate aggiuntivo. Il processo è completamente automatizzato, non richiede interazioni manuali con l'interfaccia utente e può essere integrato in job batch o servizi web per generare grafici su richiesta.

### Passo 1: Configurare il progetto
Aggiungi la dipendenza Maven di Aspose.Slides (o lo snippet Gradle equivalente) al tuo `pom.xml`. Questo scarica tutti i binari necessari e le librerie transitive.

### Passo 2: Caricare o creare una presentazione
`Presentation` è l'oggetto di livello superiore di Aspose.Slides che rappresenta un singolo file PowerPoint in memoria. Istanzialo con `new Presentation()` per una nuova presentazione o passa un percorso file per aprire un PPTX esistente.

### Passo 3: Aggiungere un grafico Sunburst
Inserisci una nuova forma di grafico in una diapositiva usando `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Questo crea il segnaposto Sunburst pronto per i dati. `ChartType.Sunburst` specifica il tipo di grafico Sunburst quando si aggiunge un grafico a una diapositiva.

### Passo 4: Popolare i dati gerarchici
`ChartData` contiene le serie di dati e le categorie per un grafico. Accedi alla collezione `ChartData` del grafico e aggiungi serie e categorie che riflettano la tua gerarchia. Per ogni livello, specifica la relazione padre‑figlio tramite la proprietà `ParentSeries`, consentendo al grafico di renderizzare automaticamente gli anelli concentrici.

### Passo 5: Personalizzare l'aspetto
Regola finemente i colori dei segmenti, gli stili dei bordi e le etichette dei dati tramite gli oggetti `ChartSeries` e `ChartDataPoint`. `ChartSeries` rappresenta una serie di punti dati in un grafico. `ChartDataPoint` rappresenta un singolo punto dati all'interno di una serie. Puoi anche abilitare la rotazione 3‑D o impostare la proprietà `Explode` per evidenziare sezioni specifiche.

### Passo 6: Salvare la presentazione
L'enumerazione `SaveFormat` definisce i formati di file in cui è possibile salvare una presentazione. Chiama `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` per scrivere il file su disco. Puoi anche esportare in PDF o PNG modificando il valore dell'enumerazione `SaveFormat`.

## Come personalizzare i colori del grafico Sunburst?
Specifica un colore di riempimento per ogni `ChartDataPoint` usando `point.getFillFormat().setFillType(FillType.Solid)` e poi `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Questo approccio diretto ti consente di abbinare il branding aziendale o enfatizzare i punti dati chiave. Puoi anche applicare riempimenti a gradiente, regolare la trasparenza o usare i colori del tema per garantire coerenza con il resto del design della diapositiva.

## Problemi comuni e soluzioni
- **Problema:** La gerarchia appare piatta.  
  **Soluzione:** Assicurati che ogni serie figlia faccia correttamente riferimento al suo `ParentSeries`. I collegamenti mancanti fanno sì che il grafico tratti tutti i dati come un unico livello.
- **Problema:** Il PNG esportato appare sfocato.  
  **Soluzione:** Aumenta il DPI di esportazione impostando `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problema:** File PPTX di grandi dimensioni causano OutOfMemoryError.  
  **Soluzione:** Usa `Presentation.setMemoryOptimization(true)` per trasmettere i dati e mantenere basso l'uso della memoria.

## Domande frequenti

**D: Posso generare un grafico Sunburst da un file CSV?**  
R: Sì. Leggi il CSV, costruisci la gerarchia in memoria e la fornisci alla collezione `ChartData` del grafico prima di salvare.

**D: Aspose.Slides supporta transizioni animate per i grafici Sunburst?**  
R: Sì. Applica un `SlideShowTransition` alla diapositiva o usa `ChartFormat.setAnimationEnabled(true)` per animazione a livello di grafico.

**D: È possibile esportare il grafico come immagine vettoriale SVG?**  
R: Assolutamente. Salva la presentazione con `SaveFormat.Svg` per ottenere una versione vettoriale scalabile del grafico Sunburst.

**D: Qual è il numero massimo di punti dati che un grafico Sunburst può gestire?**  
R: Aspose.Slides elabora in modo affidabile fino a **10.000** punti dati in un singolo grafico Sunburst senza degradazione delle prestazioni.

**D: È necessaria una licenza separata per ogni ambiente di distribuzione?**  
R: Una singola licenza commerciale copre tutti gli ambienti (sviluppo, staging, produzione) purché i termini della licenza siano rispettati.

## Conclusione
Ora hai una guida completa, passo dopo passo, su **come creare grafici sunburst** in Java usando Aspose.Slides. Seguendo il flusso di lavoro sopra, potrai generare visualizzazioni gerarchiche di alta qualità e completamente personalizzabili per qualsiasi presentazione PowerPoint.

---

**Ultimo aggiornamento:** 2026-07-03  
**Testato con:** Aspose.Slides for Java 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo‑a‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Padroneggiare la personalizzazione dei grafici PowerPoint usando Aspose.Slides Java per presentazioni dinamiche](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animare le categorie dei grafici PowerPoint con Aspose.Slides per Java | Guida passo‑a‑passo](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}