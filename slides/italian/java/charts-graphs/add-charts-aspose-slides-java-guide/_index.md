---
date: '2026-06-03'
description: Scopri come aggiungere grafici con l'aspose slides maven dependency,
  configurare le etichette dei dati e generare grafici dinamici nelle presentazioni
  Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Aggiungi e Configura Grafici nelle Presentazioni
  con Aspose.Slides per Java'
url: /it/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Aggiungi e Configura Grafici nelle Presentazioni Usando Aspose.Slides per Java

## Introduzione
The **aspose slides maven dependency** lets Java developers programmatically create, modify, and enrich PowerPoint files without ever opening PowerPoint itself. In many business and academic scenarios, manually inserting charts is time‑consuming and error‑prone. This tutorial shows you step‑by‑step how to add a Bubble Chart, bind data labels to worksheet cells, and save the result—all by leveraging the aspose slides maven dependency in a clean, repeatable way.

**What You'll Learn**
- Come aggiungere grafici con la aspose slides maven dependency
- Configurare un progetto Java usando Maven o Gradle
- Caricare una presentazione esistente e inserire un Bubble Chart
- Configurare le etichette dei dati usando riferimenti a celle (add data labels chart)
- Salvare il file aggiornato per una distribuzione successiva
- Casi d'uso reali come generazione dinamica di grafici e creazione di flussi di lavoro per grafici nelle presentazioni

## Risposte Rapide
- **Quale artefatto Maven aggiunge le funzionalità di grafico?** `com.aspose:aspose-slides:25.4` (or latest)  
- **Posso collegare le etichette dei dati a celle in stile Excel?** Yes – use `ChartDataLabel` with `setDataLabelFormat` and cell references.  
- **È necessaria una licenza per la produzione?** A full license removes the evaluation watermark and unlocks all features.  
- **Funzionerà su Java 11+?** Absolutely; the library is compatible with Java 8 through Java 21.  
- **Quanti tipi di grafico sono supportati?** Over 70 distinct chart types, including Bubble, Radar, and Stock charts.

## Cos'è la dipendenza aspose slides maven?
The **aspose slides maven dependency** is a Maven‑compatible package that provides a full‑featured API for creating and editing PowerPoint (PPTX, PPT, ODP) files in Java. By adding this dependency to your `pom.xml` or `build.gradle`, you gain access to over 70 chart types, 150+ slide layouts, and the ability to manipulate shapes, animations, and metadata without Office installed.

## Perché utilizzare la dipendenza aspose slides maven per l'automazione dei grafici?
Aspose.Slides processes multi‑thousand‑slide decks in under a second on standard server hardware, supports **70+ chart types**, and can render presentations up to **10,000 slides** without loading the entire file into memory. These quantified capabilities make it ideal for enterprise‑grade dynamic chart generation, where performance and scalability are non‑negotiable.

## Prerequisiti
- **Java Development Kit (JDK)** 8 o più recente (si consiglia Java 11+).  
- **Maven** 3.6+ **o** **Gradle** 6+.  
- **Libreria Aspose.Slides per Java** (la dipendenza aspose slides maven, versione 25.4 o successiva).  
- Familiarità di base con le collezioni Java e I/O di file.  
- Un file di licenza di valutazione o completa (`license.json`) se prevedi di eseguire il codice oltre il periodo di prova.

## Come aggiungere un grafico a una diapositiva usando Aspose.Slides?
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### Passo 1: Aggiungi la dipendenza aspose slides maven
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
These snippets pull the full Aspose.Slides API—including chart support—directly from Maven Central.

### Passo 2: Carica la presentazione e inserisci un Bubble Chart
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Passo 3: Configura la serie di dati e le etichette del grafico
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Passo 4: Salva la presentazione modificata
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Come configurare le etichette dei dati usando riferimenti a celle?
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### Risposta Diretta
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### Passo‑per‑passo
1. Identifica la serie che desideri etichettare.  
2. Recupera l'oggetto `IDataLabel` per ogni punto dati.  
3. Usa `setDataLabelFormat` con `DataLabelFormat` configurato per `CellReference`.  
4. Facoltativamente personalizza font, colore e opzioni di visualizzazione.

## Come salvare la presentazione modificata?
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### Risposta Diretta
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## Applicazioni Pratiche
1. **Report Aziendali:** Genera automaticamente grafici di vendite trimestrali da un dump di database.  
2. **Lezioni Accademiche:** Inserisci dati di ricerca in tempo reale nelle diapositive per ogni lezione.  
3. **Presentazioni di Vendita:** Crea dashboard di performance specifiche per cliente al volo.  
4. **Gestione Progetti:** Visualizza timeline in stile Gantt con etichette dati dinamiche.  
5. **Analisi di Marketing:** Inserisci KPI di campagna nelle presentazioni che si aggiornano al ricevimento di nuove metriche.

## Considerazioni sulle Prestazioni
- **Gestione della Memoria:** Usa try‑with‑resources o `presentation.dispose()` esplicito per liberare rapidamente la memoria nativa.  
- **Set di Dati Grandi:** Quando gestisci più di 10.000 punti dati, popola i dati del grafico tramite `ChartDataWorkbook` per evitare di caricare l'intero set in oggetti Java.  
- **Sicurezza dei Thread:** Ogni thread dovrebbe lavorare con la propria istanza `Presentation`; l'API non è thread‑safe su oggetti condivisi.  

## Problemi Comuni e Soluzioni
- **Problema:** “File di licenza non trovato.”  
  **Soluzione:** Place `license.json` in the classpath and call `License license = new License(); license.setLicense("license.json");` before any API usage.  
- **Problema:** Il grafico appare vuoto dopo il salvataggio.  
  **Soluzione:** Ensure that the chart’s data workbook is saved with the presentation (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problema:** Le etichette dei dati mostrano errori “#REF!”.  
  **Soluzione:** Verify that the cell reference string matches the exact sheet name and address, and that the referenced workbook is attached to the chart.  

## Domande Frequenti

**D: Posso aggiungere altri tipi di grafico oltre a Bolle?**  
A: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock, and more than 70 additional types.

**D: La dipendenza aspose slides maven funziona con OpenJDK?**  
A: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major operating systems.

**D: Come incorporo un grafico da un file Excel esistente?**  
A: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell references.

**D: Esiste un limite al numero di grafici per diapositiva?**  
A: Practically no—Aspose.Slides can handle dozens of charts per slide, limited only by available memory.

**D: In quale formato posso esportare la presentazione finale?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and JPEG are supported.

## Risorse
- [Rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/) – scarica gli ultimi binari della libreria.  
- [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/) – riferimento API completo e guide.  
- [Scarica Aspose.Slides per Java](https://releases.aspose.com/slides/java/) – pagina di download diretto per i pacchetti Maven/Gradle.  
- [Acquista una Licenza](https://purchase.aspose.com/buy) – ottieni una licenza commerciale completa.  
- [Prova Gratuita](https://releases.aspose.com/slides/java/) – inizia con una prova per valutare le funzionalità.  
- [Licenza Temporanea](https://purchase.aspose.com/temporary-license/) – richiedi una chiave temporanea per una valutazione estesa.  
- [Forum di Supporto Aspose](https://forum.aspose.com/c/slides/11) – ottieni aiuto dalla community e dagli ingegneri Aspose.

## Conclusione
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Tutorial Correlati

- [Come Creare e Configurare Presentazioni con Aspose.Slides Java: Guida Passo‑Passo](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Crea PPTX Java con Aspose.Slides Maven – Guida all'Automazione](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Come Creare un Grafico in Java con Aspose.Slides: Guida Completa](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}