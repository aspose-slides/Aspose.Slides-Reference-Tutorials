---
date: '2026-08-27'
description: Scopri come cancellare i data points dei chart in PowerPoint usando Aspose.Slides
  for Java. Questo tutorial passo‑passo mostra come cancellare programmaticamente
  i valori dei chart, le migliori pratiche e la gestione efficiente delle serie.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Scopri come cancellare i chart data points in PowerPoint usando Aspose.Slides
  for Java. Segui le istruzioni passo‑passo per ripristinare programmaticamente i
  charts in modo efficiente.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Come cancellare i chart data points in PowerPoint con Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Come cancellare i data points nei charts PowerPoint usando Aspose.Slides for
  Java: una guida completa'
url: /it/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come cancellare i punti dati nei grafici PowerPoint usando Aspose.Slides per Java

## Introduzione

In molti flussi di reporting è necessario **reimpostare un grafico** senza ricrearne il layout. Che tu stia aggiornando una dashboard, distribuendo un modello o automatizzando report notturni, sapere **come cancellare i punti dati di un grafico** fa risparmiare tempo e riduce gli errori. Questo tutorial ti mostra come usare **Aspose.Slides per Java** per cancellare programmaticamente punti specifici o un'intera serie, mantenendo intatto lo stile visivo.

**Cosa imparerai**
- Come Aspose.Slides ti permette di manipolare i grafici PowerPoint da Java.  
- Istruzioni passo‑passo per cancellare i punti dati di un grafico in una serie.  
- Consigli di best‑practice per prestazioni e licenze.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides per Java (v25.4+).  
- **Quale metodo cancella effettivamente un punto dato?** Impostare i valori delle celle X e Y a `null`.  
- **È necessaria una licenza per la produzione?** Sì – una licenza commerciale rimuove i limiti della versione di prova.  
- **Java 16 è supportato?** Assolutamente; la libreria funziona con JDK 16 e versioni successive.  
- **Posso mirare a una sola serie?** Sì – itera la serie specifica che desideri cancellare.

## Cos'è Aspose.Slides per Java?

Aspose.Slides per Java è un'API completa che consente la creazione, la modifica e la conversione di file PowerPoint senza Microsoft Office. Supporta più di 70 tipi di grafico, oltre 150 formati di file e può elaborare presentazioni fino a 500 MB senza caricare l'intero file in memoria.

## Perché cancellare i punti dati del grafico?

Cancellare i punti dati del grafico ti permette di mantenere il layout esistente — come colori, legende, impostazioni degli assi e marcatori — sostituendo i valori numerici sottostanti. Questo approccio è utile quando devi aggiornare un grafico con nuovi dati, fornire un modello con segnaposto vuoti o generare dashboard dinamiche che cambiano frequentemente senza ricostruire il design visivo.

- Aggiornare un grafico con un nuovo set di dati mantenendo colori, legende e impostazioni degli assi.  
- Distribuire un modello che contiene grafici vuoti pronti per l'inserimento da parte dell'utente.  
- Costruire dashboard dinamiche dove i dati cambiano spesso.

## Come cancellare i punti dati del grafico in PowerPoint usando Aspose.Slides per Java

Carica la presentazione, individua il grafico e imposta le celle X e Y di ogni punto dati a `null`. Questa operazione rimuove i valori numerici ma lascia intatte la serie, i marcatori e la formattazione. L'intero processo di solito termina in meno di un secondo per una PPTX standard di 10 diapositive.

### Risposta diretta
Per cancellare i punti dati di un grafico, apri il PPTX con `new Presentation("input.pptx")`, recupera l'oggetto `IChart` target, itera la `IChartSeries` desiderata e chiama `dataPoint.getXValue().setValue(null)` e `dataPoint.getYValue().setValue(null)` per ogni punto. Infine, salva la presentazione con `pres.save("output.pptx", SaveFormat.Pptx)`. Questo approccio cancella programmaticamente i dati mantenendo il design visivo del grafico.

