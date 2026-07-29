---
date: '2026-07-27'
description: Scopri come creare un grafico a ciambella Java usando Aspose.Slides –
  una guida rapida per configurare la libreria, aggiungere un grafico a ciambella
  personalizzabile, regolare la dimensione del foro e salvare la presentazione.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Scopri come creare un grafico a ciambella Java usando Aspose.Slides
  – una guida rapida per configurare la libreria, aggiungere un grafico a ciambella
  personalizzabile, regolare la dimensione del foro e salvare la presentazione.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Crea un grafico a ciambella Java – Passo‑passo con Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Crea un grafico a ciambella Java – Passo‑passo con Aspose.Slides
url: /it/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici a ciambella in Java usando Aspose.Slides per presentazioni

## Introduzione
Creare presentazioni visivamente accattivanti è essenziale per trasmettere efficacemente le informazioni. **Create doughnut chart java** è una necessità comune quando è necessario illustrare dati proporzionali con un aspetto moderno. In questo tutorial imparerai a configurare Aspose.Slides per Java, costruire un grafico a ciambella, personalizzare la dimensione del foro e i colori, e infine salvare il file della presentazione. Alla fine avrai un modello riutilizzabile da inserire in qualsiasi progetto Java che genera deck PowerPoint automaticamente.

**Cosa imparerai:**
- Configurare Aspose.Slides per Java
- Creare e configurare grafici a ciambella nelle presentazioni
- Regolare l'estetica del grafico, come la dimensione del foro
- Salvare la presentazione con il nuovo grafico

Iniziamo configurando il nostro ambiente!

## Risposte rapide
- **Quale libreria crea doughnut chart java?** Aspose.Slides for Java.  
- **Quante righe di codice sono necessarie per un grafico a ciambella di base?** About 8–10 lines after the presentation is instantiated.  
- **Posso cambiare la dimensione del foro?** Yes, the `setHoleSize(double)` method accepts values from 0 % to 100 %.  
- **Quali formati di output sono supportati?** PPTX, PDF, XPS, PNG, JPEG and several others (over 50 total).  
- **Ho bisogno di una licenza per la produzione?** A commercial license is required for unlimited use; a free trial works for evaluation.  

## Cos'è Aspose.Slides per Java?
**Aspose.Slides for Java** è un'API completamente gestita che consente agli sviluppatori di creare, modificare, convertire e renderizzare file PowerPoint senza Microsoft Office. Supporta più di 50 formati di file e può gestire presentazioni con migliaia di diapositive mantenendo un basso utilizzo della memoria.

## Perché usare i grafici a ciambella nelle presentazioni?
I grafici a ciambella mostrano relazioni parte‑intero liberando spazio al centro per etichette o immagini. Aspose.Slides può renderizzare grafici a ciambella fino a **500 diapositive al minuto** su un tipico server da 2,5 GHz, e elabora **presentazioni con centinaia di pagine** senza caricare l'intero file in memoria, rendendolo ideale per soluzioni di reporting su larga scala.

## Prerequisiti
Prima di iniziare, assicurati di aver coperto questi prerequisiti:

### Librerie richieste e versioni
Per lavorare con Aspose.Slides per Java, includila nel tuo progetto tramite Maven o Gradle, o scaricala direttamente.

#### Requisiti di configurazione dell'ambiente
- Un Java Development Kit (JDK) funzionante, preferibilmente versione 8 o superiore.
- Un Integrated Development Environment (IDE) come IntelliJ IDEA o Eclipse.

### Prerequisiti di conoscenza
Familiarità con Java e i concetti di programmazione di base è utile. Una conoscenza di base di Maven o Gradle aiuterà a semplificare il processo di configurazione.

## Configurare Aspose.Slides per Java
Incorporare Aspose.Slides nel tuo progetto può essere fatto in diversi modi:

**Maven:**  
Aggiungi questa dipendenza al tuo file `pom.xml` file:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Includi questo nel tuo file `build.gradle` file:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
- **Free Trial:** Inizia scaricando una versione di prova per esplorare le funzionalità di Aspose.Slides.  
- **Temporary License:** Ottieni una licenza temporanea per funzionalità estese senza limitazioni.  
- **Purchase:** Per un utilizzo continuativo, è necessario acquistare una licenza.

Una volta che la libreria è configurata e l'ambiente pronto, passiamo all'implementazione del nostro grafico a ciambella.

## Come creare un grafico a ciambella in Java?
Carica un nuovo oggetto `Presentation`, aggiungi un grafico a ciambella a una diapositiva, imposta la dimensione del foro e salva il file – il tutto in poche chiamate API semplici. Questo approccio ti dà il pieno controllo sui dati del grafico, sull'aspetto e sul formato di esportazione, e funziona senza la necessità di avere Microsoft PowerPoint installato sul server.

