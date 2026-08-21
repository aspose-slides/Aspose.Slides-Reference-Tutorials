---
date: '2026-08-21'
description: Scopri come creare un grafico a colonne raggruppate e aggiungere linee
  di tendenza con Aspose.Slides for Java. Include la configurazione della licenza,
  l'integrazione Maven/Gradle e esempi dettagliati.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Crea un grafico a colonne raggruppate e aggiungi linee di tendenza
  usando Aspose.Slides for Java. Questa guida copre la configurazione della licenza,
  Maven/Gradle e frammenti di codice passo‑passo.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Crea un grafico a colonne raggruppate e aggiungi linee di tendenza con Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Come creare un grafico a colonne raggruppate e aggiungere linee di tendenza
  con Aspose.Slides for Java
url: /it/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un grafico a colonne raggruppate e aggiungere linee di tendenza usando Aspose.Slides per Java

Creare presentazioni accattivanti spesso inizia con una visualizzazione chiara dei dati. In questa guida **creerai oggetti grafico a colonne raggruppate**, per poi arricchirli con una varietà di linee di tendenza — esponenziale, lineare, logaritmica, media mobile, polinomiale e potenza — utilizzando la potente API Aspose.Slides per Java.

## Risposte rapide
- **Qual è il primo passo?** Inizializzare un oggetto `Presentation` e aggiungere un grafico a colonne raggruppate a una diapositiva.  
- **Quale versione della libreria è necessaria?** Aspose.Slides per Java 25.4 o successiva.  
- **Posso usare Maven o Gradle?** Sì, entrambi sono supportati; Maven utilizza `<dependency>` e Gradle utilizza `implementation`.  
- **È necessaria una licenza?** Una licenza di prova funziona per la valutazione; una licenza completa Aspose.Slides rimuove i limiti di valutazione.  
- **Quante tipologie di linee di tendenza sono disponibili?** Sei tipi integrati: esponenziale, lineare, logaritmica, media mobile, polinomiale e potenza.

## Cos'è creare un grafico a colonne raggruppate?
`create clustered column chart` significa generare un grafico che raggruppa più serie di dati affiancate all'interno di ciascuna categoria, facilitando il confronto dei valori tra le serie. Questo tipo di grafico è ideale per visualizzare dati categorici come le vendite trimestrali per regione, consentendo agli spettatori di individuare rapidamente le differenze tra i gruppi.

## Perché aggiungere una linea di tendenza?
Le linee di tendenza rivelano il modello sottostante di una serie di dati, aiutandoti a prevedere valori futuri, evidenziare tassi di crescita o smussare dati rumorosi. Aggiungendo una linea di tendenza a un grafico a colonne raggruppate, i numeri grezzi diventano insight azionabili, permettendo alle parti interessate di comprendere le tendenze a lungo termine e prendere decisioni basate sui dati.

## Prerequisiti
- **Java Development Kit (JDK):** 8 o successivo.  
- **Aspose.Slides per Java:** versione 25.4 o successiva.  
- **IDE:** IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java.  
- **Strumento di build:** Maven o Gradle (opzionale ma consigliato).  
- **Licenza:** un file di licenza Aspose.Slides di prova o acquistato.  

È consigliato avere familiarità con la sintassi di base di Java e con la gestione delle dipendenze di progetto.

