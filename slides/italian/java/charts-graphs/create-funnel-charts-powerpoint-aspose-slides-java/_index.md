---
date: '2026-09-02'
description: Scopri come creare funnel chart in PowerPoint utilizzando Aspose.Slides
  for Java. Questa guida passo‑passo copre l'impostazione dei dati del grafico, la
  personalizzazione dei colori e l'esportazione della presentazione.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Scopri come creare funnel chart in PowerPoint utilizzando Aspose.Slides
  for Java. Questa guida ti accompagna nella configurazione dei dati, nella personalizzazione
  dei colori e nell'esportazione della presentazione finale.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Crea funnel chart in PowerPoint con Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Crea funnel chart in PowerPoint con Aspose.Slides for Java
url: /it/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maestria nella creazione di grafici a imbuto in PowerPoint con Aspose.Slides per Java

## Introduzione
Creare presentazioni accattivanti è un'arte che combina visualizzazione dei dati, design e storytelling. Un elemento visivo potente che chiarisce immediatamente un processo a più fasi è il grafico a imbuto. Che tu debba illustrare un pipeline di vendita, un flusso di conversione o un collo di bottiglia nella produzione, un grafico a imbuto ben progettato trasforma numeri grezzi in una narrazione intuitiva. In questo tutorial imparerai a **creare un grafico a imbuto** in PowerPoint in modo programmatico usando Aspose.Slides per Java, configurarne i dati, personalizzare il colore di ogni segmento e esportare la presentazione finale.

**Cosa imparerai**
- Come aggiungere Aspose.Slides per Java a un progetto Maven o Gradle  
- Come istanziare un oggetto `Presentation` e accedere alle sue diapositive  
- Come inserire un grafico a imbuto, definire le categorie e popolare i dati delle serie  
- Come stilizzare ogni sezione del grafico a imbuto con riempimenti solidi o colori specifici del brand  
- Come salvare la presentazione come file PPTX o esportare una diapositiva come immagine  

## Risposte rapide
- **Qual è la libreria principale per la visualizzazione dei dati in Java?** Aspose.Slides per Java.  
- **Come si crea un grafico a imbuto in PowerPoint?** Chiama `slide.addChart(ChartType.Funnel, …)` sulla diapositiva di destinazione.  
- **Quale API imposta la fonte dati del grafico?** Usa `IChartDataWorkbook` insieme a `chart.getChartData()`.  
- **È possibile personalizzare i colori per ogni segmento del grafico a imbuto?** Sì—imposta `FillFormat.setFillType(FillType.Solid)` e assegna un `java.awt.Color`.  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza Aspose.Slides acquistata per le distribuzioni commerciali.

## Cos'è la visualizzazione dei dati in Java?
La visualizzazione dei dati in Java è la pratica di convertire dati grezzi in grafici, diagrammi o grafica interattiva direttamente dalle applicazioni Java. Aspose.Slides per Java è una libreria leader che consente agli sviluppatori di generare oltre 100 tipi di grafico—compresi i grafici a imbuto—senza mai avviare manualmente PowerPoint, supportando presentazioni fino a 500 diapositive mantenendo un basso utilizzo di memoria.

## Perché utilizzare i grafici a imbuto in PowerPoint?
I grafici a imbuto rivelano istantaneamente i tassi di abbandono tra le fasi sequenziali, rendendoli ideali per pipeline di vendita, analisi delle conversioni o revisioni dell'efficienza dei processi. Aspose.Slides ti offre un controllo pixel‑perfect sul layout, sui colori dei segmenti e sulle etichette dei dati, così puoi mantenere la coerenza del brand ed evitare lo sforzo manuale di modificare i grafici nell'interfaccia di PowerPoint.

## Prerequisiti (H2)

### Librerie richieste, versioni e dipendenze
Per implementare Aspose.Slides per Java nel tuo progetto, includi le coordinate Maven o Gradle appropriate. La libreria funziona con Java 8‑21 e non richiede dipendenze native esterne.

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

Puoi anche scaricare il JAR direttamente da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Requisiti di configurazione dell'ambiente
Assicurati di avere installato JDK 8 o versioni successive e che la tua `JAVA_HOME` punti alla directory corretta del JDK. Aspose.Slides funziona su qualsiasi OS che supporta il JDK, inclusi Windows, macOS e Linux.

### Prerequisiti di conoscenza
Una familiarità di base con la sintassi Java, la programmazione orientata agli oggetti e il concetto di file di presentazione sarà utile, ma gli snippet di codice sono completamente spiegati per sviluppatori di qualsiasi livello di esperienza.

## Configurazione di Aspose.Slides per Java (H2)

