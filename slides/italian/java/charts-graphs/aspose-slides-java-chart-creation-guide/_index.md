---
date: '2026-06-03'
description: Scopri come creare un grafico a colonne raggruppate in Java usando Aspose.Slides.
  Questa guida copre la dipendenza Maven, i passaggi per la creazione del grafico
  e la gestione dei dati.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Creare un grafico a colonne raggruppate in Java con Aspose.Slides
url: /it/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea un grafico a colonne raggruppate in Java con Aspose.Slides

## Come creare un grafico in Java: Introduzione
Creare presentazioni dinamiche spesso richiede la visualizzazione dei dati tramite grafici. Con **Aspose.Slides for Java**, puoi creare facilmente oggetti **grafico a colonne raggruppate**, migliorare la chiarezza e avere un impatto più forte sul tuo pubblico. Questo tutorial ti guida attraverso l'installazione della libreria, l'aggiunta di un grafico a colonne raggruppate, la gestione delle serie e l'inversione condizionale dei punti dati negativi.

**Cosa imparerai**
- Come configurare Aspose.Slides for Java.  
- Passaggi per **creare un grafico a colonne raggruppate** nella tua presentazione.  
- Tecniche per gestire le serie del grafico e i punti dati.  
- Metodi per invertire condizionalmente i punti dati negativi per una migliore visualizzazione.  
- Come salvare la presentazione in modo sicuro.

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.Slides for Java.  
- **Quale tipo di grafico è dimostrato?** Grafico a colonne raggruppate.  
- **Posso invertire i valori negativi?** Sì, usando `invertIfNegative`.  
- **Quale versione di Java è richiesta?** JDK 16 o successiva.  
- **È necessaria una licenza per la produzione?** Sì, una licenza Aspose valida.

## Che cos'è un grafico a colonne raggruppate?
Un grafico a colonne raggruppate è una rappresentazione visiva che posiziona più serie di dati affiancate per ogni categoria, consentendo un rapido confronto tra gruppi. È perfetto per report finanziari, dashboard di vendite e qualsiasi scenario in cui è necessario confrontare più metriche contemporaneamente.

## Perché usare Aspose.Slides per la creazione di grafici?
Aspose.Slides ti permette di generare e personalizzare completamente i grafici in modo programmatico, eliminando la necessità di modifiche manuali in PowerPoint. Supporta **oltre 70 formati di input e output** e può elaborare presentazioni con **fino a 10.000 di diapositive** senza caricare l'intero file in memoria, garantendo alte prestazioni per report su larga scala.

## Prerequisiti
1. **Librerie richieste**  
   - Aspose.Slides for Java (versione 25.4 o successiva).  

2. **Ambiente**  
   - JDK 16 o più recente.  
   - Maven o Gradle per la gestione delle dipendenze.  

3. **Conoscenze**  
   - Programmazione Java di base.  
   - Familiarità con gli strumenti di build (Maven/Gradle).  

## Configurare Aspose.Slides for Java
### Installazione con Maven
Aggiungi la seguente dipendenza al tuo file `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installazione con Gradle
Aggiungi la seguente riga al tuo file `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
- **Prova gratuita:** Esplora le funzionalità senza una licenza.  
- **Licenza temporanea:** Utilizzala durante la valutazione.  
- **Licenza completa:** Acquista per le distribuzioni in produzione.

### Inizializzazione di base
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Come aggiungere un grafico a colonne raggruppate a una diapositiva?
`Presentation` è la classe principale che rappresenta un file PowerPoint. Carica una nuova `Presentation`, aggiungi una diapositiva e chiama `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Questa singola chiamata crea un grafico a colonne raggruppate completamente funzionale posizionato alle coordinate specificate. Puoi quindi accedere all'oggetto chart per modificare serie, punti dati e stili visivi.

## Guida passo‑passo

### Passo 1: Creare una presentazione e aggiungere un grafico a colonne raggruppate
La classe `Presentation` rappresenta un documento PowerPoint e consente di creare diapositive.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Passo 2: Gestire le serie del grafico
Ora cancelleremo eventuali serie predefinite, ne aggiungeremo una nuova e la popoleremo con valori sia positivi che negativi.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Passo 3: Invertire i punti dati negativi in modo condizionale
Il metodo `invertIfNegative` consente l'inversione dei valori negativi in una serie di grafico.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Problemi comuni e consigli
- **Hai dimenticato di liberare l'oggetto `Presentation`?** Chiama sempre `dispose()` in un blocco `finally` per liberare le risorse native.  
- **I valori negativi non vengono mostrati invertiti?** Assicurati di chiamare `invertIfNegative(true)` **dopo** aver aggiunto il punto dati.  
- **Problemi di dimensione del grafico:** Le coordinate (X, Y) e le dimensioni (larghezza, altezza) sono espresse in punti; adattale al layout della tua diapositiva.  

## Domande frequenti

**D:** Posso creare altri tipi di grafico con lo stesso approccio?  
**R:** Sì, basta sostituire `ChartType.ClusteredColumn` con qualsiasi altro valore dell'enum `ChartType` (ad es., `Line`, `Pie`).  

**D:** È necessaria una licenza per le build di sviluppo?  
**R:** È richiesta una licenza temporanea o di valutazione per accedere a tutte le funzionalità; altrimenti, la libreria funziona in modalità trial con limitazioni di watermark.  

**D:** Come esportare la presentazione in PDF dopo aver aggiunto i grafici?  
`SaveFormat.Pdf` specifica il PDF come formato di output per il salvataggio di una presentazione. Usa `pres.save("output.pdf", SaveFormat.Pdf);` dopo aver terminato la manipolazione del grafico.  

**D:** È possibile formattare singole colonne (colore, bordo)?  
`IChartDataPoint` rappresenta un singolo punto dati in un grafico e consente la formattazione. Ogni `IChartDataPoint` offre opzioni come `getFillFormat().setFillType(FillType.Solid)` e `getLineFormat()`.  

**D:** Cosa fare se devo aggiornare i dati del grafico dopo aver salvato la presentazione?  
**R:** Ricarica la presentazione con `new Presentation("file.pptx")`, modifica i dati del grafico e salva nuovamente.

---

**Ultimo aggiornamento:** 2026-06-03  
**Testato con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autore:** Aspose

## Tutorial correlati

- [How to create stacked column chart in Java with Aspose.Slides – A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [How to Create Chart in Java with Aspose.Slides – Mastering Chart Creation and Validation](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Create & Format Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}