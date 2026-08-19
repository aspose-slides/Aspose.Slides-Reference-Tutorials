---
date: '2026-07-08'
description: Scopri come aggiungere grafici a torta nelle presentazioni PowerPoint
  usando Aspose.Slides for Java. Segui questa guida passo‑passo per creare e personalizzare
  grafici a torta professionali.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Aggiungi un grafico a torta PowerPoint usando Aspose.Slides for Java.
  Questo tutorial mostra come generare e personalizzare grafici a torta programmaticamente,
  perfetto per report automatizzati.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Aggiungi un grafico a torta PowerPoint con Aspose.Slides for Java – Guida
  rapida
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Come aggiungere un grafico a torta PowerPoint con Aspose.Slides for Java
url: /it/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aggiungi grafico a torta PowerPoint con Aspose.Slides per Java

## Introduzione

Se hai bisogno di **aggiungere grafico a torta PowerPoint** alle diapositive senza aprire manualmente PowerPoint, sei nel posto giusto. In questa guida ti mostreremo come configurare Aspose.Slides per Java, creare un grafico a torta e personalizzare ogni fetta—perfetto per report automatizzati, dashboard o presentazioni personalizzate. Alla fine avrai uno snippet Java riutilizzabile che genera un file PowerPoint con grafico a torta rifinito in pochi secondi.

### Risposte rapide
- **Quale libreria crea il grafico?** Aspose.Slides per Java (ultima versione).  
- **Posso eseguirlo in modalità head‑less?** Sì—non è necessaria alcuna installazione di Office.  
- **Quale versione di Java è ottimale?** JDK 16+ per le migliori prestazioni e miglioramenti del GC.  
- **Come faccio a far esplodere una fetta?** Chiama `setExplosion` su `IDataPoint` e imposta un offset in pixel.  
- **È necessaria una licenza per la produzione?** Una versione di prova funziona per lo sviluppo; una licenza permanente rimuove tutti i limiti di valutazione.

## Perché aggiungere un grafico a torta PowerPoint usando Aspose.Slides per Java?

Puoi generare report visivi aggiornati direttamente dai tuoi servizi back‑end, eliminando errori di copia‑incolla manuali e garantendo uno stile coerente con il brand. Aspose.Slides supporta **oltre 70 tipi di grafico** e può elaborare presentazioni con **oltre 10.000 diapositive** senza caricare l’intero file in memoria, rendendolo ideale per automazione su larga scala.

## Prerequisiti

