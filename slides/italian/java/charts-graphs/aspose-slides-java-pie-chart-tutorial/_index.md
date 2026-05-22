---
date: '2026-03-02'
description: Scopri come aggiungere Excel a PowerPoint e generare PowerPoint da Excel
  creando un grafico a torta dinamico con Aspose.Slides per Java.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'Aggiungi Excel a PowerPoint: presentazione dinamica con grafico a torta usando
  Aspose.Slides per Java'
url: /it/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aggiungi Excel a PowerPoint: Presentazione dinamica con grafico a torta usando Aspose.Slides per Java

Nell'ambiente odierno guidato dai dati, **add Excel to PowerPoint** rapidamente e in modo affidabile così il tuo pubblico può vedere i numeri in formato visuale. Questo tutorial ti guida nella generazione di un PowerPoint da Excel, nella creazione di un grafico a torta con Java e nella configurazione dell'intervallo di dati del grafico — tutto con Aspose.Slides per Java. Alla fine avrai una presentazione pronta all'uso che estrae dati in tempo reale direttamente da una cartella di lavoro Excel.

## Risposte rapide
- **Quale libreria crea grafici in Java?** Aspose.Slides for Java.
- **Posso estrarre i dati di Excel direttamente in un grafico PowerPoint?** Sì – usa Aspose.Cells per leggere la cartella di lavoro e fornirla al grafico.
- **Quale tipo di grafico è dimostrato?** Un grafico a torta.
- **Come imposto l'intervallo di dati per il grafico?** Chiamando `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **Qual è il beneficio principale di questo approccio?** Automatizza il flusso di lavoro “add Excel to PowerPoint”, eliminando il copia‑incolla manuale.

## Cos'è **add Excel to PowerPoint**?
Aggiungere Excel a PowerPoint significa importare programmaticamente i dati di un foglio di calcolo e visualizzarli all'interno di una presentazione. Con Aspose.Slides e Aspose.Cells, puoi leggere qualsiasi file Excel, mappare le celle alle serie del grafico e produrre una presentazione curata senza mai aprire manualmente PowerPoint.

