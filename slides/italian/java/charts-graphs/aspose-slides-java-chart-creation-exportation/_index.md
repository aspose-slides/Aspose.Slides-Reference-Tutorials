---
date: '2026-06-03'
description: Scopri come esportare chart in Excel e creare chart Java utilizzando
  Aspose.Slides per Java. Padroneggia data visualization, business report slides e
  workbook generation.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Esporta Chart in Excel e crea Charts con Aspose.Slides
url: /it/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Esporta il grafico in Excel e crea grafici con Aspose.Slides

**Padroneggia le tecniche di visualizzazione dei dati con Aspose.Slides per Java**

Nel panorama odierno guidato dai dati, *esportare un grafico in Excel* programmaticamente è una competenza che può trasformare numeri grezzi in storie visive accattivanti. Che tu stia creando una presentazione di report aziendali o una dashboard analitica interattiva, Aspose.Slides per Java ti offre la possibilità di generare, personalizzare ed esportare grafici direttamente dal tuo codice. In questo tutorial imparerai a creare oggetti grafico, esportare i dati del grafico in Excel e collegare i grafici a cartelle di lavoro esterne per una gestione dei dati senza interruzioni.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides per Java (v25.4+).  
- **Posso esportare i dati del grafico in Excel?** Sì – usa `readWorkbookStream()` e scrivi i byte in un file *.xlsx*.  
- **Quale versione di Java è richiesta?** JDK 16 o superiore.  
- **È necessaria una licenza?** Una licenza di prova gratuita è sufficiente per la valutazione; è richiesta una licenza permanente per la produzione.  
- **Quale tipo di grafico è mostrato?** Un grafico a torta, ma lo stesso approccio funziona per grafici a barre, a linee e altri tipi.

## Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è un'API pure‑Java che consente agli sviluppatori di creare, modificare e convertire presentazioni PowerPoint senza Microsoft Office. Fornisce un set completo di classi per la manipolazione delle diapositive, la generazione di grafici e la conversione di formati, abilitando soluzioni di reporting automatizzate. Supporta **oltre 50 tipi di grafico**, binding completo dei dati ed esportazione diretta in Excel, rendendola ideale per progetti di **data visualization java**.

## Perché usare Aspose.Slides per creare grafico ed esportare il grafico in Excel?
Esporta il grafico in Excel in modo rapido e affidabile. Aspose.Slides elimina la necessità di installazioni di Office, offre **oltre 50 stili di grafico integrati** e elabora presentazioni **fino a 300 MB in meno di 30 secondi** su hardware server standard. Ottieni anche la generazione nativa di cartelle di lavoro Excel, che consente agli analisti di lavorare con i numeri grezzi senza copie manuali.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Librerie richieste e versioni
- **Aspose.Slides per Java** versione 25.4 o successiva (supporta JDK 16+)

### Requisiti per la configurazione dell'ambiente
- Java Development Kit (JDK) 16 o superiore  
- Un IDE come IntelliJ IDEA o Eclipse (o qualsiasi editor di testo preferito)

### Prerequisiti di conoscenza
- Conoscenze di base di programmazione Java  
- Familiarità con gli strumenti di build Maven o Gradle

