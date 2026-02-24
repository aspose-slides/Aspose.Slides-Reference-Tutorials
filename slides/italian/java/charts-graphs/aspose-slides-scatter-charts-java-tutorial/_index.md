---
date: '2026-02-24'
description: Scopri come personalizzare i grafici a dispersione Aspose usando Aspose.Slides
  per Java. Questa guida ti accompagna nella creazione, nella formattazione e nel
  salvataggio di grafici a dispersione dinamici nelle tue presentazioni.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Personalizza il grafico a dispersione Aspose in Java
url: /it/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

 the bullet list formatting with hyphens.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizza il grafico a dispersione Aspose in Java

In questo tutorial imparerai a **personalizzare il grafico a dispersione Aspose** con la potente libreria Aspose.Slides per Java. Ti guideremo attraverso la configurazione del progetto, la creazione di un grafico a dispersione, la modifica dei tipi di serie e dei marcatori, e infine il salvataggio della presentazione. Alla fine, sarai in grado di generare programmaticamente grafici a dispersione dall'aspetto professionale e di personalizzare ogni dettaglio visivo per adattarlo al tuo brand o alle esigenze di reporting.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides for Java (v25.4+).  
- **Quale versione di Java è supportata?** JDK 8 o superiore.  
- **Posso cambiare le forme dei marcatori?** Sì – usa `MarkerStyleType` per scegliere stelle, cerchi, ecc.  
- **Come salvo il file?** Chiama `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **È necessaria una licenza?** Una prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.

## Cos'è “personalizzare il grafico a dispersione Aspose”?
Personalizzare un grafico a dispersione con Aspose significa definire programmaticamente i dati, l'aspetto e il comportamento del grafico—tutto, dalle coordinate dei punti ai simboli dei marcatori—senza aprire PowerPoint manualmente. Questo approccio è ideale per reportistica automatizzata, presentazioni basate sui dati o qualsiasi scenario in cui siano necessarie visualizzazioni ripetibili e di alta qualità.

## Perché personalizzare i grafici a dispersione con Aspose.Slides?
- **Controllo totale** – modifica i tipi di serie, gli stili dei marcatori, i colori e altro tramite codice Java.  
- **Automazione** – genera decine di grafici al volo per dashboard o report batch.  
- **Cross‑platform** – funziona su qualsiasi OS che supporta Java, senza necessità di installare Office.  
- **Prestazioni** – API leggera che gestisce grandi set di dati in modo efficiente.

## Prerequisiti

Per seguire, assicurati di avere:

- **Aspose.Slides for Java** (v25.4 o successivo).  
- **Java Development Kit (JDK)** 8 + installato.  
- Maven o Gradle per la gestione delle dipendenze (o puoi scaricare il JAR manualmente).  
- Conoscenze di base di Java e familiarità con lo strumento di build di tua scelta.

## Configurazione di Aspose.Slides per Java

Integra la libreria nel tuo progetto utilizzando uno dei metodi seguenti.

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
- **Prova gratuita** – valutazione di 30 giorni.  
- **Licenza temporanea** – periodo di test esteso.  
- **Licenza completa** – utilizzo in produzione con supporto premium.

## Guida passo‑passo per personalizzare il grafico a dispersione Aspose

### 1️⃣ Prepare a folder for your presentation files
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Perché è importante:* Assicurarsi che la cartella di output esista impedisce `FileNotFoundException` quando successivamente salvi il PPTX.

### 2️⃣ Create a new presentation and grab the first slide
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Una nuova `Presentation` ti fornisce una tela pulita; la prima diapositiva è dove inseriremo il grafico.

### 3️⃣ Add a scatter chart with smooth lines
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Il `ChartType.ScatterWithSmoothLines` crea un grafico a dispersione a linee fluide, perfetto per la visualizzazione delle tendenze.

### 4️⃣ Clear any default series and add your own
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
Rimuovere le serie predefinite ti dà il pieno controllo sui dati da visualizzare.

### 5️⃣ Populate the first series with data points
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` prende una cella valore X e una cella valore Y, costruendo il grafico a dispersione punto per punto.

### 6️⃣ Customize series type and marker appearance
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
Qui **personalizziamo il grafico a dispersione Aspose** passando a linee rette, ingrandendo i marcatori e scegliendo simboli distinti (stella vs. cerchio) per una maggiore chiarezza visiva.

### 7️⃣ Save the presentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Salvare come `Pptx` conserva tutte le personalizzazioni del grafico e rende il file pronto per la condivisione o ulteriori modifiche.

## Casi d'uso comuni per i grafici a dispersione personalizzati
- **Dashboard finanziari** – traccia prezzo delle azioni vs. volume.  
- **Ricerca scientifica** – visualizza misurazioni sperimentali con marcatori di errore.  
- **Gestione progetti** – confronta lo sforzo pianificato vs. reale tra le attività.  

## Suggerimenti sulle prestazioni
- Disporre dell'oggetto `Presentation` (`pres.dispose()`) dopo il salvataggio per liberare le risorse native.  
- Per grandi set di dati, popola prima il workbook e poi collega le serie per evitare ripetuti refresh dell'interfaccia.  
- Riutilizza una singola istanza di `IChartDataWorkbook` quando aggiungi molte serie.

## Domande frequenti

### Come cambio il colore dei marcatori?
Usa `series.getMarker().getFillFormat().setFillColor(Color)` dove `Color` è un'istanza di `java.awt.Color` (ad esempio, `Color.RED`).

### Posso aggiungere più di due serie a un grafico a dispersione?
Assolutamente. Ripeti la chiamata `chart.getChartData().getSeries().add(...)` per ogni serie aggiuntiva e popola i suoi punti dati di conseguenza.

### È possibile impostare una legenda personalizzata per ogni serie?
Sì. Dopo aver creato una serie, chiama `series.getLegend().setText("Your Legend Text")` per sovrascrivere il nome predefinito.

### Come posso esportare il grafico come immagine invece di un PPTX?
Chiama `chart.getImage().save("chart.png", ImageFormat.Png)` dopo aver configurato il grafico. Questo ti fornisce un file PNG autonomo.

### Cosa fare se devo animare i punti del grafico a dispersione?
Aspose.Slides supporta gli effetti di animazione. Usa `chart.getTimeline().getMainSequence().addEffect(...)` per aggiungere animazioni di ingresso o enfasi al grafico o alle singole serie.

---

**Ultimo aggiornamento:** 2026-02-24  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}