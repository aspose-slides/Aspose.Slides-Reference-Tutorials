---
date: '2026-06-13'
description: Scopri come aggiungere Excel a PowerPoint e generare PowerPoint da Excel
  creando un grafico a torta dinamico con Aspose.Slides per Java.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Aggiungi Excel a PowerPoint: Presentazione dinamica con grafico a torta usando
  Aspose.Slides per Java'
url: /it/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aggiungi Excel a PowerPoint: Presentazione dinamica con grafico a torta usando Aspose.Slides per Java

Nell'ambiente odierno guidato dai dati, **add Excel to PowerPoint** rapidamente e in modo affidabile così il tuo pubblico può vedere i numeri in formato visivo. Questo tutorial ti guida nella generazione di un PowerPoint da Excel, nella creazione di un grafico a torta con Java e nella configurazione dell'intervallo di dati del grafico — tutto con Aspose.Slides per Java. Alla fine avrai una presentazione pronta all'uso che estrae dati live direttamente da una cartella di lavoro Excel.

## Risposte rapide
- **Quale libreria crea grafici in Java?** Aspose.Slides for Java.  
- **Posso importare i dati di Excel direttamente in un grafico PowerPoint?** Sì – usa Aspose.Cells per leggere la cartella di lavoro e alimentarlo nel grafico.  
- **Quale tipo di grafico è dimostrato?** Un grafico a torta.  
- **Come imposto l'intervallo di dati per il grafico?** Chiamando `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **Qual è il vantaggio principale di questo approccio?** Automatizza il flusso di lavoro “add Excel to PowerPoint”, eliminando il copia‑incolla manuale.

## Cos'è **add Excel to PowerPoint**?
Aggiungere Excel a PowerPoint significa importare programmaticamente i dati del foglio di calcolo e visualizzarli all'interno di una presentazione. Questo consente di mantenere i dati di origine nel loro formato Excel nativo presentandoli come un grafico rifinito, garantendo che eventuali aggiornamenti alla cartella di lavoro siano riflessi immediatamente nella presentazione.

## Perché generare PowerPoint da Excel con Aspose.Slides per Java?
Generare PowerPoint da Excel con Aspose.Slides per Java ti consente di costruire presentazioni in pochi secondi, estraendo dati direttamente dal workbook senza copia‑incolla manuale. La libreria supporta oltre 50 formati di input e output, elabora cartelle di lavoro con centinaia di pagine senza caricare l'intero file in memoria e offre pieno controllo programmatico su stile del grafico, colori e intervalli di dati.

## Come generare PowerPoint da Excel usando Aspose.Slides per Java?
Carica la cartella di lavoro Excel con Aspose.Cells, crea una nuova `Presentation`, aggiungi una forma di grafico a torta a una diapositiva, quindi collega il grafico all'intervallo di dati del workbook. Con poche righe di codice Java puoi produrre un file `.pptx` completo che riflette i valori più recenti del foglio di calcolo.

## Come importare Excel in PowerPoint con Aspose.Slides?
L'importazione di Excel in PowerPoint avviene leggendo il file Excel in un oggetto `Workbook`, convertendo il workbook in un array di byte e passando quell'array al data source del grafico. Il grafico legge automaticamente l'intervallo specificato, mantenendo la visualizzazione sincronizzata con il foglio di calcolo.

## Come impostare l'intervallo di dati del grafico in Aspose.Slides per Java?
Usa il metodo `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` per puntare il grafico alle celle esatte che contengono le tue categorie e valori. Questa singola chiamata definisce sia la fonte dei dati sia il layout, eliminando la necessità di costruire manualmente le serie.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 1.8+** installato.
- **Aspose.Slides for Java** e **Aspose.Cells for Java** librerie (Maven, Gradle, o download diretto del JAR).
- Una cartella di lavoro Excel (`book1.xlsx`) contenente i dati che desideri visualizzare.
- Una licenza Aspose valida (la prova gratuita funziona per la valutazione).

### Librerie richieste
Avrai bisogno di Aspose.Slides e Aspose.Cells. Usa uno di questi strumenti di gestione delle dipendenze:

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

