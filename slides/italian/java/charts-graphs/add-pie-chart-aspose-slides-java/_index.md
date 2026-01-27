---
date: '2026-01-09'
description: Scopri come utilizzare Aspose Slides Maven per aggiungere un grafico
  a una diapositiva e personalizzare un grafico a torta nelle presentazioni Java.
  Configurazione passo‑passo, codice ed esempi reali.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Aggiungi un grafico a torta a una presentazione'
url: /it/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere un grafico a torta a una presentazione usando Aspose.Slides Java

## Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per trasmettere informazioni in modo efficace, soprattutto quando la visualizzazione dei dati svolge un ruolo chiave. Se desideri automatizzare questo processo con **aspose slides maven**, sei nel posto giusto. In questo tutorial imparerai a **add chart to slide** — in particolare un grafico a torta — usando Aspose.Slides per Java, e vedrai come personalizzarlo per scenari reali.

### Cosa imparerai
- Come inizializzare un oggetto presentation in Java.  
- Passaggi per **add a pie chart java** sulla prima diapositiva di una presentazione.  
- Accesso ai workbook dei dati del grafico e elencazione dei fogli di lavoro al loro interno.  

Immergiamoci in come sfruttare Aspose.Slides Java per migliorare le tue presentazioni con grafici dinamici!

## Risposte rapide
- **Quale libreria aggiunge grafici via Maven?** aspose slides maven  
- **Quale tipo di grafico è dimostrato?** Pie chart (add chart to slide)  
- **Versione minima di Java richiesta?** JDK 16 o successiva  
- **È necessaria una licenza per i test?** Una prova gratuita funziona; per la produzione serve una licenza  
- **Dove posso trovare la dipendenza Maven?** Nella sezione di configurazione qui sotto  

## Che cos’è Aspose Slides Maven?
Aspose.Slides per Java è un’API potente che consente agli sviluppatori di creare, modificare e rendere file PowerPoint in modo programmatico. Il pacchetto Maven (`aspose-slides`) semplifica la gestione delle dipendenze, permettendoti di concentrarti sulla costruzione e personalizzazione delle diapositive—come aggiungere un grafico a torta—senza occuparti della gestione a basso livello dei file.

## Perché usare Aspose.Slides Maven per aggiungere un grafico a una diapositiva?
- **Automazione:** Genera report e dashboard automaticamente.  
- **Precisione:** Controllo completo su tipi di grafico, dati e stile.  
- **Cross‑Platform:** Funziona su qualsiasi ambiente compatibile con Java.  

## Prerequisiti
- **Aspose.Slides for Java** versione 25.4 o successiva (Maven/Gradle).  
- JDK 16+ installato.  
- Un IDE (IntelliJ IDEA, Eclipse, ecc.).  
- Conoscenze di base di Java e familiarità con Maven o Gradle.

## Configurazione di Aspose.Slides per Java
Per prima cosa, includi Aspose.Slides nel tuo progetto tramite Maven o Gradle.

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

In alternativa, puoi [download the latest release](https://releases.aspose.com/slides/java/) direttamente dal sito di Aspose.

### Acquisizione della licenza
Aspose.Slides for Java offre una prova gratuita con una licenza temporanea per i test. Per un uso illimitato in produzione, acquista una licenza tramite la [purchase page](https://purchase.aspose.com/buy).

## Guida all'implementazione
Di seguito suddividiamo la soluzione in due funzionalità: aggiungere un grafico a torta e accedere al suo workbook dei dati.

### Funzionalità 1: Creare una presentazione e aggiungere un grafico
#### Panoramica
Questa parte mostra come creare una nuova presentazione e **add a pie chart** alla prima diapositiva.

#### Passo‑per‑passo

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*Creates the `Presentation` instance that will hold all slides.*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Places a pie chart at coordinates (50, 50) with a width of 400 and height of 500. The `ChartType.Pie` enum tells Aspose to render a pie chart.*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*Releases native resources; always call `dispose()` when you’re done.*

### Funzionalità 2: Accesso al workbook dei dati del grafico e ai fogli di lavoro
#### Panoramica
Impara come raggiungere il workbook sottostante che memorizza i dati del grafico e iterare attraverso i suoi fogli di lavoro.

#### Passo‑per‑passo

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Same as Feature 1, Step 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Same as Feature 1, Step 2.*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Retrieves the `IChartDataWorkbook` linked to the chart.*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Prints each worksheet’s name, letting you verify the data structure.*

**Step 5: Dispose of Resources**  
*Same as Feature 1, Step 3.*

## Applicazioni pratiche
- **Data Reporting:** Auto‑generate slide decks with up‑to‑date metrics for business intelligence.  
- **Academic Presentations:** Visualize research results without manual chart creation.  
- **Marketing Material:** Showcase product performance or survey results instantly.

## Considerazioni sulle prestazioni
- Keep the slide and chart count reasonable; each consumes memory.  
- Always call `dispose()` to free native resources.  
- Optimize workbook data handling—avoid loading massive datasets into a single chart.

## Conclusione
Abbiamo coperto come **aspose slides maven** ti consente di **add chart to slide** in modo programmatico e come lavorare con il workbook dei dati del grafico. Con questi blocchi di costruzione puoi automatizzare qualsiasi flusso di lavoro di reporting che richieda un output PowerPoint curato.

### Prossimi passi
- Explore chart styling options (colors, legends, data labels).  
- Connect to external data sources (CSV, databases) to populate charts dynamically.  
- Combine multiple chart types in a single presentation for richer storytelling.

## Domande frequenti

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library is platform‑independent.

**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, and many more chart types.

**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit the number of high‑resolution images, and reuse chart templates when possible.

**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.

**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

## Risorse
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
