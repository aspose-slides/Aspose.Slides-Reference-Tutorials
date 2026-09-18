---
date: '2026-09-17'
description: Scopri come creare un grafico a bolle PowerPoint usando Aspose.Slides
  for Java. Questa guida ti mostra come aggiungere chart alla slide, configurare bubble
  size e salvare il PPTX in modo efficiente.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Scopri come creare un grafico a bolle PowerPoint usando Aspose.Slides
  for Java. Questo tutorial spiega come aggiungere chart alla slide, regolare bubble
  size e salvare la presentazione in modo efficiente.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Crea un grafico a bolle PowerPoint con Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Crea un grafico a bolle PowerPoint con Aspose.Slides for Java
url: /it/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un grafico a bolle PowerPoint con Aspose.Slides per Java

## Introduzione
Se hai bisogno di **creare un grafico a bolle PowerPoint** in modo programmatico, Aspose.Slides per Java ti offre un'API pulita, lato server, che funziona senza Microsoft Office. In questo tutorial imparerai come aggiungere un grafico a una diapositiva, controllare le dimensioni delle bolle e salvare il PPTX finale gestendo efficientemente le risorse. I passaggi sono suddivisi in modo da poter copiare‑incollare il codice in qualsiasi progetto Java e vedere subito i risultati.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides for Java
- **Quale versione di Java è richiesta?** JDK 16 o superiore
- **Come aggiungere un grafico a bolle?** Call `addChart(ChartType.Bubble, …)` on a slide
- **Posso modificare la dimensione delle bolle?** Yes, via `setBubbleSizeScale()`
- **Come salvo il file?** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## Che cos'è creare un grafico a bolle PowerPoint?
Creare un grafico a bolle in PowerPoint significa generare programmaticamente un grafico in cui ogni punto dati è rappresentato da una bolla la cui posizione X, posizione Y e dimensione codificano tre dimensioni dei dati. Aspose.Slides per Java gestisce il rendering, quindi non è necessario avere PowerPoint installato.

## Perché usare Aspose.Slides per Java?
Aspose.Slides supporta **oltre 50 tipi di grafico**, può elaborare presentazioni fino a **2 GB** senza caricare l'intero file in memoria, e funziona su qualsiasi piattaforma che supporta Java 16+. Queste capacità quantificate lo rendono una scelta affidabile per la creazione di report di livello aziendale.

## Prerequisiti
- **Java Development Kit** 16 o più recente installato.
- **Libreria Aspose.Slides per Java** (aggiungi tramite Maven, Gradle o download diretto del JAR).
- Familiarità di base con la sintassi Java e la programmazione orientata agli oggetti.

## Configurazione di Aspose.Slides per Java
Per iniziare a usare Aspose.Slides, includi la libreria nel tuo sistema di build.

### Maven
Aggiungi la seguente dipendenza al tuo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Includi questo nel tuo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
Puoi anche ottenere l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
- **Free trial** – esplora tutte le funzionalità senza costi.  
- **Temporary license** – valutazione estesa per progetti più grandi.  
- **Full license** – richiesta per distribuzioni in produzione.

### Inizializzazione e configurazione di base
La classe `Presentation` è il punto di ingresso per creare o caricare file PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Guida all'implementazione
Di seguito trovi una guida passo‑paso per creare un grafico a bolle e gestire le risorse.

## Come creare un grafico a bolle PowerPoint
In questa sezione imparerai la sequenza esatta di chiamate API necessarie per generare un grafico a bolle, configurare le sue proprietà visive e salvare il risultato come file PPTX. L'approccio funziona per qualsiasi progetto Java che includa Aspose.Slides e segua le migliori pratiche di gestione delle risorse.

Carica la presentazione, aggiungi un grafico a bolle, configura il suo aspetto e salva il file.

### Risposta diretta
Crea una nuova `Presentation`, chiama `addChart(ChartType.Bubble, …)` sulla diapositiva desiderata, regola la scala delle dimensioni delle bolle con `setBubbleSizeScale(150)`, quindi salva usando `pres.save("Result.pptx", SaveFormat.Pptx)`. Questa sequenza aggiunge un grafico a bolle completamente funzionale in poche righe di Java.

- **`ChartType.Bubble`** rappresenta il tipo di grafico a bolle.  
- **`addChart`** inserisce un nuovo grafico del tipo specificato su una diapositiva.  
- **`setBubbleSizeScale`** regola la dimensione complessiva delle bolle nel grafico.  
- **`SaveFormat.Pptx`** specifica il formato file PPTX per il salvataggio.