In alternativa, scarica i JAR direttamente da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
- **Prova gratuita:** disponibile sulla [pagina di download di Aspose](https://releases.aspose.com/slides/java/).  
- **Licenza temporanea:** per testare senza limitazioni di valutazione, richiedila su [pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licenza a pagamento:** per utilizzare i prodotti Aspose in produzione, acquista la licenza completa.

## Configurazione di Aspose.Slides per Java

Aggiungi la dipendenza Aspose.Slides al tuo progetto (vedi gli snippet Maven/Gradle sopra) e posiziona i file JAR nel classpath se non utilizzi uno strumento di build.

### Inizializzazione e configurazione di base
Importa la classe principale che rappresenta un file PowerPoint:  
```java
import com.aspose.slides.Presentation;
```  

## Guida all'implementazione

Di seguito trovi una guida passo‑a‑passo che copre **create pie chart java**, **set chart data range** e **add Excel to PowerPoint** in un unico flusso.

### Creare e aggiungere grafico alla presentazione

**Panoramica:** Inizializza una nuova presentazione, prendi la prima diapositiva e inserisci un grafico a torta.

#### Passo 1: Inizializzare la presentazione  
```java
Presentation pres = new Presentation();
```  
- **Scopo:** Crea un file PowerPoint vuoto in memoria.

#### Passo 2: Accedere alla prima diapositiva  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **Spiegazione:** Recupera la prima diapositiva creata automaticamente.

#### Passo 3: Aggiungere grafico a torta alla diapositiva  
L'oggetto `IChart` rappresenta una forma di grafico su una diapositiva.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **Parametri:** Posizione (`x`, `y`) e dimensione (`width`, `height`).  
- **Scopo:** Posiziona una forma di grafico a torta sulla diapositiva.

### Caricare la cartella di lavoro da file

**Panoramica:** Carica la cartella di lavoro Excel che contiene i dati per il grafico.

#### Passo 1: Definire la directory del documento  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- Imposta questo percorso sulla cartella contenente `book1.xlsx`.

#### Passo 2: Aprire la cartella di lavoro  
La classe `Workbook` di Aspose.Cells carica un file Excel in memoria.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **Scopo:** Legge il file Excel in memoria.

### Salvare la cartella di lavoro in ByteArrayOutputStream

**Panoramica:** Converti la cartella di lavoro in un array di byte affinché Aspose.Slides possa consumarlo.

#### Passo 1: Creare ByteArrayOutputStream  
`ByteArrayOutputStream` fornisce un buffer in‑memoria per dati binari.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **Scopo:** Fornisce uno stream in‑memoria per l'archiviazione temporanea.

#### Passo 2: Salvare la cartella di lavoro nello stream  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **Spiegazione:** Scrive la cartella di lavoro come stream di byte XLSX.

### Scrivere i dati della cartella di lavoro nel grafico

**Panoramica:** Alimenta l'array di byte Excel nel grafico come sua fonte dati.

#### Passo 1: Alimentare i dati nel grafico  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **Scopo:** Collega il grafico ai dati Excel.

### Impostare l'intervallo di dati del grafico e configurare le serie

**Panoramica:** Definisci quali celle il grafico deve leggere e migliora lo stile visivo.

#### Passo 1: Definire l'intervallo di dati  
Il metodo `setRange` definisce le celle Excel usate come fonte dati del grafico.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **Spiegazione:** Punta il grafico all'intervallo esatto su *Sheet2*.

#### Passo 2: Configurare le proprietà della serie  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **Scopo:** Abilita colori diversi per ogni fetta del grafico a torta.

### Salvare la presentazione su file

**Panoramica:** Persiste la presentazione completata su disco.

#### Passo 1: Definire il percorso di output  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- Scegli una cartella dove desideri il file PowerPoint finale.

#### Passo 2: Salvare la presentazione  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **Spiegazione:** Scrive la presentazione come file `.pptx`.

## Applicazioni pratiche

1. **Reporting aziendale:** trasformare i fogli di calcolo delle vendite mensili in presentazioni raffinate con un solo comando.  
2. **Strumenti educativi:** mostrare suddivisioni statistiche per presentazioni in aula senza creare grafici manualmente.  
3. **Integrazione dashboard:** automatizzare la generazione di dashboard basate su slide che estraggono dati live dalle cartelle di lavoro Excel.

## Considerazioni sulle prestazioni

- **Gestione della memoria:** avvolgere gli stream in try‑with‑resources o chiuderli in un blocco `finally` per evitare perdite.  
- **Set di dati grandi:** elaborare i dati a blocchi o usare `Workbook.getWorksheets().clear()` dopo aver estratto i valori necessari.  
- **Caricamento pigro:** caricare la cartella di lavoro solo quando è necessario popolare il grafico, non all'avvio dell'applicazione.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Chart shows no data** | Verifica che la stringa dell'intervallo corrisponda esattamente al nome del foglio e agli indirizzi delle celle (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Usa `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` per garantire che lo stream venga rilasciato prontamente. |
| **License not applied** | Carica la licenza prima che qualsiasi classe Aspose venga istanziata: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Domande frequenti

**Q: Posso usare Aspose.Slides senza una licenza?**  
A: Sì, ma la modalità di valutazione aggiunge filigrane e limita alcune funzionalità. Per la produzione, ottieni una licenza temporanea o completa.

**Q: Come gestire presentazioni di grandi dimensioni in Aspose.Slides?**  
A: Usa una gestione efficiente delle risorse, suddividi la presentazione in parti più piccole e disponi prontamente degli oggetti non più utilizzati.

**Q: In quali formati può esportare Aspose.Slides?**  
A: PPTX, PDF, XPS, ODP, HTML e formati immagine come PNG, JPEG e BMP.

**Q: È possibile aggiornare un file PowerPoint esistente invece di crearne uno nuovo?**  
A: Assolutamente. Carica un file esistente con `new Presentation("existing.pptx")`, modifica diapositive/grafici, quindi salva.

**Q: La libreria supporta l'impostazione di colori personalizzati per singole fette di torta?**  
A: Sì – dopo aver recuperato la serie, puoi impostare `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` e assegnare un `Color`.

## Risorse
- **Documentazione:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **Acquista licenza:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Prova gratuita:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licenza temporanea:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**Last Updated:** 2026-06-13  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come aggiornare l'intervallo dati del grafico PowerPoint usando Aspose.Slides per Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [Come aggiungere un grafico a torta PowerPoint con Aspose.Slides per Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}