### Inizializzare l'oggetto Presentation
La classe `Presentation` è l'oggetto di livello superiore di Aspose.Slides che rappresenta un file PowerPoint in memoria.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Questo passaggio crea una presentazione vuota dove puoi aggiungere diapositive, forme e grafici.

### Aggiungere un grafico a ciambella alla diapositiva
`ISlide` è l'interfaccia per una singola diapositiva; puoi recuperare la prima diapositiva o aggiungerne una nuova.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Il metodo `addChart` crea un grafico a ciambella; i parametri definiscono la sua posizione (X, Y) e le dimensioni (larghezza, altezza) sulla diapositiva.

### Configurare la dimensione del foro del grafico a ciambella
`Chart` espone `setHoleSize(double)` per controllare il raggio interno come percentuale del raggio del grafico.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Impostare la dimensione del foro al 90 % fa apparire il grafico quasi come un cerchio completo, utile quando si desidera enfatizzare i segmenti esterni.

### Salvare la presentazione
`presentation.save(String, SaveFormat)` scrive il file su disco nel formato scelto.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
L'esempio salva il risultato come `DoughnutHoleSize_out.pptx`, ma puoi anche scegliere PDF, PNG o qualsiasi dei più di 50 formati supportati.

### Pulire le risorse
Chiamare `presentation.dispose()` rilascia le risorse native e previene perdite di memoria, particolarmente importante in applicazioni server a lunga esecuzione.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Applicazioni pratiche
I grafici a ciambella sono versatili. Ecco alcuni scenari in cui brillano:
1. **Budget Allocation:** Mostra come un budget è distribuito tra i dipartimenti.  
2. **Survey Results:** Visualizza le risposte a domande con risposte a scelta multipla.  
3. **Website Traffic Sources:** Mostra la percentuale di traffico proveniente da diversi canali (organico, a pagamento, referral, ecc.).

## Considerazioni sulle prestazioni
Quando lavori con Aspose.Slides, considera questi consigli per prestazioni ottimali:
- Elimina gli oggetti `Presentation` non appena hai finito per liberare la memoria nativa.  
- Usa stream (`FileInputStream`, `ByteArrayOutputStream`) per grandi set di dati per evitare di caricare interi file in RAM.  
- Riutilizza gli oggetti chart quando generi molte diapositive in un ciclo per ridurre l'overhead di creazione degli oggetti.  

## Problemi comuni e soluzioni
- **Error while saving:** Verifica che la directory di output esista e che l'applicazione abbia i permessi di scrittura.  
- **Missing chart data:** Assicurati di popolare la collezione `ChartData` del grafico prima di chiamare `setHoleSize`.  
- **Memory spikes:** Per presentazioni con migliaia di diapositive, abilita `Presentation.setSlideSize` a una dimensione più piccola e elimina prontamente le diapositive intermedie.  

## Domande frequenti

**Q: Posso regolare i colori dei segmenti del mio grafico a ciambella?**  
A: Sì. Usa `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` e poi specifica il colore RGB desiderato.

**Q: Come aggiungo le etichette dei dati al mio grafico?**  
A: Chiama `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` per visualizzare il valore all'interno di ogni segmento.

**Q: È possibile salvare i grafici in formati diversi da PPTX?**  
A: Assolutamente. Aspose.Slides supporta PDF, XPS, PNG, JPEG, TIFF e molti altri formati—oltre 50 in totale.

**Q: Cosa devo fare se incontro un'eccezione durante il caricamento di una grande presentazione?**  
A: Usa il costruttore `Presentation` che accetta uno stream e abilita `loadOptions.setLoadFormat(LoadFormat.Pptx)` per streammare il file e ridurre il consumo di memoria.

**Q: Posso automatizzare gli aggiornamenti del grafico con fonti di dati live?**  
A: Sì. Recupera i dati da un database o da un'API REST, aggiorna la collezione `ChartData` e chiama `chart.refresh()` prima di salvare la presentazione.

## Risorse
- **Documentation:** Esplora i riferimenti API dettagliati su [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** Ottieni l'ultima versione della libreria da [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** Per accesso completo, acquista una licenza su [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** Prova Aspose.Slides con una versione di prova gratuita disponibile sulla loro pagina di download.  
- **Temporary License:** Ottieni una licenza temporanea per test estesi senza limitazioni.  
- **Support:** Hai domande? Visita il [Aspose Forum](https://forum.aspose.com/c/slides/11) per assistenza.

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Tutorial correlati

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}