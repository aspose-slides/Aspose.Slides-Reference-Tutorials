---
date: '2026-09-12'
description: Scopri come utilizzare Maven Aspose Slides per aggiungere e personalizzare
  grafici azionari dinamici in PowerPoint con Java. Include configurazione, aggiunta
  di serie di dati, formattazione delle linee e salvataggio.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Il tutorial Maven Aspose Slides mostra come creare e personalizzare
  grafici azionari dinamici in PowerPoint usando Java, coprendo serie di dati, formattazione
  delle linee e salvataggio.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Guida Maven Aspose Slides: crea grafici azionari dinamici in PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: crea grafici azionari dinamici in PowerPoint con Java'
url: /it/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: crea grafici azionari dinamici in PowerPoint con Java

## Introduzione

**Maven Aspose Slides** consente di generare programmaticamente presentazioni PowerPoint sofisticate da Java. In questo tutorial imparerai a creare grafici azionari dinamici, aggiungere e formattare le serie di dati, personalizzare le linee del grafico e infine salvare il file. Che tu sia un analista finanziario che prepara report trimestrali o uno sviluppatore che costruisce presentazioni automatiche, i passaggi seguenti ti offrono una soluzione completa, pronta per la produzione.

**Cosa imparerai**
- Come configurare Maven con Aspose.Slides per Java  
- Come aggiungere un grafico azionario e cancellare i dati predefiniti  
- Come **aggiungere un grafico di serie di dati** e **formattare le linee del grafico**  
- Come **personalizzare gli elementi visivi specifici di chart java**  
- Come salvare la presentazione aggiornata

Pronto a trasformare i numeri grezzi in visualizzazioni azionarie accattivanti? Iniziamo!

## Risposte rapide
- **Quale artefatto Maven è necessario?** `aspose-slides` version 25.4 (or newer).  
- **Posso eseguirlo su qualsiasi OS?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **Ho bisogno di una licenza per lo sviluppo?** A free temporary license works for testing; a full license is required for production.  
- **Quali tipi di grafico sono supportati?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **Quanto grande può essere una presentazione che posso elaborare?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## Cos'è Maven Aspose Slides?

`Aspose.Slides for Java` è un'API Java che consente la creazione, manipolazione e conversione di file PowerPoint senza Microsoft Office. L'integrazione Maven semplifica la gestione delle dipendenze, permettendo di scaricare la libreria direttamente da Maven Central.

## Perché usare Maven Aspose Slides per i grafici azionari?

Aspose.Slides supporta **oltre 70 tipi di grafico** e può renderizzare presentazioni di centinaia di pagine in meno di un secondo su hardware server tipico. Le sue funzionalità **linea high‑low** e **barra up/down** ti offrono un controllo preciso sulle visualizzazioni finanziarie, molto oltre ciò che offre l'interfaccia di PowerPoint.

## Prerequisiti

