---
date: '2026-07-17'
description: Scopri come aggiungere grafici Sunburst in PowerPoint usando Aspose Slides
  per Java. Guida passo‑passo che copre l'installazione, la creazione del grafico,
  la personalizzazione e casi d'uso reali.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Come aggiungere grafici Sunburst in PowerPoint usando Aspose Slides
  per Java. Segui questo tutorial per configurare la libreria, creare un grafico,
  personalizzare i punti dati e applicarlo a progetti reali.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Come aggiungere grafici Sunburst in PowerPoint con Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Come aggiungere grafici Sunburst in PowerPoint con Aspose (Java)
url: /it/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere grafici Sunburst in PowerPoint con Aspose (Java)

## Introduzione

Aggiungere un grafico Sunburst a una presentazione PowerPoint può trasformare istantaneamente una tabella di dati piatta in una gerarchia visiva coinvolgente. In questo tutorial imparerai **come aggiungere grafici Sunburst** in PowerPoint usando Aspose.Slides per Java, dalla configurazione dell'ambiente alla messa a punto di colori ed etichette. Che tu stia creando un dashboard di vendite, una scomposizione di progetto‑attività o una presentazione educativa, i passaggi seguenti ti forniranno una soluzione pronta per la produzione.

**Cosa imparerai**
- Come configurare Aspose.Slides in un progetto Maven o Gradle  
- Come creare una nuova presentazione e inserire un grafico Sunburst  
- Come personalizzare i punti dati, le etichette e i colori di riempimento  
- Scenari reali in cui i grafici Sunburst brillano  

Iniziamo e vediamo quanto sia facile trasformare i dati gerarchici grezzi in una visualizzazione PowerPoint raffinata.

## Risposte rapide
- **Libreria principale?** Aspose.Slides for Java  
- **Tipo di grafico supportato?** Sunburst (gerarchico radiale)  
- **Versione minima di Java?** JDK 16  
- **Tempo tipico di implementazione?** 10‑15 minuti per un grafico di base  
- **Licenza necessaria per la produzione?** Sì, una licenza Aspose valida  

## Cos'è un grafico Sunburst?
Un grafico Sunburst è un diagramma radiale che visualizza dati gerarchici annidando anelli verso l'esterno da un punto centrale. È perfetto per mostrare relazioni a più livelli come strutture organizzative, categorie di prodotto o alberi di file‑system. Ogni anello concentric rappresenta un livello della gerarchia e la dimensione di ciascun segmento riflette il suo valore quantitativo, consentendo agli spettatori di comprendere rapidamente sia la struttura sia la magnitudine.

## Perché usare Aspose.Slides per Java?
Aspose.Slides supporta **oltre 50 tipi di grafico** e può manipolare presentazioni con **fino a 10.000 diapositive** senza caricare l'intero file in memoria, offrendo alte prestazioni per report a scala aziendale. Funziona cross‑platform, offre una copertura API estesa e include opzioni di licenza robuste che rimuovono i limiti di valutazione, rendendolo ideale per ambienti di produzione.

## Prerequisiti
- **Java Development Kit (JDK)** 16 o più recente  
- **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java  
- Familiarità di base con la sintassi Java e gli strumenti di build Maven/Gradle  

## Configurazione di Aspose.Slides per Java

