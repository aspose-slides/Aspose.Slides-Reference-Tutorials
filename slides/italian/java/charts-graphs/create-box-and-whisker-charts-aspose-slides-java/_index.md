---
date: '2026-08-21'
description: Scopri come creare un box plot Java usando Aspose.Slides, aggiungere
  un grafico alla diapositiva e generare un box‑and‑whisker chart in PowerPoint. Ideale
  per gli sviluppatori Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Scopri come creare un box plot Java usando Aspose.Slides, aggiungere
  un grafico alla diapositiva e generare un box‑and‑whisker chart in PowerPoint. Perfetto
  per gli sviluppatori Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Come creare un box plot Java con Aspose.Slides per PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Come creare un box plot Java con Aspose.Slides per PowerPoint
url: /it/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un box plot java con Aspose.Slides per PowerPoint

In questa guida **creerai un box plot java** con Aspose.Slides, quindi incorporerai il grafico direttamente in una diapositiva PowerPoint. Generare grafici a scatola e baffi in modo programmatico ti consente di trasformare dati statistici grezzi in intuizioni visive chiare senza uscire dal tuo codice Java. Se devi automatizzare la generazione di report PowerPoint, Aspose.Slides per Java offre un'API affidabile e ad alte prestazioni.

## Cosa imparerai

- Configurare l'ambiente per Aspose.Slides per Java
- Passaggi per **aggiungere un grafico alla diapositiva** e generare un grafico a scatola‑baffi in PowerPoint usando Java
- Best practice per ottimizzare le prestazioni quando si lavora con Aspose.Slides
- Applicazioni pratiche dei grafici a scatola‑baffi

## Risposte rapide
- **Quale libreria crea un box plot in Java?** Aspose.Slides per Java.  
- **Quale tipo di grafico viene utilizzato?** `ChartType.BoxAndWhisker`.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per la valutazione; è richiesta una licenza commerciale per la produzione.  
- **Posso aggiungere più serie?** Sì – ripeti il blocco di creazione della serie per ogni set di dati.  
- **Qual è il formato del file finale?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Cos'è un box plot e perché usarlo in Java?

Un grafico a scatola‑baffi (spesso chiamato *box plot*) visualizza la distribuzione dei dati — mediana, quartili e outlier — in forma compatta. In Java, generare questo grafico in modo programmatico ti permette di incorporare intuizioni statistiche direttamente nelle presentazioni PowerPoint, eliminando la creazione manuale dei grafici. È particolarmente utile per confrontare distribuzioni tra più categorie, come i punteggi dei test tra classi o i dati di vendita tra regioni. Generando il grafico in Java, puoi integrarlo in pipeline di reporting automatizzate, garantendo che i dati più recenti siano sempre riflessi nelle tue presentazioni.

## Perché aggiungere un grafico alla diapositiva con Aspose.Slides?

Aspose.Slides astrae i dettagli a basso livello di OpenXML, fornendoti un'API fluida per creare, formattare ed esportare grafici. Questo significa che puoi automatizzare la generazione di report, produrre un branding coerente e integrare i grafici in flussi di lavoro Java più ampi. La libreria supporta anche opzioni di stile come colori, font e marker, consentendoti di allineare il grafico all'identità aziendale. Inoltre, gestisce compiti complessi come il binding dei dati e l'aggiornamento del grafico senza richiedere Microsoft Office.

## Come aggiungere un grafico a una diapositiva con Aspose.Slides in Java?

Carica o crea una `Presentation`, inserisci un `Chart` di tipo `BoxAndWhisker`, fornisci i dati e salva il file — tutto in poche righe di Java. L'API gestisce layout, scaling e rendering, così non devi manipolare XML manualmente. Puoi anche impostare titoli del grafico ed etichette degli assi programmaticamente per fornire contesto agli spettatori.

## Prerequisiti

- **Java Development Kit (JDK)**: JDK 8 o superiore.  
- **Aspose.Slides per Java Library**: Necessaria per la manipolazione di PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java.

## Configurazione di Aspose.Slides per Java

Aggiungi la libreria come dipendenza Maven, Gradle o manuale.

### Maven

Aggiungi la seguente dipendenza nel tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Nel tuo `build.gradle`, includi:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto

In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza

- **Prova gratuita** – esplora le funzionalità senza costi.  
- **Licenza temporanea** – da usare per valutazioni a breve termine.  
- **Acquisto** – sblocca tutte le funzionalità per carichi di lavoro di produzione.

Per inizializzare Aspose.Slides, assicurati che il JAR sia nel classpath e imposta eventuali file di licenza come descritto nella documentazione.

## Guida all'implementazione

Di seguito trovi una procedura passo‑passo. Ogni blocco è spiegato prima dello snippet in modo da capire esattamente cosa fa.

### Che cos'è la classe `Presentation`?

La classe `Presentation` è l'oggetto centrale in Aspose.Slides che rappresenta un intero file PowerPoint in memoria. Fornisce l'accesso a diapositive, grafici, forme e altri elementi, consentendo di creare, modificare e salvare presentazioni programmaticamente. Con questa classe puoi aggiungere nuove diapositive, inserire immagini e manipolare l'ordine delle diapositive con semplici chiamate API.

### Passo 1: creare o aprire una presentazione