- **Java Development Kit (JDK)** – versione 11 o superiore.  
- **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor preferisci.  
- **Aspose.Slides for Java** – versione 25.4 (l'ultima al momento della stesura).  

### Configurazione di Aspose.Slides per Java

#### Maven
To integrate Aspose.Slides into your project using Maven, add the following dependency to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
For Gradle users, include this in your `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Download diretto
In alternativa, scarica l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Acquisizione della licenza** – inizia con una prova gratuita o richiedi una licenza temporanea. Per uso commerciale, acquista una licenza completa.

Per un riferimento dettagliato all'API, consulta la [documentazione di Aspose.Slides](https://docs.aspose.com/slides/java/).

## Come creare un grafico azionario dinamico passo passo

Carica la tua presentazione, aggiungi un grafico azionario, cancella i dati predefiniti, quindi inserisci le tue serie e categorie. La risposta diretta alla domanda principale è:

> Carica un PPTX esistente con `new Presentation("template.pptx")`, aggiungi un `Chart` di tipo `ChartType.Stock`, cancella le sue serie e categorie predefinite, quindi popolalo con i tuoi punti dati e le opzioni di formattazione. Infine, chiama `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inizializza presentazione
#### Panoramica
Inizia caricando un file PowerPoint esistente così da poterlo modificare in loco.

#### Passo‑per‑passo
1. **Importa la libreria** – la classe `Presentation` è il punto di ingresso per tutte le operazioni sulle slide.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Carica il file della presentazione** – fornisci il percorso al tuo PPTX modello.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi grafico azionario alla slide
#### Panoramica
Inserisci un grafico Stock nella prima slide della presentazione.

La classe `Chart` rappresenta una forma di grafico che può essere aggiunta a una slide.

#### Risposta diretta
Aggiungi un grafico azionario chiamando `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Questo crea un oggetto grafico che puoi manipolare immediatamente.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Cancella le serie di dati e le categorie esistenti nel grafico
#### Panoramica
Rimuovi eventuali serie o categorie pre‑popolate così da poter iniziare con un set di dati pulito.

L'oggetto `ChartData` contiene le serie e le categorie per un grafico.

#### Risposta diretta
Invoca `chart.getChartData().getSeries().clear()` e `chart.getChartData().getCategories().clear()` per cancellare il contenuto predefinito prima di aggiungere i tuoi.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi categorie ai dati del grafico
#### Panoramica
Definisci le categorie dell'asse X (ad es., date) che raggruppano i valori azionari.

`ChartCategory` rappresenta un'etichetta dell'asse X per un grafico.

#### Risposta diretta
Crea un nuovo `ChartCategory` per ogni etichetta usando `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, ripetendo per ogni mese o periodo.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi serie di dati al grafico
#### Panoramica
Aggiungi le quattro serie essenziali: Open, High, Low e Close.

`ChartSeries` contiene una collezione di punti dati per una specifica serie nel grafico.

#### Risposta diretta
Per ogni serie, chiama `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Questo registra la serie nel workbook dei dati del grafico.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi punti dati alle serie
#### Panoramica
Popola ogni serie con valori numerici che rappresentano i prezzi delle azioni.

`DataPoint` rappresenta un singolo valore in una serie.

#### Risposta diretta
Itera attraverso la tua collezione di dati e usa `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (o il metodo appropriato per il tipo di serie) per inserire ogni punto.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formatta linee high‑low e barre up/down
#### Panoramica
Regola lo stile visivo dei connettori high‑low e dei riempimenti delle barre up/down.

`Marker` definisce il simbolo visivo per un punto dati.

#### Risposta diretta
Imposta `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` e configura `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` per controllare lo spessore e il colore della linea.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Visualizza barre up/down
Usa il metodo `setShowUpDownBars(true)` del grafico per rendere visibili le barre up/down.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personalizza le etichette dati sulle linee high‑low
#### Panoramica
Mostra i valori numerici direttamente sulle linee high‑low per un rapido riferimento.

`DataLabel` controlla l'aspetto delle etichette associate ai punti dati.

#### Risposta diretta
Abilita le etichette dati con `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` e stilale secondo necessità.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Imposta colore di riempimento delle barre up/down
#### Panoramica
Assegna alle barre up un riempimento verde e alle barre down un riempimento rosso per trasmettere intuitivamente il movimento del mercato.

L'oggetto `UpDownBars` fornisce l'accesso alla formattazione delle barre up e down.

#### Risposta diretta
Applica `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` e imposta il colore solido su `Color.GREEN`; ripeti per la barra down con `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Salva il file PowerPoint
#### Panoramica
Salva le tue modifiche in un nuovo file PPTX.

Il metodo `save` scrive la presentazione su disco nel formato specificato.

#### Risposta diretta
Chiama `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – questo scrive la presentazione modificata su disco nel formato standard di PowerPoint.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Problemi comuni e risoluzione

- **Il grafico non appare** – assicurati che le coordinate X/Y e le dimensioni del grafico siano entro i limiti della slide.  
- **Punti dati mancanti** – verifica che gli indici delle celle del workbook dei dati corrispondano alla serie/riga che intendi popolare.  
- **Eccezione di licenza** – una licenza di prova temporanea scade dopo 30 giorni; sostituiscila con una licenza permanente per le build di produzione.  
- **Rallentamento delle prestazioni su file grandi** – usa `Presentation.setCacheSize(0)` per disabilitare il caching se elabori migliaia di slide in batch.

## Domande frequenti

**Q: Posso usare questo codice in un'applicazione web?**  
A: Sì. La libreria è pure Java, quindi puoi eseguirla in qualsiasi contenitore servlet o servizio Spring Boot.

**Q: Aspose.Slides supporta altri tipi di grafico oltre a Stock?**  
A: Assolutamente. Supporta oltre 70 tipi di grafico, inclusi Line, Bar, Pie e Radar.

**Q: Come aggiungere un titolo al grafico programmaticamente?**  
A: Usa `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` e poi formatta il titolo secondo necessità.

**Q: Esiste un limite al numero di punti dati per serie?**  
A: Praticamente, puoi aggiungere decine di migliaia di punti; l'uso della memoria scala linearmente e la libreria trasmette i dati per mantenere basso l'ingombro.

**Q: Quali coordinate Maven devo usare per l'ultima versione?**  
A: L'ultima versione è sempre disponibile sotto `com.aspose:aspose-slides:25.4` (o più recente) su Maven Central.

---

**Ultimo aggiornamento:** 2026-09-12  
**Testato con:** Aspose.Slides for Java 25.4  
**Autore:** Aspose

## Tutorial correlati

- [dipendenza maven aspose slides: aggiungi e configura grafici nelle presentazioni usando Aspose.Slides per Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Crea grafico PowerPoint Java – salva presentazioni con grafici usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Crea e formatta grafici PowerPoint Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}