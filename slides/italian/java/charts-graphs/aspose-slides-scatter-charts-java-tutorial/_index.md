---
date: '2026-07-27'
description: Come personalizzare un grafico usando Aspose.Slides per Java. Scopri
  come creare un grafico PowerPoint, formattare le serie a dispersione e salvare le
  presentazioni in modo efficiente.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Come personalizzare un grafico con Aspose.Slides per Java. Questa
  guida mostra come creare un grafico PowerPoint, formattare i punti a dispersione
  e esportare le presentazioni.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Come personalizzare il grafico: grafico a dispersione Aspose in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Come personalizzare il grafico: grafico a dispersione Aspose in Java'
url: /it/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizza il grafico a dispersione Aspose in Java

In questo tutorial scoprirai **come personalizzare un grafico** — in particolare un grafico a dispersione — utilizzando la potente libreria Aspose.Slides per Java. Ti guideremo attraverso la configurazione del progetto, la creazione di un grafico a dispersione, la modifica dei tipi di serie e dei marcatori, e infine il salvataggio della presentazione. Alla fine, sarai in grado di generare programmaticamente grafici a dispersione dall’aspetto professionale e di personalizzare ogni dettaglio visivo per adattarlo al tuo brand o alle esigenze di reporting.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides for Java (v25.4+).  
- **Quale versione di Java è supportata?** JDK 8 o superiore.  
- **Posso cambiare le forme dei marcatori?** Yes – use `MarkerStyleType` to pick stars, circles, etc.  
- **Come salvo il file?** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **È necessaria una licenza?** A free trial works for development; a commercial license is needed for production.

## Come personalizzare un grafico in Java con Aspose.Slides?
`Presentation` è la classe Aspose.Slides che rappresenta un intero file PowerPoint in memoria. Carica una nuova `Presentation`, aggiungi un grafico a dispersione sulla prima diapositiva, configura le serie e gli stili dei marcatori, quindi chiama `save`. Questo flusso di lavoro unico crea un grafico completamente stilizzato in poche righe di codice Java, pronto per l’inclusione in qualsiasi presentazione PowerPoint.

## Cos'è “personalizzare il grafico a dispersione Aspose”?
Personalizzare un grafico a dispersione con Aspose significa definire programmaticamente i dati, l’aspetto e il comportamento del grafico—tutto, dalle coordinate dei punti ai simboli dei marcatori—senza aprire manualmente PowerPoint. Questo approccio è ideale per reportistica automatizzata, presentazioni guidate dai dati o qualsiasi scenario in cui siano necessarie visualizzazioni ripetibili e di alta qualità.

## Perché personalizzare i grafici a dispersione con Aspose.Slides?
Aspose.Slides offre agli sviluppatori il pieno controllo programmatico sull’aspetto dei grafici, consentendo la creazione automatica di visualizzazioni di alta qualità, l’integrazione fluida nei flussi di lavoro di reporting e la possibilità di personalizzare ogni elemento visivo senza aprire manualmente PowerPoint, risparmiando tempo e garantendo coerenza tra le presentazioni.

- **Controllo totale** – modifica i tipi di serie, gli stili dei marcatori, i colori e altro tramite codice Java.  
- **Automazione** – genera decine di grafici al volo per dashboard o report batch.  
- **Cross‑platform** – funziona su qualsiasi OS che supporta Java, senza necessità di installare Office.  
- **Prestazioni** – API leggera che elabora **oltre 150 tipi di grafico** e gestisce presentazioni con centinaia di pagine senza caricare l’intero file in memoria.

## Prerequisiti

Per seguire, assicurati di avere:

- **Aspose.Slides for Java** (v25.4 o successiva).  
- **Java Development Kit (JDK)** 8 + installato.  
- Maven o Gradle per la gestione delle dipendenze (oppure puoi scaricare il JAR manualmente).  
- Conoscenze di base di Java e familiarità con lo strumento di build scelto.

## Configurare Aspose.Slides per Java

Integra la libreria nel tuo progetto usando uno dei metodi seguenti.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Oppure scarica l'ultima versione da [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
- **Free Trial** – valutazione di 30 giorni.  
- **Temporary License** – periodo di test esteso.  
- **Full License** – uso in produzione con supporto premium.

## Guida passo‑passo per personalizzare il grafico a dispersione Aspose

### 1️⃣ Prepara una cartella per i file della tua presentazione
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Perché è importante:* Assicurarsi che la cartella di output esista evita `FileNotFoundException` quando si salva successivamente il PPTX.

### 2️⃣ Crea una nuova presentazione e prendi la prima diapositiva
`Presentation` rappresenta un documento PowerPoint e fornisce l’accesso a diapositive e forme. La classe `Presentation` rappresenta un intero file PowerPoint in memoria.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Aggiungi un grafico a dispersione con linee fluide
`ChartType.ScatterWithSmoothLines` crea un grafico a dispersione dove i punti sono collegati da linee fluide.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Cancella eventuali serie predefinite e aggiungi le tue
`IChartSeries` rappresenta una serie di dati all’interno di un grafico.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Popola la prima serie con i punti dati
`addDataPointForScatterSeries` aggiunge un singolo punto X‑Y a una serie di dispersione.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Personalizza il tipo di serie e l'aspetto del marcatore
`Marker` controlla il simbolo visivo usato per ogni punto dati in una serie di grafico.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Salva la presentazione
`save` scrive la presentazione su un file nel formato specificato.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Casi d'uso comuni per i grafici a dispersione personalizzati
- **Dashboard finanziari** – traccia prezzo delle azioni vs. volume.  
- **Ricerca scientifica** – visualizza misurazioni sperimentali con marcatori di errore.  
- **Gestione progetti** – confronta lo sforzo pianificato vs. reale tra le attività.  

## Suggerimenti sulle prestazioni
- Chiama `pres.dispose()` dopo il salvataggio per rilasciare la memoria nativa.  
- Per set di dati di grandi dimensioni, popola prima il workbook e poi associa le serie per evitare aggiornamenti UI ripetuti.  
- Riutilizza una singola istanza di `IChartDataWorkbook` quando aggiungi molte serie per mantenere basso l'uso della memoria.

## Domande frequenti

**Q: Come cambio il colore dei marcatori?**  
A: Usa `series.getMarker().getFillFormat().setFillColor(Color)` dove `Color` è un'istanza di `java.awt.Color` come `Color.RED`.

**Q: Posso aggiungere più di due serie a un grafico a dispersione?**  
A: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional series and populate its points accordingly.

**Q: È possibile impostare una legenda personalizzata per ogni serie?**  
A: Absolutely. After creating a series, invoke `series.getLegend().setText("Your Legend Text")` to override the default name.

**Q: Come posso esportare il grafico come immagine invece di un PPTX?**  
A: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring the chart. This produces a standalone PNG file.

**Q: E se avessi bisogno di animare i punti del grafico a dispersione?**  
A: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)` to add entrance or emphasis animations to the chart or individual series.

**Ultimo aggiornamento:** 2026-07-27  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea e personalizza grafici PowerPoint in Java usando Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Come creare un grafico a bolle in PowerPoint usando Aspose.Slides per Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Crea e personalizza grafici con linee di tendenza in Aspose.Slides per Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}