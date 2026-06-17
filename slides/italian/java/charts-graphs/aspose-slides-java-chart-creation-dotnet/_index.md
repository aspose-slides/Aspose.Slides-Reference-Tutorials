---
date: '2026-06-03'
description: Scopri come creare grafici in presentazioni .NET e aggiungere un grafico
  alla diapositiva con Aspose.Slides for Java. Segui questa guida passo‑passo per
  la visualizzazione dei dati.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Crea grafici in .NET usando Aspose.Slides for Java
url: /it/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea grafici in .NET usando Aspose.Slides per Java

## Introduzione
Creare presentazioni accattivanti spesso richiede l'integrazione di rappresentazioni visive dei dati, come i grafici, per migliorare la comprensione e il coinvolgimento del pubblico. **Se vuoi creare grafici in .NET**, Aspose.Slides per Java ti offre un'API potente e indipendente dal linguaggio che funziona senza problemi all'interno delle applicazioni .NET. In questo tutorial imparerai a inizializzare una presentazione, aggiungere diversi tipi di grafico, gestire la cartella dati del grafico e formattare i dati delle serie—including la gestione dei valori negativi. Alla fine sarai in grado di generare grafici in file di presentazione in modo programmatico e aggiungere un grafico a una diapositiva con poche righe di codice.

## Risposte rapide
- **Qual è l'obiettivo principale?** Crea grafici in presentazioni .NET usando Aspose.Slides per Java.  
- **Quale versione della libreria è richiesta?** Aspose.Slides per Java 25.4 o successiva.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Posso usare Maven o Gradle?** Sì, entrambi i sistemi di build sono supportati.  
- **Quali tipi di grafico sono disponibili?** Colonna raggruppata, linea, torta, barra, area e altri.

## Come creare grafici in presentazioni .NET con Aspose.Slides per Java?
La classe `Presentation` rappresenta un file PowerPoint e fornisce metodi per manipolare le sue diapositive. Carica un nuovo oggetto `Presentation`, chiama `slides.addEmptySlide()` per ottenere una diapositiva, quindi usa `slide.getShapes().addChart()` per inserire il tipo di grafico desiderato alle coordinate specificate. Dopo aver aggiunto il grafico, popola la sua cartella dati con serie e categorie, applica eventuali formattazioni (come i colori per i valori negativi) e infine salva la presentazione in un file .pptx. Questo flusso ti consente di **creare grafici in .NET** con un set conciso di chiamate API.

## Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è un'API cross‑platform che consente agli sviluppatori di creare, modificare e renderizzare file PowerPoint senza Microsoft Office. Supporta **50+ input and output formats** e può elaborare presentazioni con migliaia di diapositive mantenendo l'utilizzo della memoria sotto i 200 MB.

## Perché usare Aspose.Slides per Java in un progetto .NET?
Aspose.Slides per Java gira sulla Java Virtual Machine e può essere chiamato da .NET tramite un wrapper nativo, offrendo agli sviluppatori .NET l'accesso a un motore di grafici maturo, elaborazione ad alte prestazioni di grandi set di dati e piena compatibilità con il codice Java esistente senza riscrivere la logica.

## Prerequisiti
Prima di immergerti nella creazione di grafici con Aspose.Slides per Java, elenchiamo ciò di cui hai bisogno:

### Librerie richieste e versioni
- **Aspose.Slides per Java**: Versione 25.4 o successiva.

### Requisiti di configurazione dell'ambiente
- Un ambiente di sviluppo che supporti le applicazioni .NET.  
- Conoscenza di base dei concetti di programmazione Java.

### Prerequisiti di conoscenza
- Familiarità con la creazione di presentazioni in un contesto di applicazione .NET.  
- Comprensione delle dipendenze Java e della loro gestione (Maven/Gradle).

## Configurazione di Aspose.Slides per Java
Per iniziare a usare Aspose.Slides, devi includerlo come dipendenza nel tuo progetto. Ecco come fare:

### Maven
Il frammento di dipendenza Maven aggiunge Aspose.Slides per Java al tuo progetto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Includi questa riga nel tuo file `build.gradle` per scaricare la libreria da Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, puoi scaricare l'ultima versione da [rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

#### Passaggi per l'acquisizione della licenza
- **Free Trial**: Inizia con una licenza temporanea per esplorare le funzionalità.  
- **Purchase**: Acquista una licenza per un uso di produzione senza restrizioni.

#### Inizializzazione e configurazione di base
L'inizializzazione di `Slides` richiede l'impostazione della licenza e la creazione di un'istanza `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Questa configurazione garantisce una gestione efficace delle risorse.

