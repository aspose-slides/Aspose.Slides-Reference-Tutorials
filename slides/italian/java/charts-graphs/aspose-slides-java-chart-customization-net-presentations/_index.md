---
date: '2026-06-08'
description: Scopri come aggiungere serie al grafico e personalizzare i grafici a
  colonne impilate nelle presentazioni .NET utilizzando Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Aggiungere serie al grafico con Aspose.Slides for Java in .NET
url: /it/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare la personalizzazione dei grafici nelle presentazioni .NET con Aspose.Slides per Java

## Introduzione
Nel mondo delle presentazioni guidate dai dati, i grafici sono strumenti indispensabili che trasformano numeri grezzi in storie visive accattivanti. Quando è necessario **add series to chart** in modo programmatico, soprattutto all'interno di file di presentazione .NET, il compito può sembrare opprimente. Fortunatamente, **Aspose.Slides for Java** offre un'API potente e indipendente dal linguaggio che rende la creazione e la personalizzazione dei grafici semplice — anche quando il formato di destinazione è un .NET PPTX. Questa guida ti accompagna nell'aggiungere serie, costruire un grafico a colonne impilate e perfezionare aspetti visivi come la larghezza dello spazio, così da poter generare diapositive dinamiche e ricche di dati dall'aspetto curato e professionale.

## Risposte rapide
La classe `Presentation` rappresenta un file PPTX, e `slide.getShapes().addChart(...)` inserisce una forma di grafico. Usa `chart.getChartData().getSeries().add(...)` per aggiungere una serie, e `setGapWidth()` regola la spaziatura.

- **Qual è la classe principale per avviare una presentazione?** `Presentation` – rappresenta un file PPTX in memoria.  
- **Quale metodo aggiunge un grafico a una diapositiva?** `slide.getShapes().addChart(...)` crea l'oggetto grafico sulla diapositiva.  
- **Come si aggiunge una nuova serie?** `chart.getChartData().getSeries().add(...)` inserisce una nuova serie di dati.  
- **È possibile modificare la larghezza dello spazio tra le barre?** Sì — chiama `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (il valore è una percentuale).  
- **È necessaria una licenza per la produzione?** Assolutamente sì — una licenza valida di Aspose.Slides for Java sblocca tutte le funzionalità e rimuove le filigrane di valutazione.

## Cos'è “add series to chart”?
Aggiungere una serie a un grafico significa inserire una nuova collezione di punti dati che il grafico visualizza come un elemento distintivo (ad esempio, un gruppo di colonne separato). Ogni serie può avere i propri valori, colori e formattazioni, consentendo confronti fianco a fianco di più set di dati.

## Perché usare Aspose.Slides per Java per modificare le presentazioni .NET?
Aspose.Slides per Java ti consente di generare o modificare file PPTX pienamente compatibili con i visualizzatori PowerPoint .NET, senza necessità di installare Microsoft Office. Usa Aspose.Slides per Java quando ti serve una soluzione server‑side, cross‑platform che crea o aggiorna file .NET PPTX, supporta oltre 50 tipi di grafico e gestisce file fino a 500 MB senza caricare l'intero documento in memoria. La sua API funziona in Java, Kotlin, Scala o qualsiasi linguaggio JVM, fornendo lo stesso output atteso dagli sviluppatori .NET.

## Prerequisiti
- Libreria **Aspose.Slides for Java** (versione 25.4 o successiva).  
- Maven, Gradle o download manuale del JAR.  
- Conoscenze di base di Java e familiarità con la struttura dei file PPTX.  

## Configurazione di Aspose.Slides per Java
### Installazione con Maven
Aggiungi la seguente dipendenza al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installazione con Gradle
Inserisci questa riga nel tuo file `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica l'ultimo JAR dalla pagina ufficiale di rilascio: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Acquisizione della licenza**  
Inizia con una prova gratuita scaricando una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/). Per l'uso in produzione, acquista una licenza completa per sbloccare tutte le funzionalità e rimuovere le filigrane di valutazione.

## Guida passo‑passo all'implementazione
Di seguito ogni passaggio è accompagnato da un frammento di codice conciso (invariato rispetto al tutorial originale) seguito da una spiegazione di ciò che fa.

