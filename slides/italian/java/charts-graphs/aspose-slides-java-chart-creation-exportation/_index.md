---
date: '2026-02-09'
description: Scopri come creare grafici ed esportarli in Excel utilizzando Aspose.Slides
  per Java. Padroneggia la visualizzazione dei dati, le diapositive di report aziendali
  e la generazione di cartelle di lavoro.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Come creare un grafico con Aspose.Slides per Java
url: /it/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico usando Aspose.Slides per Java

**Padroneggia le tecniche di visualizzazione dei dati con Aspose.Slides per Java**

Nel panorama odierno guidato dai dati, *come creare un grafico* programmaticamente è una competenza che può trasformare numeri grezzi in storie visive accattivanti. Che tu stia costruendo una presentazione di report aziendali o una dashboard analitica interattiva, Aspose.Slides per Java ti offre il potere di generare, personalizzare ed esportare grafici direttamente dal tuo codice. In questo tutorial imparerai a creare oggetti grafico, esportare i dati del grafico in Excel e collegare i grafici a cartelle di lavoro esterne per una gestione dei dati senza soluzione di continuità.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.Slides per Java (v25.4+).  
- **Posso esportare i dati del grafico in Excel?** Sì – usa `readWorkbookStream()` e scrivi i byte in un file *.xlsx*.  
- **Quale versione di Java è richiesta?** JDK 16 o superiore.  
- **Ho bisogno di una licenza?** Una prova gratuita funziona per la valutazione; è necessaria una licenza permanente per la produzione.  
- **Quale tipo di grafico è mostrato?** Un grafico a torta, ma lo stesso approccio funziona per grafici a barre, a linee e altri tipi di grafico.

## Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è un'API pure‑Java che consente agli sviluppatori di creare, modificare e convertire presentazioni PowerPoint senza Microsoft Office. Supporta una gamma completa di tipi di grafico, data binding e capacità di esportazione, rendendola ideale per progetti **data visualization java**.

## Perché usare Aspose.Slides per creare grafico ed esportarlo in Excel?
- **Nessuna installazione di Office** – funziona su qualsiasi server o ambiente cloud.  
- **Libreria di grafici ricca** – decine di tipi di grafico e controllo completo dello stile.  
- **Esportazione diretta in Excel** – genera una cartella di lavoro esterna per analisi successive.  
- **Orientata alle prestazioni** – basso consumo di memoria e elaborazione veloce per presentazioni di grandi dimensioni.

## Prerequisiti
Prima di immergerci, assicurati di avere quanto segue:

### Librerie richieste e versioni
- **Aspose.Slides per Java** versione 25.4 o successiva

### Requisiti di configurazione dell'ambiente
- Java Development Kit (JDK) 16 o superiore  
- Un IDE come IntelliJ IDEA o Eclipse (o qualsiasi editor di testo tu preferisca)

### Prerequisiti di conoscenza
- Competenze di base di programmazione Java  
- Familiarità con gli strumenti di build Maven o Gradle

## Configurare Aspose.Slides per Java
Aggiungi la libreria al tuo progetto usando il tuo sistema di build preferito.

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

In alternativa, puoi [scaricare direttamente l'ultima versione](https://releases.aspose.com/slides/java/).

### Passaggi per l'acquisizione della licenza
Aspose.Slides offre una licenza di prova gratuita per esplorare tutte le sue funzionalità. Puoi anche richiedere una licenza temporanea o acquistarne una per un uso prolungato. Segui questi passaggi:

1. Visita la [pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per ottenere la tua licenza.  
2. Per una prova gratuita, scarica da [Releases](https://releases.aspose.com/slides/java/).  
3. Richiedi una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, inizializzalo nella tua applicazione Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guida passo‑passo

### Come creare un grafico – Caricare una presentazione
Caricare un file PowerPoint esistente è il primo passo prima di poter aggiungere o modificare grafici.

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

**Spiegazione:**  
- `Presentation` rappresenta il file PowerPoint.  
- Chiama sempre `dispose()` per rilasciare le risorse native.

### Come creare un grafico – Aggiungere un grafico a torta a una diapositiva
Ora inseriremo un grafico a torta, perfetto per mostrare dati proporzionali.

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

**Spiegazione:**  
- `addChart` inserisce il grafico nella prima diapositiva.  
- I parametri definiscono il tipo di grafico, la posizione X/Y e le dimensioni.

### Come esportare il grafico in Excel – Esportare i dati del grafico
Esportare i dati del grafico consente agli analisti di lavorare con i numeri in Excel, permettendo approfondimenti più dettagliati.

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

**Spiegazione:**  
- `readWorkbookStream()` estrae la cartella di lavoro Excel sottostante del grafico come array di byte.  
- L'array di byte viene scritto in `externalWorkbook1.xlsx`, fornendoti un file Excel pronto all'uso.

### Come creare un grafico – Impostare una cartella di lavoro esterna per dati dinamici
Collegare un grafico a una cartella di lavoro esterna ti permette di aggiornare il grafico semplicemente modificando il file Excel.

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

**Spiegazione:**  
- `setExternalWorkbook` collega il grafico al file Excel specificato, consentendo aggiornamenti dei dati in tempo reale senza ricostruire la diapositiva.

## Applicazioni pratiche
Aspose.Slides offre soluzioni versatili per vari scenari reali:

1. **Diapositive di report aziendali:** Genera automaticamente grafici di performance trimestrale dai tuoi flussi di dati.  
2. **Presentazioni accademiche:** Trasforma i dati della ricerca in visualizzazioni chiare senza creare grafici manualmente.  
3. **Analisi finanziaria:** Esporta i dati del grafico in Excel per consentire agli auditor di verificare i numeri.  
4. **Analisi di marketing:** Visualizza le metriche delle campagne e condividi cartelle di lavoro modificabili con gli stakeholder.

## Problemi comuni e risoluzione
- **`FileNotFoundException`** – Verifica che `dataDir` punti a una cartella valida e che il percorso di output sia scrivibile.  
- **Memory leaks** – Chiama sempre `pres.dispose()` in un blocco `finally` per liberare le risorse native.  
- **Chart not appearing** – Assicurati che l'indice della diapositiva (`get_Item(0)`) corrisponda a una diapositiva che esiste realmente.

## Domande frequenti

**D: Posso usare un tipo di grafico diverso (ad es., Barre, Linea) con lo stesso codice?**  
R: Sì. Sostituisci `ChartType.Pie` con qualsiasi altro valore enum `ChartType` come `ChartType.Bar` o `ChartType.Line`.

**D: È possibile aggiornare la cartella di lavoro esterna dopo la creazione del grafico?**  
R: Assolutamente. Modifica direttamente il file Excel; il grafico collegato rifletterà le modifiche al prossimo riapertura della presentazione.

**D: Ho bisogno di una licenza separata per la funzionalità di esportazione in Excel?**  
R: No. La capacità di esportazione in Excel è inclusa nella licenza standard di Aspose.Slides per Java.

**D: Quali versioni di Java sono supportate?**  
R: Aspose.Slides per Java supporta JDK 16 e versioni successive; versioni precedenti potrebbero funzionare ma non sono testate ufficialmente.

**D: Come posso incorporare la cartella di lavoro Excel generata all'interno del file PPTX?**  
R: Usa `chart.getChartData().setExternalWorkbook(null)` per incorporare la cartella di lavoro, oppure mantieni il collegamento esterno per aggiornamenti dinamici.

---

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}