## Configurare Aspose.Slides per Java
Aggiungi la libreria al tuo progetto usando il sistema di build preferito.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, puoi [scaricare l'ultima versione direttamente](https://releases.aspose.com/slides/java/).

### Passaggi per l'acquisizione della licenza
Aspose.Slides offre una licenza di prova gratuita per esplorare tutte le sue funzionalità. Puoi anche richiedere una licenza temporanea o acquistarne una per uso prolungato. Segui questi passaggi:

1. Visita la [pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per ottenere la tua licenza.  
2. Per una prova gratuita, scarica da [Releases](https://releases.aspose.com/slides/java/).  
3. Richiedi una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, inizializzalo nella tua applicazione Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guida passo‑passo

### Come creare un grafico – Carica una presentazione
Carica un file PowerPoint esistente prima di poter aggiungere o modificare grafici.  
La classe `Presentation` rappresenta un file PowerPoint in memoria, esponendo diapositive, forme e oggetti grafico.  
Carica il tuo file con `new Presentation("input.pptx")`, quindi lavora con la prima diapositiva usando `presentation.getSlides().get_Item(0)`. Chiama sempre `presentation.dispose()` in un blocco `finally` per rilasciare le risorse native.

### Come creare un grafico – Aggiungi un grafico a torta a una diapositiva
Inserisci un grafico a torta, perfetto per mostrare dati proporzionali.  
L'interfaccia `IChart` è il punto di ingresso principale per la manipolazione dei grafici; `addChart` crea un nuovo grafico sulla diapositiva target. Specifica il tipo di grafico (`ChartType.Pie`), le coordinate X/Y e larghezza/altezza. Dopo la creazione, puoi personalizzare titoli, legenda e serie di dati tramite l'oggetto `ChartData`.

### Come esportare il grafico in Excel – Esporta i dati del grafico
L'esportazione dei dati del grafico consente agli analisti di lavorare con i numeri in Excel, permettendo approfondimenti più dettagliati.  
`readWorkbookStream()` restituisce la cartella di lavoro Excel sottostante al grafico come array di byte. Chiama `chart.getChartData().readWorkbookStream()` per recuperare la cartella di lavoro e scrivi questo array in un file denominato `externalWorkbook1.xlsx` usando le normali API I/O di Java. Il file Excel risultante contiene esattamente i dati utilizzati dal grafico, pronto per ulteriori analisi.

### Come creare un grafico – Imposta cartella di lavoro esterna per dati dinamici
Collega un grafico a una cartella di lavoro esterna per consentire aggiornamenti dei dati in tempo reale senza ricostruire la diapositiva.  
`setExternalWorkbook()` associa il grafico a un file Excel esterno per aggiornamenti dinamici. Usa `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` per collegare il grafico al file esterno. Quando la cartella di lavoro Excel viene modificata, il grafico riflette automaticamente le modifiche al prossimo riapertura della presentazione, supportando scenari di reporting dinamico.

## Applicazioni pratiche
Aspose.Slides offre soluzioni versatili per vari scenari reali:

1. **Diapositive di report aziendali:** Genera automaticamente grafici di performance trimestrale dai tuoi flussi di dati.  
2. **Presentazioni accademiche:** Trasforma i dati della ricerca in visualizzazioni chiare senza dover creare manualmente i grafici.  
3. **Analisi finanziaria:** Esporta i dati del grafico in Excel per gli auditor, riducendo gli errori manuali.  
4. **Analisi di marketing:** Visualizza le metriche delle campagne e condividi cartelle di lavoro modificabili con gli stakeholder per decisioni collaborative.  
5. **Generazione automatica di dashboard:** Combina l'API di creazione grafici con job programmati per produrre deck diapositive aggiornati ogni mattina.

## Problemi comuni e risoluzione
- **`FileNotFoundException`** – Verifica che `dataDir` punti a una cartella valida e che il percorso di output sia scrivibile.  
- **Perdite di memoria** – Chiama sempre `presentation.dispose()` in un blocco `finally` per liberare le risorse native.  
- **Il grafico non appare** – Assicurati che l'indice della diapositiva (`get_Item(0)`) corrisponda a una diapositiva esistente e che le dimensioni del grafico siano entro i limiti della diapositiva.  
- **L'esportazione Excel genera un file vuoto** – Conferma che il grafico contenga effettivamente serie di dati prima di chiamare `readWorkbookStream()`.

## Domande frequenti

**D: Posso usare un tipo di grafico diverso (ad es., Barre, Linea) con lo stesso codice?**  
R: Sì. Sostituisci `ChartType.Pie` con qualsiasi altro valore dell'enumerazione `ChartType`, come `ChartType.Bar` o `ChartType.Line`.

**D: È possibile aggiornare la cartella di lavoro esterna dopo la creazione del grafico?**  
R: Assolutamente. Modifica direttamente il file Excel; il grafico collegato rifletterà le modifiche al prossimo riapertura della presentazione.

**D: Ho bisogno di una licenza separata per la funzionalità di esportazione Excel?**  
R: No. La capacità di esportazione Excel è inclusa nella licenza standard di Aspose.Slides per Java.

**D: Quali versioni di Java sono supportate?**  
R: Aspose.Slides per Java supporta JDK 16 e versioni successive; versioni precedenti potrebbero funzionare ma non sono testate ufficialmente.

**D: Come posso incorporare la cartella di lavoro Excel generata all'interno del file PPTX?**  
R: Usa `chart.getChartData().setExternalWorkbook(null)` per incorporare la cartella di lavoro, oppure mantieni il collegamento esterno per aggiornamenti dinamici.

---

**Ultimo aggiornamento:** 2026-06-03  
**Testato con:** Aspose.Slides per Java 25.4 (classificatore JDK 16)  
**Autore:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea grafico in Java con Aspose.Slides – Aggiungi e valida i grafici](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recupera dati della cartella di lavoro dai grafici PowerPoint usando Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Come aggiornare l'intervallo dati di un grafico PowerPoint usando Aspose.Slides per Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}