Apri un PPTX esistente o avviane una nuova:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Suggerimento:** Se il file non esiste, Aspose.Slides creerà automaticamente una nuova presentazione vuota.

### Passo 2: aggiungere un grafico a scatola‑baffi alla diapositiva

Posiziona il grafico dove ti serve specificando posizione e dimensione (in punti):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Passo 3: cancellare i dati esistenti

Prima di inserire nuovi dati, rimuovi eventuali categorie o serie segnaposto:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Passo 4: configurare le categorie

Aggiungi le categorie (etichette dell'asse X) che appariranno sotto ogni scatola:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Nota:** Regola il testo dell'etichetta per corrispondere al dominio dei tuoi dati (ad es., “Q1”, “Prodotto A”).

### Passo 5: creare e personalizzare la serie

Ora crea una serie, imposta le opzioni visive e inserisci i valori numerici:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Puoi sostituire l'array `int[] data` con valori letti da un database, file CSV o qualsiasi altra fonte.

### Passo 6: salvare la presentazione

Persisti le modifiche in un nuovo file PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Passo 7: liberare le risorse

Disporre sempre dell'oggetto `Presentation` per liberare le risorse native:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Applicazioni pratiche

I grafici a scatola‑baffi sono indispensabili nell'analisi statistica e nella presentazione dei dati. Ecco alcuni scenari in cui brillano:

1. **Analisi finanziaria** – visualizzare la distribuzione dei ricavi per regione.  
2. **Controllo qualità** – individuare outlier nelle misurazioni di produzione.  
3. **Ricerca accademica** – mostrare la variabilità dei risultati sperimentali.  
4. **Ricerca di mercato** – confrontare le prestazioni di prodotto tra demografie.

Incorporare questi grafici direttamente nelle presentazioni PowerPoint permette agli stakeholder di cogliere dati complessi a colpo d'occhio.

## Considerazioni sulle prestazioni

Aspose.Slides può gestire presentazioni con **oltre 500 diapositive** e grafici con **oltre 100 000 punti dati**, mantenendo l'uso di memoria sotto i 200 MB su un server tipico. Per rimanere entro questi limiti:

- **Gestione della memoria** – disponi prontamente gli oggetti `Presentation`.  
- **Gestione dei dati** – carica solo i dati necessari; evita di inserire set di dati massivi direttamente nel workbook del grafico.  
- **Caricamento lazy** – quando generi molte diapositive, crea grafici solo per quelle che verranno visualizzate.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Il grafico appare vuoto** | Celle dei dati non popolate correttamente | Verifica che i riferimenti `wb.getCell` puntino alla riga/colonna corretta e che il valore non sia `null`. |
| **Outlier non mostrati** | `setShowOutlierPoints` impostato a `false` | Assicurati di chiamare `series.setShowOutlierPoints(true)`. |
| **Perdita di memoria** | Presentation non disposta | Avvolgi sempre l'uso in `try/finally` e chiama `dispose()`. |
| **Quartili errati** | Uso del metodo predefinito `Inclusive` | Passa a `Exclusive` tramite `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Domande frequenti

**D1: Cos'è un grafico a scatola‑baffi?**  
Un grafico a scatola‑baffi, noto anche come box plot, mostra la distribuzione dei dati basata su cinque statistiche riepilogative: minimo, primo quartile, mediana, terzo quartile e massimo, più eventuali outlier.

**D2: Posso personalizzare l'aspetto del grafico a scatola‑baffi?**  
Sì. Aspose.Slides consente di modificare colori, stili di linea, forme dei marker e aggiungere etichette dati tramite l'API di formattazione del grafico.

**D3: È possibile gestire più serie in un unico grafico?**  
Assolutamente. Ripeti il blocco di creazione della serie per ogni set di dati da visualizzare.

**D4: Come risolvere problemi di visualizzazione dei dati?**  
Assicurati che i dati siano scritti correttamente nelle celle del workbook e che le proprietà di visibilità come `setShowMeanLine` siano abilitate.

**D5: Dove posso ottenere supporto se incontro problemi?**  
Visita il [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per aiuto della community, o consulta la documentazione ufficiale.

**D6: Aspose.Slides supporta altri tipi di grafico?**  
Sì, supporta più di 50 tipologie di grafico — inclusi linee, barre, torta, dispersione, radar e funnel — così da scegliere la visualizzazione più adatta ai tuoi dati.

**D7: Posso generare grafici in un ambiente server senza interfaccia?**  
La libreria funziona completamente in scenari server‑side; non è necessaria alcuna installazione di UI o Microsoft Office.

## Risorse

- **Documentazione**: Esplora i riferimenti API dettagliati su [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Accedi alla pagina dei rilasci di Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Acquisto**: Acquista una licenza per sbloccare tutte le funzionalità [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Prova gratuita & licenza temporanea**: Inizia con una prova gratuita o richiedi una licenza temporanea [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Seguendo questa guida, sei ora pronto a generare programmaticamente grafici a scatola‑baffi perspicaci nelle tue applicazioni Java e incorporarli direttamente nelle presentazioni PowerPoint. Buon coding!

---

**Ultimo aggiornamento:** 2026-08-21  
**Testato con:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autore:** Aspose

## Tutorial correlati

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}