## Perché generare PowerPoint da Excel con Aspose.Slides per Java?
- **Velocità:** Crea report in pochi secondi, non minuti.
- **Precisione:** I dati vengono letti direttamente dalla cartella di lavoro di origine, eliminando errori di trascrizione.
- **Flessibilità:** Personalizza colori, stili e intervalli di dati del grafico al volo.
- **Scalabilità:** Integra nei lavori batch, servizi web o pipeline di reportistica programmata.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK) 1.8+** installato.
- Librerie **Aspose.Slides for Java** e **Aspose.Cells for Java** (Maven, Gradle o download diretto del JAR).
- Una cartella di lavoro Excel (`book1.xlsx`) contenente i dati che desideri visualizzare.
- Una licenza Aspose valida (la versione di prova gratuita funziona per la valutazione).

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
- **Prova gratuita:** Disponibile sulla [pagina di download di Aspose](https://releases.aspose.com/slides/java/).  
- **Licenza temporanea:** Per testare senza limitazioni di valutazione, richiedila su [pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licenza d'acquisto:** Per utilizzare i prodotti Aspose in produzione, acquista la licenza completa.

## Configurazione di Aspose.Slides per Java

Aggiungi la dipendenza Aspose.Slides al tuo progetto (vedi gli snippet Maven/Gradle sopra) e posiziona i file JAR nel tuo classpath se non utilizzi uno strumento di build.

### Inizializzazione e configurazione di base
Importa la classe principale che rappresenta un file PowerPoint:
```java
import com.aspose.slides.Presentation;
```

## Guida all'implementazione

Di seguito trovi una guida passo‑passo che copre **create pie chart java**, **set chart data range** e **add Excel to PowerPoint** in un unico flusso.

### Creare e aggiungere un grafico alla presentazione

**Panoramica:** Inizializza una nuova presentazione, ottieni la prima diapositiva e inserisci un grafico a torta.

#### Passo 1: Inizializza la presentazione
```java
Presentation pres = new Presentation();
```
- **Scopo:** Crea un file PowerPoint vuoto in memoria.

#### Passo 2: Accedi alla prima diapositiva
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **Spiegazione:** Recupera la prima diapositiva creata automaticamente.

#### Passo 3: Aggiungi un grafico a torta alla diapositiva
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **Parametri:** Posizione (`x`, `y`) e dimensione (`width`, `height`).  
- **Scopo:** Posiziona una forma di grafico a torta sulla diapositiva.

### Caricare la cartella di lavoro da file

**Panoramica:** Carica la cartella di lavoro Excel che contiene i dati per il grafico.

#### Passo 1: Definisci la directory del documento
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- Imposta questo al percorso della cartella contenente `book1.xlsx`.

#### Passo 2: Apri la cartella di lavoro
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **Scopo:** Legge il file Excel in memoria.

### Salva la cartella di lavoro in ByteArrayOutputStream

**Panoramica:** Converte la cartella di lavoro in un array di byte affinché Aspose.Slides possa utilizzarlo.

#### Passo 1: Crea ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **Scopo:** Fornisce uno stream in memoria per l'archiviazione temporanea.

#### Passo 2: Salva la cartella di lavoro nello stream
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **Spiegazione:** Scrive la cartella di lavoro come stream di byte XLSX.

### Scrivi i dati della cartella di lavoro nel grafico

**Panoramica:** Fornisci l'array di byte Excel al grafico come sua fonte dati.

#### Passo 1: Fornisci i dati al grafico
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **Scopo:** Collega il grafico ai dati Excel.

### Imposta l'intervallo di dati del grafico e configura le serie

**Panoramica:** Definisci quali celle il grafico deve leggere e migliora lo stile visivo.

#### Passo 1: Definisci l'intervallo di dati
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **Spiegazione:** Indica al grafico l'intervallo esatto su *Sheet2*.

#### Passo 2: Configura le proprietà della serie
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **Scopo:** Abilita colori diversi per ogni fetta del grafico a torta.

### Salva la presentazione su file

**Panoramica:** Salva la presentazione completata su disco.

#### Passo 1: Definisci il percorso di output
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- Scegli una cartella dove desideri il file PowerPoint finale.

#### Passo 2: Salva la presentazione
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **Spiegazione:** Scrive la presentazione come file `.pptx`.

## Applicazioni pratiche

1. **Reportistica aziendale:** Trasforma i fogli di calcolo delle vendite mensili in presentazioni curate con un solo comando.  
2. **Strumenti educativi:** Mostra suddivisioni statistiche per presentazioni in classe senza creare manualmente i grafici.  
3. **Integrazione dashboard:** Automatizza la generazione di dashboard basate su slide che estraggono dati in tempo reale dalle cartelle di lavoro Excel.

## Considerazioni sulle prestazioni

- **Gestione della memoria:** Avvolgi gli stream in try‑with‑resources o chiudili in un blocco `finally` per evitare perdite.  
- **Set di dati grandi:** Elabora i dati a blocchi o usa `Workbook.getWorksheets().clear()` dopo aver estratto i valori necessari.  
- **Caricamento pigro:** Carica la cartella di lavoro solo quando è necessario popolare il grafico, non all'avvio dell'applicazione.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Il grafico non mostra dati** | Verifica che la stringa dell'intervallo corrisponda esattamente al nome del foglio e agli indirizzi delle celle (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | Usa `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` per garantire il rilascio rapido dello stream. |
| **Licenza non applicata** | Carica la licenza prima di istanziare qualsiasi classe Aspose: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Domande frequenti

**D: Posso usare Aspose.Slides senza licenza?**  
R: Sì, ma la modalità di valutazione aggiunge filigrane e limita alcune funzionalità. Per la produzione, ottieni una licenza temporanea o completa.

**D: Come gestisco presentazioni di grandi dimensioni in Aspose.Slides?**  
R: Usa una gestione efficiente delle risorse, suddividi la presentazione in parti più piccole e disponi prontamente degli oggetti non utilizzati.

**D: In quali formati di file può esportare Aspose.Slides?**  
R: PPTX, PDF, XPS, ODP, HTML e formati immagine come PNG, JPEG e BMP.

**D: È possibile aggiornare un file PowerPoint esistente invece di crearne uno nuovo?**  
R: Assolutamente. Carica un file esistente con `new Presentation("existing.pptx")`, modifica diapositive/grafici, quindi salva.

**D: La libreria supporta l'impostazione di colori personalizzati per singole fette di torta?**  
R: Sì – dopo aver recuperato la serie, puoi impostare `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` e assegnare un `Color`.

## Risorse
- **Documentazione:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **Acquista licenza:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **Prova gratuita:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licenza temporanea:** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---

**Ultimo aggiornamento:** 2026-03-02  
**Testato con:** Aspose.Slides 25.4 per Java (JDK 16) & Aspose.Cells 25.4  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}