### Dipendenza Maven
Aggiungi l'artifact Maven di Aspose.Slides al tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dipendenza Gradle
Se preferisci Gradle, includi la seguente riga in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
Puoi anche scaricare l'ultimo JAR direttamente dalla pagina ufficiale dei rilasci: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
Per eseguire senza limiti di valutazione, ottieni una licenza:
- **Prova gratuita** – licenza temporanea per una rapida valutazione.  
- **Licenza temporanea** – richiedine una dal [sito Aspose](https://purchase.aspose.com/temporary-license).  
- **Acquisto completo** – acquista un abbonamento per uso illimitato in produzione.

### Inizializzazione di base
La classe `Presentation` è il punto di ingresso per creare o aprire file PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guida all'implementazione

### Come aggiungere un grafico Sunburst a una presentazione PowerPoint usando Aspose.Slides per Java?
Carica una nuova `Presentation`, aggiungi una diapositiva, inserisci un `IChart` di tipo `ChartType.Sunburst` e chiama `save`. Questo conciso modello a tre passaggi crea un grafico Sunburst completamente funzionale pronto per ulteriori personalizzazioni.

#### Passo 1: Inizializzare la Presentazione
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Passo 2: Aggiungere il grafico Sunburst
L'interfaccia `IChart` definisce un oggetto grafico che può essere posizionato su qualsiasi diapositiva. Qui aggiungiamo un grafico Sunburst alle coordinate (100, 100) con una dimensione di 450 × 400 punti.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Passo 3: Salvare la Presentazione
Salva sempre le modifiche chiamando `save`. Puoi scegliere PPTX, PDF o uno dei oltre 50 formati di output supportati.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modificare i punti dati nel grafico

#### Panoramica
Puoi personalizzare ogni sezione del Sunburst — etichette, colori e visibilità — tramite la collezione di punti dati del grafico.

#### Passo 1: Accedere alla collezione di punti dati
La prima serie del grafico contiene una collezione di oggetti `IChartDataPoint` che rappresentano ogni sezione.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Passo 2: Mostrare il valore per un punto dati specifico
Imposta `IsValueShown` su `true` sul punto dati desiderato per visualizzare il suo valore numerico direttamente sulla sezione.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Passo 3: Modificare i formati delle etichette
Regola la visibilità delle etichette, il colore del carattere e lo sfondo per migliorare la leggibilità.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Passo 4: Impostare il colore di riempimento per i punti dati
Personalizza il colore di riempimento delle singole sezioni per abbinare la palette del tuo brand o per evidenziare segmenti chiave.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Passo 5: Salvare la presentazione modificata
Salva il grafico personalizzato salvando nuovamente la presentazione.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Applicazioni pratiche

1. **Business Analytics** – Visualizza le vendite per regione → linea di prodotto → SKU in una singola vista radiale.  
2. **Project Management** – Mostra le strutture di scomposizione del lavoro, approfondendo da fasi a compiti a sotto‑compiti.  
3. **Education** – Mappa le gerarchie del curriculum, come dipartimenti → corsi → moduli.  

## Considerazioni sulle prestazioni

- **Efficienza della memoria:** Aspose.Slides trasmette i dati, quindi anche un mazzo di 500 pagine con più grafici rimane sotto i 200 MB di RAM.  
- **Garbage Collection:** Rilascia gli oggetti diapositiva (`slide.dispose()`) quando non sono più necessari per evitare perdite di memoria.  

## Domande frequenti

**Q: Cos'è un grafico Sunburst?**  
A: Un grafico Sunburst visualizza dati gerarchici in anelli concentrici, con ogni anello che rappresenta un livello della gerarchia.

**Q: Come installo Aspose.Slides per Java usando Maven?**  
A: Aggiungi la dipendenza Maven mostrata nella sezione “Dipendenza Maven” al tuo `pom.xml` ed esegui `mvn clean install`.

**Q: Posso personalizzare altri tipi di grafico con Aspose.Slides?**  
A: Sì, la libreria supporta oltre 50 tipi di grafico, inclusi colonne, linee, torta e radar.

**Q: La mia presentazione non si salva—cosa devo controllare?**  
A: Verifica che il percorso del file sia corretto, che la directory esista e che tu abbia i permessi di scrittura. Inoltre, assicurati che il metodo `Presentation.save()` sia chiamato.

**Q: Dove posso trovare ulteriore aiuto o esempi?**  
A: Visita il [forum Aspose](https://forum.aspose.com/c/slides/11) o consulta il [riferimento ufficiale di Aspose.Slides](https://reference.aspose.com/slides/java/).

## Risorse
- **Documentazione:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Riferimento (minuscolo):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Forum della community:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Download:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Ultimo aggiornamento:** 2026-07-17  
**Testato con:** Aspose.Slides for Java 24.12  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animare i grafici PowerPoint usando Aspose.Slides per Java – Guida passo passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Creare un grafico in Java con Aspose.Slides – Aggiungere e convalidare i grafici](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}