---
date: '2026-05-29'
description: Scopri come creare un grafico a torta Aspose usando Aspose.Slides Maven,
  aggiungere un grafico a torta Java a una diapositiva e personalizzare i dati del
  grafico. Guida passo‑passo con configurazione Maven ed esempi reali.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Crea un grafico a torta Aspose – Aggiungi un grafico a una presentazione con
  Maven
url: /it/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere un grafico a torta a una presentazione usando Aspose.Slides Java

## Introduzione
In questa guida **creerai un grafico a torta aspose** con Aspose.Slides Maven e vedrai come incorporarlo in una diapositiva PowerPoint. Creare presentazioni visivamente accattivanti è fondamentale per trasmettere efficacemente le informazioni, soprattutto quando la visualizzazione dei dati gioca un ruolo chiave. Se desideri automatizzare questo processo con **aspose slides maven**, sei nel posto giusto. Ti guideremo nell'aggiungere un grafico a una diapositiva — specificamente un grafico a torta — e nel personalizzarlo per scenari reali.

### Cosa imparerai
- Come inizializzare un oggetto presentazione in Java.  
- Passaggi per **aggiungere un grafico a torta java** sulla prima diapositiva di una presentazione.  
- Accedere ai workbook dei dati del grafico e elencare i fogli di lavoro al loro interno.  

Scopriamo come puoi sfruttare Aspose.Slides Java per migliorare le tue presentazioni con grafici dinamici!

## Risposte rapide
- **Quale libreria aggiunge grafici via Maven?** aspose slides maven  
- **Quale tipo di grafico è mostrato?** Pie chart (add chart to slide)  
- **Versione minima di Java richiesta?** JDK 16 o successiva  
- **È necessaria una licenza per i test?** Una prova gratuita funziona; per la produzione è necessaria una licenza  
- **Dove posso trovare la dipendenza Maven?** Nella sezione di configurazione qui sotto  

## Cos'è Aspose Slides Maven?
Aspose.Slides per Java è un'API potente che consente agli sviluppatori di creare, modificare e rendere file PowerPoint in modo programmatico. Il pacchetto Maven (`aspose-slides`) semplifica la gestione delle dipendenze, permettendoti di concentrarti sulla creazione e personalizzazione delle diapositive — come aggiungere un grafico a torta — senza occuparsi della gestione a basso livello dei file.

