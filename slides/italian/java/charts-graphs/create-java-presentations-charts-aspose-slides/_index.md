---
date: '2026-03-20'
description: Scopri come aggiungere grafici alle presentazioni Java usando Aspose.Slides
  e genera rapidamente file di grafici per le presentazioni.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Come aggiungere un grafico alle presentazioni Java con Aspose.Slides
url: /it/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere un grafico a una presentazione usando Aspose.Slides per Java

## Introduzione

Creare presentazioni dinamiche che trasmettano efficacemente i dati è essenziale nell'attuale ambiente aziendale frenetico. Che tu stia preparando un rapporto finanziario, un deck di marketing o un aggiornamento sullo stato di un progetto, **sapere come aggiungere un grafico** alle tue diapositive può migliorare notevolmente il coinvolgimento del pubblico. In questo tutorial imparerai passo‑passo come aggiungere un grafico a colonne impilate 3D, configurarne i dati e salvare il file finale—tutto con Aspose.Slides per Java.

### Risposte rapide
- **Qual è la libreria principale?** Aspose.Slides per Java  
- **Quale tipo di grafico è dimostrato?** Colonna impilata 3D  
- **Posso generare file di grafici per presentazioni programmaticamente?** Sì, utilizzando i metodi API mostrati di seguito  
- **Quale versione di Java è consigliata?** JDK 16 o successiva  
- **È necessaria una licenza per la produzione?** È richiesta una licenza valida di Aspose.Slides per uso commerciale  

## Che cosa significa “come aggiungere un grafico” in Aspose.Slides?

Aspose.Slides per Java fornisce un ricco insieme di oggetti che consentono di creare, modificare ed esportare file PowerPoint senza Microsoft Office. Aggiungere un grafico è semplice come creare un oggetto `Presentation`, inserire una forma grafico e alimentarla con i dati tramite il workbook integrato.

## Perché aggiungere un grafico alle presentazioni Java?

- **Impatto visivo:** I grafici trasformano numeri grezzi in visualizzazioni immediatamente comprensibili.  
- **Automazione:** Genera report al volo—ideale per digest email programmati o dashboard.  
- **Coerenza:** Usa lo stesso stile e branding in tutti i deck generati.  
- **Portabilità:** Esporta in PPTX, PDF o immagini con una singola chiamata di metodo.

## Prerequisiti

- **Librerie e dipendenze:** Aspose.Slides per Java deve essere installato.  
- **Configurazione dell'ambiente:** Lavorare in un ambiente Java (JDK 16 o successivo consigliato).  
- **Base di conoscenza:** Familiarità con i concetti di programmazione Java di base sarà utile.

## Configurazione di Aspose.Slides per Java

### Installazione

Per integrare Aspose.Slides nel tuo progetto, segui una delle opzioni seguenti.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download diretto**: In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
- **Prova gratuita:** Inizia con una prova gratuita per esplorare le funzionalità.  
- **Licenza temporanea:** Ottieni una licenza temporanea per test più estesi.  
- **Acquisto:** Acquista una licenza completa per uso commerciale.

Una volta installato, puoi istanziare la classe `Presentation`, che funge da punto di ingresso per tutte le operazioni relative ai grafici.

## Guida all'implementazione

### Come aggiungere un grafico a una presentazione con una colonna impilata 3D

#### Panoramica
Creare una presentazione da zero è semplice con Aspose.Slides. In questa sezione aggiungeremo un grafico a colonne impilate 3D alla prima diapositiva della nostra presentazione.

**Passaggi:**

1. **Inizializzare l'oggetto Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Spiegare i parametri**  
   - `ChartType.StackedColumn3D`: Specifica il tipo di grafico.  
   - Posizione e dimensione `(0, 0, 500, 500)`: Determina dove il grafico appare sulla diapositiva.

### Configurare i dati del grafico

#### Panoramica
Per rendere il grafico significativo, configura le serie di dati e le categorie. Questa sezione dimostra come aggiungere punti dati specifici al tuo grafico.

**Passaggi:**

1. **Accedere al workbook dei dati del grafico**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Impostare le proprietà Rotation3D per il grafico

#### Panoramica
Migliora l'appeal visivo del tuo grafico con le proprietà di rotazione 3D. Questa personalizzazione ti permette di regolare la prospettiva e la profondità.

**Passaggi:**

1. **Configurare le rotazioni 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Spiegare i parametri**  
   - `setRightAngleAxes(true)`: Garantisce che gli assi siano perpendicolari.  
   - Valori di rotazione: Regola l'angolo e la profondità della vista 3D.

### Popolare i dati della serie nel grafico

#### Panoramica
Popolare il grafico con punti dati è fondamentale per l'analisi. Qui aggiungeremo valori specifici a una serie all'interno del grafico.

**Passaggi:**

1. **Aggiungere punti dati**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Regolare la sovrapposizione delle serie nel grafico

#### Panoramica
Affinare l'aspetto del grafico può migliorare la leggibilità. Questa sezione spiega come regolare la proprietà di sovrapposizione per una migliore visualizzazione dei dati.

**Passaggi:**

1. **Impostare la sovrapposizione delle serie**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Salvare la presentazione

#### Panoramica
Una volta configurata la presentazione, salvala su disco nel formato desiderato. Questo passaggio assicura che tutte le modifiche siano preservate.

**Passaggi:**

1. **Salvare la presentazione**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Il grafico appare piatto** | Rotazione 3D non impostata | Chiamare `setRotation3D` con i valori X/Y appropriati. |
| **I dati non vengono visualizzati** | Le celle del workbook non sono collegate | Assicurarsi che `fact.getCell` faccia riferimento agli indici di riga/colonna corretti. |
| **File non salvato** | Percorso errato o permessi mancanti | Verificare che `outputFilePath` sia scrivibile e che la cartella esista. |

## Domande frequenti

**D: Posso generare file di grafici per presentazioni in formati diversi da PPTX?**  
R: Sì, Aspose.Slides supporta PDF, ODP e formati immagine tramite l'enumerazione `SaveFormat`.

**D: È necessaria una licenza per eseguire il codice in sviluppo?**  
R: Una licenza temporanea o di valutazione è sufficiente per lo sviluppo, ma è richiesta una licenza completa per le distribuzioni in produzione.

**D: È possibile aggiungere più grafici alla stessa diapositiva?**  
R: Assolutamente. Chiama `slide.getShapes().addChart` più volte con posizioni o dimensioni diverse.

**D: Come posso modificare la palette di colori del grafico?**  
R: Usa `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` e imposta un `SolidFillColor`.

**D: Posso collegare il grafico a una fonte dati esterna, come un database?**  
R: Sì. Recupera i dati con JDBC, quindi popola le celle del workbook programmaticamente prima del salvataggio.

## Conclusione

Hai ora appreso **come aggiungere un grafico** a una presentazione Java, configurarne i dati, personalizzare la rotazione 3D, regolare la sovrapposizione delle serie e salvare il file finale. Questa conoscenza ti consente di automatizzare la generazione di report, creare un branding coerente e fornire presentazioni basate sui dati senza sforzi manuali. Per personalizzazioni più approfondite—come lo stile delle legende, degli assi o l'applicazione di temi—esplora le funzionalità complete nella documentazione ufficiale.

Per funzionalità avanzate e opzioni di personalizzazione, consulta la [documentazione di Aspose.Slides per Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-20  
**Testato con:** Aspose.Slides per Java 25.4 (JDK 16)  
**Autore:** Aspose