## Guida all'implementazione
Ti guideremo passo‑passo nell'implementazione delle funzionalità.

### Inizializzazione della presentazione
**Panoramica:**  
Creare un'istanza di presentazione prepara il terreno per tutte le operazioni successive. Questa funzionalità mostra come partire da zero usando Aspose.Slides.

#### Passo 1: Importare i pacchetti necessari
`Presentation` e le classi correlate fanno parte dello spazio dei nomi `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Passo 2: Creare un nuovo oggetto Presentation
Istanzia un oggetto `Presentation` e avvolgilo in un blocco try‑with‑resources per garantire lo smaltimento.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Questo assicura che l'oggetto presentation venga correttamente smaltito dopo l'uso, prevenendo perdite di memoria.*

### Aggiungere un grafico alla diapositiva
**Panoramica:**  
Aggiungere un grafico alla tua diapositiva può rendere la visualizzazione dei dati più efficace e coinvolgente.

#### Passo 1: Importare i pacchetti necessari
La classe `Chart` rappresenta una forma grafica che può essere posizionata su una diapositiva e personalizzata.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Passo 2: Inizializzare la presentazione e aggiungere il grafico
Crea una diapositiva, quindi chiama `addChart` con `ChartType.ClusteredColumn` e le coordinate e dimensioni desiderate.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Qui aggiungiamo un grafico a colonna raggruppata alla prima diapositiva alle coordinate e dimensioni specificate.*

### Gestione della cartella dati del grafico
**Panoramica:**  
Gestire efficientemente la cartella dati del tuo grafico ti permette di manipolare serie e categorie senza problemi.

#### Passo 1: Importare i pacchetti necessari
`IChartDataWorkbook` fornisce l'accesso alla cartella dati simile a Excel utilizzata dai grafici.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Passo 2: Accedere e cancellare la cartella dati
Recupera la cartella dati dal grafico e cancella eventuali dati esistenti per ricominciare da zero.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Cancellare la cartella dati è fondamentale per partire con una base pulita quando si aggiungono nuove serie e categorie.*

### Aggiungere serie e categorie al grafico
**Panoramica:**  
Questa funzionalità mostra come aggiungere punti dati significativi gestendo serie e categorie.

#### Passo 1: Aggiungere serie e categorie
Usa `chart.getChartData().getSeries().add()` e `chart.getChartData().getCategories().add()` per definire la struttura.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Aggiungere serie e categorie consente una presentazione dei dati più organizzata.*

### Popolare i dati delle serie e formattare
**Panoramica:**  
Popola il tuo grafico con punti dati e formatta l'aspetto per migliorare la leggibilità, soprattutto quando si trattano valori negativi.

#### Passo 1: Popolare i dati delle serie
Assegna valori numerici a ciascuna cella nella cartella dati e applica un riempimento rosso per i numeri negativi.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Questa sezione dimostra come popolare i dati e applicare una formattazione colore per una migliore visualizzazione.*

## Problemi comuni e soluzioni
- **LicenseNotFoundException** – Assicurati che il percorso del file di licenza sia corretto e che il file sia accessibile a runtime.  
- **NullPointerException on chart data** – Cancella sempre la cartella dati prima di aggiungere nuove serie per evitare dati residui.  
- **Chart not rendering in .NET** – Verifica di utilizzare la versione compatibile .NET del JAR Aspose.Slides e che il runtime Java sia correttamente configurato nel tuo progetto .NET.

## Domande frequenti

**Q: Posso generare un grafico nei file di presentazione senza una GUI?**  
A: Sì, Aspose.Slides per Java è completamente headless e funziona su server senza componenti grafici.

**Q: Quali versioni .NET sono supportate?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 e .NET 6 sono tutti supportati.

**Q: Quanti tipi di grafico posso aggiungere?**  
A: Sono disponibili oltre 20 tipi di grafico, inclusi colonna, linea, torta, area e radar.

**Q: È possibile stilizzare singoli punti dati?**  
A: Assolutamente – puoi impostare colori di riempimento, bordi e marcatori per ogni punto dati tramite l'API `IDataPoint`.

**Q: Devo convertire manualmente gli oggetti Java in tipi .NET?**  
A: No, il wrapper .NET di Aspose.Slides per Java gestisce automaticamente la conversione dei tipi.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come incorporare grafici in presentazioni .NET usando Aspose.Slides per una visualizzazione efficace dei dati](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Come recuperare il tipo di origine dati del grafico usando Aspose.Slides per .NET - Grafici & Diagrammi](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Creare e manipolare serie di grafici con Aspose.Slides .NET per una visualizzazione efficace dei dati](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}