## Perché usare Aspose.Slides Maven per aggiungere un grafico a una diapositiva?
Usare Aspose.Slides Maven ti consente di generare grafici direttamente dal codice Java senza modifiche manuali di PowerPoint. Fornisce un controllo programmatico completo sui tipi di grafico, le fonti di dati e lo stile, garantendo coerenza del brand e precisione. L'artifact Maven gestisce anche tutte le dipendenze necessarie, semplificando le compilazioni e consentendo un'integrazione fluida nei pipeline CI/CD.

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
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, puoi [scaricare l'ultima versione](https://releases.aspose.com/slides/java/) direttamente dal sito di Aspose.

### Acquisizione della licenza
Aspose.Slides per Java offre una prova gratuita con una licenza temporanea per i test. Per un uso di produzione senza limitazioni, acquista una licenza tramite la [pagina di acquisto](https://purchase.aspose.com/buy).

## Guida all'implementazione
Di seguito suddividiamo la soluzione in due funzionalità: aggiungere un grafico a torta e accedere al suo workbook dei dati.

### Funzione 1: Creare una presentazione e aggiungere un grafico
#### Panoramica
Questa sezione mostra come creare una nuova presentazione e **aggiungere un grafico a torta** alla prima diapositiva.

#### Come creare un grafico a torta aspose?
Carica la classe `Presentation`, aggiungi un grafico di tipo `ChartType.Pie` e salva il file. L'intera operazione richiede solo tre chiamate API e viene eseguita in meno di un secondo per un tipico mazzo di 10 diapositive, rendendola ideale per la generazione automatizzata di report.

#### Passo‑per‑passo

**Passo 1: Inizializzare un nuovo oggetto Presentation**  
La classe `Presentation` è l'oggetto di livello superiore di Aspose.Slides che rappresenta un file PowerPoint in memoria.  
```java
Presentation pres = new Presentation();
```
*Crea l'istanza `Presentation` che conterrà tutte le diapositive.*

**Passo 2: Aggiungere un grafico a torta**  
`ChartType.Pie` indica ad Aspose di renderizzare un grafico a torta.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Posiziona un grafico a torta alle coordinate (50, 50) con larghezza 400 e altezza 500.*

**Passo 3: Rilasciare le risorse**  
Chiamare `dispose()` rilascia le risorse native e previene perdite di memoria.  
```java
if (pres != null) pres.dispose();
```
*Rilascia le risorse native; chiama sempre `dispose()` quando hai finito.*

### Funzione 2: Accedere al workbook dei dati del grafico e ai fogli di lavoro
#### Panoramica
Scopri come accedere al workbook sottostante che memorizza i dati del grafico e iterare attraverso i suoi fogli di lavoro.

#### Come accedere al workbook dei dati del grafico?
Recupera l'`IChartDataWorkbook` dal grafico, quindi itera la sua collezione `Worksheets`. Questo workbook imita un file Excel, consentendoti di leggere, modificare o aggiungere serie di dati programmaticamente, e il grafico le rifletterà immediatamente quando aggiornato durante l'esecuzione senza riavviare.

#### Passo‑per‑passo

**Passo 1: (Riutilizzo) Inizializzare un nuovo oggetto Presentation**  
*Stesso della Funzione 1, Passo 1.*

**Passo 2: (Riutilizzo) Aggiungere un grafico a torta**  
*Stesso della Funzione 1, Passo 2.*

**Passo 3: Ottenere il workbook dei dati del grafico**  
`IChartDataWorkbook` è l'interfaccia che fornisce accesso in lettura/scrittura al workbook interno del grafico, simile a Excel.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Recupera l'`IChartDataWorkbook` collegato al grafico.*

**Passo 4: Iterare attraverso i fogli di lavoro**  
Gli oggetti `Worksheet` rappresentano fogli individuali all'interno del workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Stampa il nome di ogni foglio di lavoro, consentendoti di verificare la struttura dei dati.*

**Passo 5: Rilasciare le risorse**  
*Stesso della Funzione 1, Passo 3.*

## Applicazioni pratiche
- **Reporting dei dati:** Genera automaticamente mazzi di diapositive con metriche aggiornate per l'intelligence aziendale.  
- **Presentazioni accademiche:** Visualizza i risultati della ricerca senza creare manualmente i grafici.  
- **Materiale di marketing:** Mostra le prestazioni del prodotto o i risultati dei sondaggi istantaneamente.

## Considerazioni sulle prestazioni
- Aspose.Slides può gestire **oltre 50 formati di input e output** e processare presentazioni con centinaia di pagine senza caricare l'intero file in memoria.  
- Mantieni un numero ragionevole di diapositive e grafici; ogni grafico consuma memoria nativa.  
- Chiama sempre `dispose()` per liberare le risorse tempestivamente.  
- Ottimizza la gestione dei dati del workbook — evita di caricare dataset massivi in un unico grafico.

## Conclusione
Abbiamo illustrato come **aspose slides maven** ti consenta di **add chart to slide** programmaticamente e come lavorare con il workbook dei dati del grafico. Con questi blocchi costitutivi puoi automatizzare qualsiasi flusso di lavoro di reporting che richieda un output PowerPoint curato.

### Prossimi passi
- Esplora le opzioni di stile del grafico (colori, legende, etichette dati).  
- Collegati a fonti dati esterne (CSV, database) per popolare i grafici in modo dinamico.  
- Combina più tipi di grafico in una singola presentazione per una narrazione più ricca.

## Domande frequenti

**Q:** Come installo Aspose.Slides per Java?  
**A:** Usa la dipendenza Maven o Gradle mostrata sopra, o scarica la libreria dalla pagina dei rilasci.

**Q:** Quali sono i requisiti di sistema per Aspose.Slides?  
**A:** JDK 16 o successivo; la libreria funziona su qualsiasi piattaforma che supporta Java.

**Q:** Posso aggiungere altri tipi di grafico oltre ai grafici a torta?  
**A:** Sì, Aspose.Slides supporta grafici a barre, linee, dispersione, radar e più di 20 tipi di grafico.

**Q:** Come gestire presentazioni di grandi dimensioni in modo efficiente?  
**A:** Rilascia gli oggetti tempestivamente, limita le immagini ad alta risoluzione e riutilizza i modelli di grafico per mantenere basso l'uso della memoria.

**Q:** Dove posso trovare maggiori dettagli sulle funzionalità di Aspose.Slides?  
**A:** Visita la [documentazione Aspose](https://reference.aspose.com/slides/java/) per un riferimento API completo.

**Q:** È necessaria una licenza per l'uso commerciale?  
**A:** È necessaria una licenza valida per la produzione; è disponibile una prova gratuita per la valutazione.

**Q:** Il pacchetto Maven include tutte le capacità di grafico?  
**A:** Sì, l'artifact Maven `aspose-slides` contiene l'intero motore di grafici.

## Risorse
- Documentazione: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Scarica: [Ultime versioni](https://releases.aspose.com/slides/java/)
- Pagina di acquisto: [Pagina di acquisto](https://purchase.aspose.com/buy)
- Download di prova: [Download di prova](https://releases.aspose.com/slides/java/)
- Richiedi una licenza temporanea: [Richiedi una licenza temporanea](https://purchase.aspose.com/temporary-license/)
- Forum della community Aspose: [Forum della community Aspose](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## Tutorial correlati

- [Come personalizzare i colori del grafico a torta in Java con Aspose.Slides – Guida completa](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Creare un grafico a torta di torta in Java con Aspose.Slides: Guida completa](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animare i grafici PowerPoint usando Aspose.Slides per Java – Guida passo‑per‑passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}