- **Aspose.Slides per Java** – il tutorial fa riferimento alla versione 25.4 (l'ultima al momento della stesura).  
- **Java Development Kit** – si consiglia JDK 16 o versioni successive.  
- **Maven** o **Gradle** per la gestione delle dipendenze.  

## Configurazione di Aspose.Slides per Java

### Maven
Aggiungi questa dipendenza al tuo file `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inserisci quanto segue nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, scarica l'ultima versione direttamente da [Rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

### Licenze
Per utilizzare Aspose.Slides senza limitazioni:

- Inizia con una **prova gratuita** per valutare l'API.  
- Richiedi una **licenza temporanea** per test estesi nella pagina [Licenza temporanea](https://purchase.aspose.com/temporary-license/).  
- Acquista un abbonamento completo tramite la [pagina di acquisto](https://purchase.aspose.com/buy).

## Come aggiungere un grafico a torta PowerPoint usando Aspose.Slides per Java

Carica una nuova presentazione, inserisci un grafico a torta e salva il file—tutto in tre passaggi concisi. Questo modello funziona per qualsiasi dimensione di set di dati e può essere inserito in un ciclo per generare decine di diapositive automaticamente. L'approccio è leggero, richiede solo poche righe di codice e nessuna risorsa esterna, rendendolo adatto sia a piccoli utility che a grandi lavori batch.

### Passo 1: Inizializzare la Presentazione
La classe `Presentation` rappresenta un singolo file PowerPoint in memoria. Creare un'istanza ti fornisce un nuovo deck di diapositive vuoto su cui lavorare.
```java
Presentation pres = new Presentation();
```

### Passo 2: Aggiungere il grafico a torta
Inserisci un grafico a torta nella prima diapositiva. Le coordinate (50, 50) e le dimensioni (600 × 400) si adattano a un layout standard 16:9 e lasciano spazio per i titoli.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Passo 3: Salvare la Presentazione
Scrivi la presentazione su disco. Sostituisci `YOUR_OUTPUT_DIRECTORY` con la cartella in cui desideri salvare il file.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Passo 4: Pulire le risorse
Rilascia l'oggetto `Presentation` per liberare le risorse native ed evitare perdite di memoria.
```java
if (pres != null) pres.dispose();
```

## Come personalizzare l'esplosione del punto dati e il colore?

Carica il grafico, individua il punto dati di destinazione, quindi applica un offset di esplosione e un colore di riempimento solido. Questo fa risaltare la fetta per enfatizzare. Queste regolazioni aiutano a catturare l'attenzione del pubblico su valori critici e migliorano la leggibilità complessiva del grafico.

### Passo 1: Caricare una Presentazione Esistente (o riutilizzare quella appena creata)
L'oggetto `Presentation` carica un file PowerPoint esistente in memoria, consentendoti di modificarne il contenuto.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Passo 2: Accedere al Grafico e al Punto Dati di Destinazione
L'interfaccia `IDataPoint` rappresenta un singolo punto dati (fetta) all'interno di una serie di grafico.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Passo 3: Applicare Esplosione e Colore
`setExplosion(int)` imposta la distanza, in pixel, con cui una fetta è spostata dal centro del grafico. Separa visivamente la fetta con `setExplosion(20)` e cambia il suo riempimento in blu usando `setFillType(FillType.Solid)` e `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Passo 4: Salvare e Rilasciare
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Applicazioni pratiche
- **Report di vendita:** Evidenzia i prodotti più venduti con fette esplose.  
- **Analisi di bilancio:** Assegna colori distinti ai dipartimenti per un rapido confronto visivo.  
- **Diapositive educative:** Scomponi concetti complessi in segmenti di grafico facilmente comprensibili.  

## Considerazioni sulle prestazioni
- **Rilasciare gli oggetti** tempestivamente per evitare perdite di memoria, soprattutto quando si generano molte diapositive in un ciclo.  
- **Monitorare l'uso dell'heap** per presentazioni di grandi dimensioni; utilizza la sovraccarico `Save` che accetta un `OutputStream` per trasmettere i dati e mantenere basso l'impatto di memoria.  
- Attieniti a **JDK 16+** per beneficiare dei più recenti miglioramenti della garbage collection, che possono ridurre il tempo di elaborazione fino al 30 % per presentazioni da 1.000 diapositive.

## Conclusione
Ora disponi di un flusso di lavoro completo, pronto per la produzione, per **aggiungere grafico a torta PowerPoint** usando Aspose.Slides per Java. Sperimenta con diverse distanze di esplosione, colori e set di dati per allineare il risultato al tuo brand. Quando sei pronto, esplora altri tipi di grafico—bar, line o scatter—per costruire un dashboard analitico completo all'interno di PowerPoint.

## Domande frequenti

**Q: Qual è il più grande vantaggio dell'utilizzo di Aspose.Slides per Java?**  
A: Ti consente di creare, modificare e rendere file PowerPoint programmaticamente senza la necessità di installare Microsoft Office, supportando oltre 70 tipi di grafico e più di 100 formati di file.

**Q: Posso generare un file PowerPoint da zero?**  
A: Sì, istanzia un oggetto `Presentation`, aggiungi diapositive, grafici o forme, quindi chiama `save`—tutto in puro codice Java.

**Q: Come faccio a far esplodere una specifica fetta di torta?**  
A: Recupera il `IDataPoint` per la fetta e chiama `setExplosion(pixelOffset)`. L'offset definisce quanto la fetta si sposta verso l'esterno.

**Q: Esiste un limite al numero di diapositive che posso creare?**  
A: Aspose.Slides può gestire presentazioni con fino a **10.000 diapositive** in un singolo file, a condizione di trasmettere l'output per evitare di caricare tutto in memoria.

**Q: Dove posso trovare esempi più avanzati di personalizzazione dei grafici?**  
A: Consulta la documentazione ufficiale [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) per riferimenti API dettagliati e progetti di esempio.

## Risorse
- **Documentazione:** [Documentazione Aspose.Slides Java](https://reference.aspose.com/slides/java/)  
- **Scarica la libreria:** [Rilasci Aspose](https://releases.aspose.com/slides/java/)  
- **Acquista licenza:** [Acquista Aspose.Slides](https://purchase.aspose.com/buy)  
- **Prova gratuita:** [Prova Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Licenza temporanea:** [Richiedi licenza temporanea](https://purchase.aspose.com/temporary-license/)  
- **Forum di supporto:** [Supporto Aspose](https://forum.aspose.com/c/slides/11)

---

**Ultimo aggiornamento:** 2026-07-08  
**Testato con:** Aspose.Slides per Java 25.4 (classificatore JDK 16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animare grafici PowerPoint usando Aspose.Slides per Java – Guida passo passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Creare e convalidare layout di grafici in PowerPoint usando Aspose.Slides per Java | Guida SEO ottimizzata](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}