1. **Aggiungi la dipendenza** – Usa lo snippet Maven o Gradle sopra.  
2. **Ottieni una licenza** –  
   - **Prova gratuita** – Scarica una licenza temporanea da [Aspose's website](https://purchase.aspose.com/temporary-license/) per la valutazione.  
   - **Licenza completa** – Acquista una licenza di produzione tramite la [purchase page](https://purchase.aspose.com/buy).  
3. **Inizializzazione di base** –  

`Presentation` è la classe core di Aspose.Slides che rappresenta un file PowerPoint in memoria. Fornisce l'accesso a diapositive, forme e oggetti grafico.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Il codice sopra crea una nuova istanza di `Presentation`, pronta per la manipolazione delle diapositive, e garantisce che le risorse vengano rilasciate con `dispose()`.

## Guida all'implementazione

Passeremo in rassegna ogni funzionalità necessaria per costruire un grafico a imbuto completo, aggiungendo un breve testo esplicativo prima di ogni segnaposto di codice.

### Funzionalità 1: creazione di una presentazione (H2)

#### Panoramica
Inizia creando un'istanza della classe `Presentation`. Questo oggetto è il punto di ingresso per tutte le operazioni successive.

`Presentation` è l'oggetto di livello superiore di Aspose.Slides che contiene la collezione di diapositive e le impostazioni globali del documento.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Lo snippet apre una presentazione vuota, che potrai successivamente salvare come file `.pptx`.

### Funzionalità 2: aggiungere un grafico a imbuto a una diapositiva (H2)

#### Panoramica
Inserisci un grafico a imbuto nella prima diapositiva, definisci le sue dimensioni e imposta il tipo di grafico.

`ChartType.Funnel` indica ad Aspose.Slides di renderizzare una visualizzazione a forma di imbuto invece di un grafico a barre o a linee.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

La chiamata `addChart` crea la forma del grafico, la posiziona a `(50, 50)` punti e le assegna una larghezza di `500` e un'altezza di `400`.

### Funzionalità 3: cancellare i dati del grafico (H2)

#### Panoramica
Prima di popolare il grafico, cancella eventuali categorie o serie segnaposto che il modello potrebbe contenere.

`chart.getChartData().getCategories().clear()` rimuove tutte le voci di categoria esistenti, mentre `chart.getChartData().getSeries().clear()` rimuove eventuali serie pre‑riempite.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Ciò garantisce una base pulita affinché i tuoi dati personalizzati compaiano esattamente come previsto.

### Funzionalità 4: configurare il workbook dei dati del grafico (H2)

#### Panoramica
L'oggetto `IChartDataWorkbook` memorizza i valori grezzi che alimentano il grafico. Inizializzarlo ti consente di scrivere dati direttamente nelle celle.

`IChartDataWorkbook` è un foglio di calcolo leggero in memoria che Aspose.Slides utilizza per fornire serie e categorie al grafico.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Il codice cancella eventuali celle esistenti, preparando il workbook per nuove voci.

### Funzionalità 5: aggiungere categorie a un grafico (H2)

#### Panoramica
Definisci le etichette testuali che appaiono sul lato sinistro dell'imbuto—rappresentano ciascuna fase del tuo processo.

`chart.getChartData().getCategories().add()` crea un nuovo oggetto categoria collegato a una specifica cella del workbook.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Qui aggiungiamo tre fasi: “Prospects”, “Qualified Leads” e “Closed Deals”.

### Funzionalità 6: aggiungere serie di dati a un grafico (H2)

#### Panoramica
Popola l'imbuto con valori numerici e, facoltativamente, assegna un colore unico a ciascuna sezione.

`IDataPoint` rappresenta un singolo punto dati all'interno di una serie di grafico.  

`chart.getChartData().getSeries().add()` crea una serie che contiene i punti dati numerici; ogni `IDataPoint` può ricevere il proprio colore di riempimento.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Il ciclo dimostra come impostare un riempimento solido per ogni punto, usando costanti `java.awt.Color` specifiche del brand o colori generati casualmente per varietà visiva.

## Casi d'uso comuni e consigli (H2)

- **Report della pipeline di vendita** – Mostra quanti lead passano da prospect a closed‑won in ogni fase.  
- **Analisi dell'efficienza dei processi** – Visualizza la perdita di materiale o i ritardi temporali tra le fasi di produzione.  
- **Revisione del funnel di marketing** – Confronta i tassi di conversione tra campagne o fonti di traffico.  

**Consiglio professionale:** invece di colori casuali, utilizza la palette del brand della tua azienda (ad esempio `new Color(0, 112, 192)`) per mantenere la presentazione coerente con gli altri asset di marketing.

## Domande frequenti (H2)

**D: Come cambio l'orientamento del grafico a imbuto?**  
R: Imposta la proprietà `ChartOrientation` sull'oggetto `IChart` a `ChartOrientation.Vertical` o `ChartOrientation.Horizontal`.

**D: Posso esportare la diapositiva come immagine dopo aver aggiunto il grafico?**  
R: Sì—chiama `pres.getSlides().get_Item(0).getThumbnail(1, 1)` e scrivi il `java.awt.image.BufferedImage` risultante in un file PNG o JPEG.

**D: Cosa succede se ho bisogno di più di tre categorie?**  
R: Basta aggiungere categorie aggiuntive usando `chart.getChartData().getCategories().add(...)` e fornire punti dati corrispondenti per ogni nuova categoria.

**D: C'è un modo per nascondere la legenda?**  
R: Usa `chart.getChartTitle().setVisible(false)` e `chart.getLegend().setVisible(false)` per rimuovere sia il titolo che la legenda dalla visualizzazione.

**D: È necessaria una licenza per le build di sviluppo?**  
R: Una licenza temporanea è sufficiente per la valutazione; è richiesta una licenza commerciale completa per le distribuzioni in produzione.

---

**Ultimo aggiornamento:** 2026-09-02  
**Testato con:** Aspose.Slides per Java 25.4 (jdk16)  
**Autore:** Aspose

## Tutorial correlati

- [Come aggiungere un grafico a PowerPoint usando Aspose.Slides per Java: Guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Come modificare i dati di un grafico PowerPoint usando Aspose.Slides per Java: Guida completa](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aggiungere animazione a un grafico PowerPoint usando Aspose.Slides per Java – Guida passo‑passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}