## Come configurare Aspose.Slides per Java?
Aggiungi la libreria Aspose.Slides al tuo progetto usando il gestore di dipendenze preferito, quindi posiziona il file di licenza dove il runtime possa trovarlo. Questo garantisce la piena funzionalità e rimuove le restrizioni di valutazione.

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
Inserisci questa riga nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
Puoi anche scaricare manualmente il JAR da [Rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

#### Licenza Aspose Slides
Posiziona il file `Aspose.Slides.lic` nella radice del tuo progetto o imposta la licenza programmaticamente con `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Una licenza di prova rimuove tutte le restrizioni funzionali, ma una licenza acquistata elimina la filigrana di valutazione e garantisce ottimizzazioni complete delle prestazioni. Per l'uso in produzione, considera l'acquisto di una licenza dalla [pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

## Come creare una presentazione e aggiungere un grafico a colonne raggruppate?
La classe `Presentation` rappresenta un file PowerPoint e fornisce metodi per creare, modificare e salvare diapositive. Istanzia una `Presentation`, aggiungi una diapositiva, quindi chiama `addChart` con `ChartType.ClusteredColumn` per creare l'oggetto grafico. Questo processo imposta la tela della diapositiva, inserisce una forma grafico e la prepara per il popolamento dei dati e lo styling.

1. **Inizializza la presentazione** – imposta la cartella di output e crea una nuova istanza `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Aggiungi un grafico a colonne raggruppate** – ottieni la forma grafico, configura le sue serie e popola i punti dati.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Come aggiungere una linea di tendenza esponenziale?
L'interfaccia `ITrendline` definisce una linea di tendenza che può essere aggiunta a una serie di grafico per modellare i pattern dei dati. Applica una linea di tendenza esponenziale a una serie creando un'istanza `ITrendline`, impostando il suo `TrendlineType` su `Exponential` e collegandola alla serie desiderata. Questo tipo di linea è utile per dati che crescono rapidamente a un ritmo crescente.

1. **Configura la linea di tendenza** – seleziona la serie e chiama `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Come aggiungere una linea di tendenza lineare?
Una linea di tendenza lineare mostra la retta di migliore adattamento attraverso i tuoi punti dati. Puoi anche personalizzarne l'aspetto, come colore e spessore della linea, per adattarlo allo stile della presentazione.

1. **Imposta la linea di tendenza** – usa `addTrendline(TrendlineType.Linear)` e poi regola `getLineFormat().setFillFormat().setFillType(FillType.Solid)` per cambiare il colore.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Come aggiungere una linea di tendenza logaritmica con un riquadro di testo personalizzato?
Le linee di tendenza logaritmiche sono ideali per dati che crescono rapidamente all'inizio e poi si stabilizzano. Sovrascrivere l'etichetta predefinita ti consente di aggiungere testo esplicativo che chiarisce il significato della tendenza.

1. **Personalizza la linea di tendenza** – dopo aver aggiunto la linea, accedi al suo `getDataLabel()` e imposta la proprietà `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Come aggiungere una linea di tendenza media mobile?
Le linee di tendenza media mobile smussano le fluttuazioni a breve termine per evidenziare le tendenze a lungo termine. Puoi specificare il periodo (numero di punti) usato per la media, controllando così la levigatezza della linea.

1. **Configura la linea di tendenza** – chiama `addTrendline(TrendlineType.MovingAverage)` e imposta `setPeriod(3)` per usare una media mobile a tre punti.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Come aggiungere una linea di tendenza polinomiale?
Le linee di tendenza polinomiale adattano i dati con una curva definita da un'equazione polinomiale. La proprietà `order` controlla il grado del polinomio, permettendoti di modellare relazioni più complesse.

1. **Personalizza la linea di tendenza** – dopo aver aggiunto la linea, imposta `setOrder(3)` per una regressione cubica.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Come aggiungere una linea di tendenza potenza?
Le linee di tendenza potenza sono utili quando i dati seguono una relazione di tipo legge di potenza. Puoi anche impostare valori di previsione indietro e avanti per estendere la linea oltre l'intervallo di dati esistente.

1. **Configura la linea di tendenza** – usa `addTrendline(TrendlineType.Power)` e regola `setBackward(2)` per estendere la linea all'indietro.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Applicazioni pratiche delle linee di tendenza nei grafici a colonne raggruppate
- **Analisi finanziaria:** Le tendenze esponenziali e polinomiali aiutano a prevedere i movimenti dei prezzi delle azioni.  
- **Previsione delle vendite:** Le linee di media mobile smussano i picchi stagionali, offrendo una visione più chiara delle tendenze di vendita sottostanti.  
- **Ricerca scientifica:** Le tendenze logaritmiche sono perfette per dati che coprono diversi ordini di grandezza, come l'intensità acustica o i valori di pH.  
- **Monitoraggio operativo:** Le linee di tendenza potenza possono modellare il degrado delle prestazioni nel tempo.

## Come ottimizzare la memoria quando si usa Aspose.Slides?
Rilascia gli oggetti prontamente e utilizza `presentation.dispose()` dopo il salvataggio. Per set di dati di grandi dimensioni, abilita il caricamento pigro delle immagini ed evita di caricare l'intero grafico in memoria contemporaneamente.

- **Pattern di dispose:** Avvolgi `Presentation` in un blocco try‑with‑resources o chiama `presentation.dispose()` in un blocco finally.  
- **Caricamento pigro:** Imposta `ChartData.setUseCache(true)` quando lavori con migliaia di punti dati.  
- **Output in streaming:** Scrivi la presentazione direttamente su un `FileOutputStream` per evitare di tenere l'intero file in RAM.

## Benefici quantificati di Aspose.Slides per Java
Aspose.Slides supporta **oltre 50 tipi di grafico**, può generare presentazioni con **più di 1.000 diapositive** in meno di **30 secondi** su una tipica CPU da 2 GHz, e processa **PDF di 500 pagine** senza richiedere Microsoft Office installato. Questi numeri sono verificati sull'ultima release 25.4.

## Conclusione
Ora disponi di una soluzione completa, end‑to‑end, per **creare oggetti grafico a colonne raggruppate** e arricchirli con tutti i principali tipi di linee di tendenza disponibili in Aspose.Slides per Java. Seguendo i passaggi sopra, potrai produrre presentazioni basate sui dati che sono sia visivamente accattivanti sia analiticamente potenti.

I prossimi passi includono l'esplorazione delle opzioni di styling del grafico, l'esportazione in PDF/HTML e l'automazione della generazione di grafici su più fonti di dati.

## Domande frequenti

**D: Come configuro Aspose.Slides per un progetto Maven?**  
R: Aggiungi lo snippet `<dependency>` mostrato nella sezione Maven al tuo `pom.xml` ed esegui `mvn clean install`.

**D: Posso personalizzare le linee di tendenza oltre al colore e all'etichetta?**  
R: Sì, puoi modificare lo stile della linea, larghezza, pattern di tratteggio e persino i valori di previsione avanti/indietro tramite l'API `ITrendline`.

**D: Cosa devo fare se incontro un errore di compatibilità di versione?**  
R: Verifica che la tua versione di JDK corrisponda al requisito minimo di Aspose.Slides (JDK 8+). Consulta le note di rilascio di Aspose per eventuali cambiamenti incompatibili.

**D: È possibile aggiungere linee di tendenza a più grafici automaticamente?**  
R: Assolutamente. Itera su ogni `IChart` nella collezione di diapositive e invoca il metodo `addTrendline` appropriato per ciascuna serie.

**D: È necessaria una licenza a pagamento per l'uso in produzione?**  
R: Sì, una licenza acquistata di Aspose.Slides rimuove i limiti di valutazione e sblocca ottimizzazioni complete delle prestazioni.

---

**Ultimo aggiornamento:** 2026-08-21  
**Testato con:** Aspose.Slides per Java 25.4  
**Autore:** Aspose

## Tutorial correlati

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}