### Ancore di definizione
- `Presentation` è l'oggetto di livello superiore di Aspose.Slides che rappresenta un file PowerPoint in memoria.  
- `IChart` è l'interfaccia che fornisce l'accesso alle serie, assi e formattazione di una forma grafico.  
- `IChartSeries` rappresenta una singola serie all'interno di un grafico e contiene una collezione di oggetti `IDataPoint`.  
- `IDataPoint` contiene i valori X e Y individuali per un punto del grafico.

### Implementazione passo‑passo

1. **Carica la presentazione** – crea un'istanza `Presentation` che punta al tuo file sorgente.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Accedi alla diapositiva e al grafico** – recupera la diapositiva (di solito indice 0) e cast il primo shape a `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Itera la serie target** – seleziona la serie che vuoi cancellare (ad es., `chart.getChartData().getSeries().get_Item(0)`) e cicla i suoi punti dati, impostando entrambi i valori delle celle X e Y a `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Salva la presentazione modificata** – scrivi le modifiche in un nuovo file o sovrascrivi l'originale.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Configurazione di Aspose.Slides per Java

### Installazione Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Installazione Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Download diretto

In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza

Per utilizzare Aspose.Slides oltre i limiti della versione di prova:
- Ottieni una licenza **di prova gratuita**.  
- Richiedi una licenza **temporanea** per la valutazione.  
- Acquista una licenza **commerciale** per l'uso in produzione.

#### Inizializzazione e configurazione di base

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Applicazioni pratiche

Cancellare i punti dati del grafico è utile in molti scenari reali:

1. **Pipeline di aggiornamento dati** – sostituisci numeri obsoleti con nuove analisi senza ricostruire il layout del grafico.  
2. **Distribuzione di modelli** – fornisci modelli PowerPoint che contengono grafici vuoti pronti per l'inserimento da parte dell'utente.  
3. **Dashboard dinamiche** – genera presentazioni notturne che estraggono dati da API, cancellando prima i valori vecchi.  
4. **Job di reporting automatizzati** – integra la logica di cancellazione nei pipeline CI/CD per la generazione automatica di report.

## Considerazioni sulle prestazioni

- **Rilascia gli oggetti**: chiama `pres.dispose()` dopo il salvataggio per liberare le risorse native.  
- **Elaborazione batch**: riutilizza un'unica istanza `License` per molti file per ridurre l'overhead.  
- **Ottimizzazione JVM**: aumenta la dimensione dell'heap (`-Xmx2g` o superiore) quando gestisci presentazioni più grandi di 200 MB.  
- **Modalità a basso consumo di memoria**: Aspose.Slides può streammare file PPTX di grandi dimensioni, consentendo l'elaborazione di fino a 10 000 diapositive senza caricare tutto in memoria.

## Domande frequenti

**D: È necessaria una licenza per le build di sviluppo?**  
R: Una licenza di prova gratuita è sufficiente per sviluppo e test. Una licenza commerciale è richiesta per le distribuzioni in produzione.

**D: Aspose.Slides per Java supporta le funzionalità di PowerPoint 2016/2019?**  
R: Sì, la libreria supporta pienamente le funzionalità PPTX moderne, inclusi tipi di grafico avanzati e SmartArt.

**D: Posso cancellare i punti dati in un grafico che utilizza un asse secondario?**  
R: Assolutamente – basta fare riferimento alla serie che appartiene all'asse secondario e impostare i suoi punti dati a `null` come descritto sopra.

**D: È possibile cancellare solo i valori Y mantenendo le etichette X?**  
R: Sì. Chiama `dataPoint.getYValue().setValue(null)` e lascia intatta la cella X.

**D: Come posso automatizzare questo per più presentazioni?**  
R: Avvolgi il codice di cancellazione in un ciclo che itera su una directory di file PPTX, applicando la stessa logica a ciascun file.

## Risorse

- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/java/)
- [Temporary License Application](https://purchase.aspose.com/temporary-license/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

Con queste risorse sei pronto a iniziare a cancellare i punti dati dei grafici nelle tue applicazioni Java. Buona programmazione!

---

**Ultimo aggiornamento:** 2026-08-27  
**Testato con:** Aspose.Slides per Java 25.4 (JDK 16)  
**Autore:** Aspose

## Tutorial correlati

- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Clear Specific Chart Series Data Points Data in Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}