---
date: '2026-01-14'
description: Scopri come esportare il grafico in Excel usando Aspose.Slides per Java
  e aggiungere una diapositiva con grafico a torta alle presentazioni. Guida passo‑passo
  con codice.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Esporta grafico in Excel con Aspose.Slides Java
url: /it/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Esporta un Grafico in Excel con Aspose.Slides per Java

**Padroneggia le Tecniche di Visualizzazione dei Dati con Aspose.Slides per Java**

Nel panorama odierno guidato dai dati, la possibilità di **export chart to excel** direttamente dalla tua applicazione Java può trasformare visualizzazioni PowerPoint statiche in set di dati riutilizzabili e analizzabili. Che tu debba generare report, alimentare pipeline di analisi o semplicemente consentire agli utenti business di modificare i dati del grafico in Excel, Aspose.Slides lo rende semplice. Questo tutorial ti guida nella creazione di un grafico, nell'aggiunta di una diapositiva a torta e nell'esportazione dei dati del grafico in una cartella di lavoro Excel.

**Cosa Imparerai:**
- Caricare e manipolare file di presentazione senza sforzo
- **Add pie chart slide** e altri tipi di grafico alle tue diapositive
- **Export chart to excel** (generare excel dal grafico) per analisi successive
- Impostare un percorso di cartella di lavoro esterna per **embed chart in presentation** e mantenere i dati sincronizzati

Iniziamo!

## Quick Answers
- **Qual è lo scopo principale?** Esportare i dati del grafico da una diapositiva PowerPoint a un file Excel.  
- **Quale versione della libreria è necessaria?** Aspose.Slides per Java 25.4 o successiva.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per la valutazione; è richiesta una licenza commerciale per la produzione.  
- **Posso aggiungere una diapositiva a torta?** Sì – il tutorial mostra come aggiungere un Pie chart.  
- **È Java 16 il minimo?** Sì, JDK 16 o superiore è consigliato.

## How to export chart to excel using Aspose.Slides?
Esportare i dati del grafico in Excel è semplice come caricare una presentazione, creare un grafico e poi scrivere lo stream della cartella di lavoro del grafico su un file. I passaggi seguenti ti guidano attraverso l’intero processo, dalla configurazione del progetto alla verifica finale.

## Prerequisites
Prima di iniziare, assicurati di avere a disposizione quanto segue:

### Required Libraries and Versions
- **Aspose.Slides per Java** versione 25.4 o successiva

### Environment Setup Requirements
- Java Development Kit (JDK) 16 o superiore
- Un editor di codice o IDE come IntelliJ IDEA o Eclipse

### Knowledge Prerequisites
- Conoscenze di base di programmazione Java
- Familiarità con i sistemi di build Maven o Gradle

## Setting Up Aspose.Slides for Java
Per iniziare a usare Aspose.Slides, includilo nel tuo progetto usando Maven o Gradle.

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

In alternativa, puoi [download the latest version directly](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
Aspose.Slides offre una licenza di prova gratuita per esplorare tutte le sue funzionalità. Puoi anche richiedere una licenza temporanea o acquistarne una per uso esteso. Segui questi passaggi:
1. Visita la [Aspose Purchase page](https://purchase.aspose.com/buy) per ottenere la tua licenza.  
2. Per una prova gratuita, scarica da [Releases](https://releases.aspose.com/slides/java/).  
3. Richiedi una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, inizializzalo nella tua applicazione Java:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

### Feature 1: Load Presentation
Caricare una presentazione è il primo passo per qualsiasi operazione di manipolazione.

#### Overview
Questa funzionalità dimostra come caricare un file PowerPoint esistente usando Aspose.Slides per Java.

#### Step‑by‑Step Implementation
**Load Presentation**
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
**Explanation:**  
- `Presentation` è inizializzato con il percorso del tuo file `.pptx`.  
- Disporre sempre dell'oggetto `Presentation` per liberare le risorse native.

### Feature 2: Add Pie Chart Slide
Aggiungere un grafico può migliorare notevolmente la presentazione dei dati, e molti sviluppatori chiedono **how to add chart slide** in Java.

#### Overview
Questa funzionalità mostra come aggiungere una **pie chart slide** (lo scenario classico “add pie chart slide”) alla prima diapositiva di una presentazione.

#### Step‑by‑Step Implementation
**Add Pie Chart**
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
**Explanation:**  
- `addChart` inserisce un grafico a torta.  
- I parametri definiscono il tipo di grafico e la sua posizione/dimensione sulla diapositiva.

### Feature 3: Generate Excel from Chart
Esportare i dati del grafico ti consente di **generate excel from chart** per un'analisi più approfondita.

#### Overview
Questa funzionalità dimostra come esportare i dati del grafico da una presentazione a una cartella di lavoro Excel esterna.

#### Step‑by‑Step Implementation
**Export Data**
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
**Explanation:**  
- `readWorkbookStream` estrae i dati della cartella di lavoro del grafico.  
- L'array di byte viene scritto in un file `.xlsx` usando `FileOutputStream`.

### Feature 4: Embed Chart in Presentation with External Workbook
Collegare un grafico a una cartella di lavoro esterna ti permette di **embed chart in presentation** e mantenere i dati sincronizzati.

#### Overview
Questa funzionalità dimostra come impostare un percorso di cartella di lavoro esterna affinché il grafico possa leggere/scrivere dati direttamente da Excel.

#### Step‑by‑Step Implementation
**Set External Workbook Path**
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
**Explanation:**  
- `setExternalWorkbook` collega il grafico a un file Excel, consentendo aggiornamenti dinamici senza ricostruire la diapositiva.

## Practical Applications
Aspose.Slides offre soluzioni versatili per vari scenari:

1. **Business Reports:** Crea report dettagliati con grafici direttamente da applicazioni Java.  
2. **Academic Presentations:** Arricchisci le lezioni con diapositive a torta interattive.  
3. **Financial Analysis:** **Export chart to excel** per modellazione finanziaria approfondita.  
4. **Marketing Analytics:** Visualizza le performance delle campagne e **generate excel from chart** per il team di analisi.

## Frequently Asked Questions

**Q: Posso usare questo approccio con altri tipi di grafico (es. Bar, Line)?**  
A: Assolutamente. Sostituisci `ChartType.Pie` con qualsiasi altro valore dell'enum `ChartType`.

**Q: È necessaria una libreria Excel separata per leggere il file esportato?**  
A: No. Il file `.xlsx` esportato è una cartella di lavoro Excel standard che può essere aperta con qualsiasi applicazione di fogli di calcolo.

**Q: Come influisce la cartella di lavoro esterna sulla dimensione della diapositiva?**  
A: Il collegamento a una cartella di lavoro esterna non aumenta significativamente la dimensione del file PPTX; il grafico fa riferimento al workbook a runtime.

**Q: È possibile aggiornare i dati di Excel e far riflettere le modifiche automaticamente nella diapositiva?**  
A: Sì. Dopo aver chiamato `setExternalWorkbook`, qualsiasi modifica salvata nella cartella di lavoro sarà riflessa al prossimo apertura della presentazione.

**Q: Cosa succede se devo esportare più grafici dalla stessa presentazione?**  
A: Itera sulla collezione di grafici di ciascuna diapositiva, chiama `readWorkbookStream()` per ognuno e scrivi su file di cartella di lavoro separati.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}