#### Implementazione passo‑passo
**1. Inizializzare la presentazione** – istanziare l'oggetto `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Aggiungere un grafico a bolle** – inserire il grafico nelle coordinate scelte.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` indica ad Aspose.Slides di creare un grafico a bolle.  
- I parametri numerici definiscono la posizione X/Y e la larghezza/altezza in punti.

**3. Configurare la scala delle dimensioni delle bolle** – ingrandire le bolle per un impatto visivo migliore.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Impostare la scala al **150 %** rende ogni bolla 1,5 × più grande del valore predefinito.

**4. Salvare la presentazione** – scrivere il PPTX su disco.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Suggerimenti per la risoluzione dei problemi
- Verifica i permessi di scrittura per la cartella di output.  
- Conferma che il JAR di Aspose.Slides corrisponda alla versione JDK che stai utilizzando.

## Come gestire efficacemente le risorse di PowerPoint
Una gestione efficace delle risorse previene le perdite di memoria e mantiene ridotto l'impronta della JVM, soprattutto durante l'elaborazione di presentazioni di grandi dimensioni o in ambienti server. Segui lo schema qui sotto per garantire che le risorse native vengano rilasciate anche in caso di eccezione.

Una gestione efficiente delle risorse previene le perdite di memoria, soprattutto durante l'elaborazione di presentazioni di grandi dimensioni.

### Risposta diretta
Dopo aver terminato di lavorare con una `Presentation`, chiama sempre `pres.dispose()` all'interno di un blocco `try‑finally`; questo rilascia le risorse native e consente alla JVM di recuperare rapidamente la memoria.

- **`pres.dispose()`** rilascia le risorse native utilizzate dalla presentazione.

**1. Creare e modificare** – lavorare con la presentazione secondo necessità.  
```java
Presentation pres = new Presentation();
```

**2. Rilasciare le risorse** – liberare la memoria una volta completata l'elaborazione.  
```java
if (pres != null) pres.dispose();
```

## Applicazioni pratiche
I grafici a bolle eccellono in scenari in cui è necessario visualizzare simultaneamente tre dimensioni dei dati:

1. **Market analysis** – la dimensione della bolla rappresenta il fatturato mentre gli assi X/Y mostrano crescita e quota di mercato.  
2. **Performance metrics** – confronta la produttività dei dipendenti (X), la soddisfazione (Y) e l'impatto (dimensione).  
3. **Geographical data** – traccia le città con la popolazione codificata nella dimensione della bolla.  
4. **Project management** – visualizza la timeline (X), il costo (Y) e il rischio (dimensione) su una singola diapositiva.

## Considerazioni sulle prestazioni
- **Utilizzo delle risorse** – elimina le presentazioni prontamente per mantenere basso l'uso dell'heap.  
- **Gestione della memoria Java** – avvolgi il lavoro sulla presentazione in `try‑finally` per garantire la cancellazione anche in caso di eccezioni.  
- **Rimani aggiornato** – aggiorna all'ultima versione di Aspose.Slides per beneficiare di ottimizzazioni delle prestazioni e correzioni di bug.

## Domande frequenti

**Q: Che cos'è Aspose.Slides per Java?**  
A: Aspose.Slides per Java è una libreria autonoma che consente di creare, modificare e convertire file PowerPoint senza la necessità di Microsoft Office.

**Q: Come integrazione Aspose.Slides nel mio progetto Java esistente?**  
A: Aggiungi la dipendenza Maven o Gradle mostrata in precedenza, oppure inserisci il JAR nel tuo classpath, quindi importa `com.aspose.slides.*`.

**Q: Posso usare Aspose.Slides per presentazioni di grandi dimensioni?**  
A: Sì, la libreria gestisce efficientemente presentazioni fino a **2 GB** e supporta lo streaming per evitare di caricare l'intero file in memoria.

**Q: Quali tipi di grafico sono disponibili oltre ai grafici a bolle?**  
A: Sono supportati oltre **50 tipi di grafico**, tra cui barre, linee, torta, radar e cascata.

**Q: Esiste un supporto integrato per lo stile degli elementi del grafico?**  
A: Assolutamente. È possibile personalizzare colori, caratteri, bordi e etichette dei dati tramite gli oggetti `ChartSeries` e `ChartTitle` del grafico.

## Risorse
- **Documentazione**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Acquisto**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Versione di prova gratuita**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licenza temporanea**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Supporto**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Ultimo aggiornamento:** 2026-09-17  
**Testato con:** Aspose.Slides per Java 25.4 (jdk16)  
**Autore:** Aspose

## Tutorial correlati

- [Come aggiungere un grafico a PowerPoint usando Aspose.Slides per Java: Guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java crea grafico PowerPoint usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Crea grafico PowerPoint Java – Salva presentazioni con grafici usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}