### Passo 1: Creare una presentazione vuota
`Presentation` è la classe di ingresso che rappresenta un file PowerPoint in memoria.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Iniziamo con un file PPTX pulito, che ci fornisce una tela per aggiungere grafici.*

### Passo 2: Aggiungere un grafico a colonne impilate alla diapositiva
`Chart` rappresenta una forma di grafico all'interno di una diapositiva. `ChartType.StackedColumn` specifica un grafico a colonne impilate.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Il metodo `addChart` crea un **grafico a colonne impilate** e lo posiziona nell'angolo in alto‑a‑sinistra della diapositiva.*

### Passo 3: Aggiungere serie al grafico (Obiettivo principale)
`Series` incapsula una singola serie di dati in un grafico.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Qui **add series to chart** – ogni chiamata crea una nuova serie di dati che apparirà come un gruppo di colonne separato.*

### Passo 4: Aggiungere categorie al grafico
`Category` definisce un'etichetta dell'asse X per i dati del grafico.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Le categorie fungono da etichette dell'asse X, dando significato a ciascuna colonna.*

### Passo 5: Popolare i dati della serie
`DataPoint` contiene un valore numerico per una serie in una specifica categoria.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*I punti dati forniscono a ogni serie i valori numerici, che il grafico renderà come altezze delle barre.*

### Passo 6: Impostare la larghezza dello spazio per il gruppo di serie del grafico
`SeriesGroup` controlla le proprietà di layout per un gruppo di serie, come la larghezza dello spazio.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Regolare la larghezza dello spazio migliora la leggibilità, soprattutto quando sono presenti molte categorie.*

## Casi d'uso comuni
- **Report finanziari** – confrontare i ricavi trimestrali tra le unità di business.  
- **Dashboard di progetto** – mostrare le percentuali di completamento dei compiti per team.  
- **Analisi di marketing** – visualizzare le performance delle campagne fianco a fianco.  
Questi scenari beneficiano dell'**esempio di grafico a colonne impilate** perché evidenziano i contributi delle singole categorie al totale.

## Suggerimenti sulle prestazioni
- **Riutilizza l'oggetto `Presentation`** quando crei più grafici per ridurre il consumo di memoria.  
- **Limita il numero di punti dati** a quelli strettamente necessari per la narrazione visiva; Aspose.Slides può gestire 10.000 punti, ma la velocità di rendering diminuisce dopo circa 5.000.  
- **Disporre gli oggetti** (`presentation.dispose()`) dopo il salvataggio per liberare risorse ed evitare perdite di memoria.  

## Domande frequenti
**Q: Posso aggiungere altri tipi di grafico oltre alle colonne impilate?**  
A: Sì, Aspose.Slides supporta grafici a linee, a torta, ad area, radar, a bolle e oltre 50 altri tipi, tutti accessibili tramite lo stesso metodo `addChart`.

**Q: È necessaria una licenza separata per l'output .NET?**  
A: No, la stessa licenza Java funziona per tutti i formati di output, inclusi i file PPTX .NET.

**Q: Come modifico la palette dei colori del grafico?**  
A: Usa `series.getFormat().getFill().setFillType(FillType.Solid)` e poi imposta l'oggetto `Color` desiderato per ciascuna serie.

**Q: È possibile aggiungere etichette dati programmaticamente?**  
A: Assolutamente. Chiama `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` per visualizzare il valore numerico su ogni colonna.

**Q: Cosa succede se devo aggiornare una presentazione esistente?**  
A: Carica il file con `new Presentation("existing.pptx")`, modifica il grafico usando le stesse chiamate API e salvalo nuovamente su disco.

## Conclusione
Ora disponi di una guida completa, end‑to‑end, su come **add series to chart**, creare un **grafico a colonne impilate** e perfezionarne l'aspetto nelle presentazioni .NET usando Aspose.Slides per Java. Sperimenta con diversi tipi di grafico, colori e fonti di dati per costruire report visivi accattivanti che impressionano gli stakeholder e guidano decisioni basate sui dati.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come creare grafici a colonne impilate basati su percentuali in .NET usando Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Creazione e manipolazione avanzata delle serie di grafico con Aspose.Slides .NET per una visualizzazione dati efficace](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Cancella punti dati specifici di una serie di grafico con Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}