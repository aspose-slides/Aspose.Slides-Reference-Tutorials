---
date: '2026-02-22'
description: Scopri come creare un grafico a colonne impilate in Java usando Aspose.Slides.
  Questo tutorial copre la dipendenza Maven di Aspose Slides, l'aggiunta di un grafico
  a colonne impilate percentuali, la formattazione delle etichette dei dati del grafico
  e il salvataggio della presentazione in formato PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Come creare un grafico a colonne impilate in Java con Aspose.Slides – Guida
  completa
url: /it/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a colonne impilate in Java con Aspose.Slides – Guida completa

## Introduzione

Eleva le tue presentazioni incorporando visualizzazioni di dati approfondite grazie alla potenza di Aspose.Slides per Java. In questa guida **creerai grafici a colonne impilate** che appariranno professionali, sia che tu stia preparando report aziendali sia che tu voglia mostrare statistiche di progetto. Alla fine di questo tutorial sarai in grado di:

- Configurare l'ambiente con la dipendenza Maven di Aspose Slides
- Creare una presentazione da zero
- **Aggiungere un grafico a colonne impilate percentuali** e personalizzarne l'aspetto
- **Formattare le etichette dei dati del grafico** e **modificare il formato dell'asse verticale**
- **Salvare la presentazione come PPTX** con una singola riga di codice

Segui passo passo le istruzioni per iniziare subito a costruire presentazioni accattivanti.

## Risposte rapide
- **Quale libreria è necessaria?** dipendenza Maven/Gradle `aspose-slides` (vedi “aspose slides maven dependency” sotto)  
- **Quale tipo di grafico viene usato?** `ChartType.PercentsStackedColumn` per un grafico a colonne impilate percentuali  
- **Come modifico il formato numerico dell'asse?** Usa `IAxis.setNumberFormat()` e disabilita il collegamento alla sorgente  
- **Posso personalizzare le etichette dei dati?** Sì – itera sugli oggetti `IChartDataPoint` e imposta un `ITextFrame` personalizzato  
- **Come salvo il file?** Chiama `presentation.save("output.pptx", SaveFormat.Pptx)`

## Che cos'è un grafico a colonne impilate?
Un grafico a colonne impilate visualizza più serie di dati sovrapposte una sull'altra in colonne verticali. Quando utilizzi la variante **impilata percentuale**, ogni colonna totalizza sempre il 100 %, facilitando il confronto delle contribuzioni proporzionali tra le categorie.

## Perché usare Aspose.Slides per Java?
Aspose.Slides offre un'API pure‑Java che funziona su qualsiasi piattaforma senza la necessità di Microsoft Office installato. Fornisce un controllo dettagliato sugli oggetti grafico, supporta un'ampia gamma di formati e consente di generare presentazioni in modo programmatico—perfetto per report automatizzati o generazione di documenti lato server.

## Prerequisiti
- **Java Development Kit (JDK):** 8 o superiore  
- **IDE:** IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java  
- **Strumento di build:** Maven o Gradle (opzionale ma consigliato)  
- **Conoscenza di base di Java** – dovresti sentirti a tuo agio con classi e metodi  

## Configurazione di Aspose.Slides per Java
Per iniziare, aggiungi la libreria Aspose.Slides al tuo progetto.

### Dipendenza Maven di Aspose Slides
Aggiungi quanto segue al tuo `pom.xml` (questa è la **aspose slides maven dependency** di cui hai bisogno):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternativa Gradle
Se preferisci Gradle, includi questa riga in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica l'ultimo JAR da [Aspose.Slides per Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per rimuovere le limitazioni di valutazione, considera l'ottenimento di una licenza temporanea o acquistata.

- **Prova gratuita:** Accesso a funzionalità limitate senza costi immediati.  
- **Licenza temporanea:** Richiedi tramite [sito di Aspose](https://purchase.aspose.com/temporary-license/).  
- **Acquisto:** Visita la pagina di acquisto per l'accesso completo.

### Inizializzazione di base
Ecco un frammento minimo che mostra come creare un oggetto `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guida all'implementazione

### Creazione di una presentazione e aggiunta di una diapositiva
**Panoramica:**  
Innanzitutto, creeremo una presentazione vuota e verificheremo che esista una diapositiva.

#### Passo 1: Inizializzare l'oggetto Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Passo 2: Salvare la presentazione
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Aggiunta di un grafico a colonne impilate percentuali a una diapositiva
**Panoramica:**  
Ora inseriremo un **grafico a colonne impilate percentuali** nella prima diapositiva.

#### Passo 1: Inizializzare e accedere alla diapositiva
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Passo 2: Aggiungere il grafico alla diapositiva
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizzazione del formato numerico dell'asse del grafico
**Panoramica:**  
Per una migliore leggibilità **modificheremo il formato dell'asse verticale** per mostrare le percentuali.

#### Passo 1: Aggiungere e accedere al grafico
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Passo 2: Impostare il formato numerico personalizzato
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Aggiunta di serie e punti dati al grafico
**Panoramica:**  
Popoleremo il grafico con serie di dati di esempio.

#### Passo 1: Inizializzare la presentazione e il grafico
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Passo 2: Aggiungere le serie di dati
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formattazione del colore di riempimento delle serie
**Panoramica:**  
Assegna a ogni serie un colore distinto per rendere il grafico più leggibile.

#### Passo 1: Inizializzare e accedere al grafico
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Passo 2: Impostare i colori di riempimento
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formattazione delle etichette dei dati
**Panoramica:**  
Ora **formatteremo le etichette dei dati del grafico** in modo che mostrino testo personalizzato.

#### Passo 1: Accedere alle serie del grafico e ai punti dati
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Passo 2: Personalizzare le etichette dei dati
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Problemi comuni e soluzioni
- **Il grafico appare vuoto:** Assicurati di aver aggiunto almeno una serie di dati e un punto dati prima di salvare.  
- **I numeri dell'asse non mostrano le percentuali:** Ricorda di impostare `verticalAxis.setNumberFormatLinkedToSource(false)`; altrimenti il formato personalizzato viene ignorato.  
- **Messaggio di valutazione della licenza:** Applica un file di licenza valido prima di creare l'oggetto `Presentation` per sopprimere il banner di valutazione.

## Domande frequenti

**D: Posso usare questo codice con Java 11 o versioni successive?**  
R: Sì. La libreria supporta JDK 8+; basta utilizzare il classificatore appropriato (ad es., `jdk16` per JDK 16 o versioni successive).

**D: Come esportare il grafico come immagine anziché come PPTX?**  
R: Usa `chart.getImage().save("chart.png", ImageFormat.Png);` dopo aver aggiunto il grafico alla diapositiva.

**D: È possibile aggiungere una legenda al grafico a colonne impilate?**  
R: Assolutamente. Chiama `chart.getChartTitle().addTextFrameForOverriding("My Chart");` e configura `chart.getLegend()` secondo necessità.

**D: Cosa succede se devo aggiornare i dati dopo aver generato la presentazione?**  
R: Puoi modificare le celle del `ChartDataWorkbook` e poi chiamare `chart.refresh();` per riflettere le modifiche.

**D: Aspose.Slides funziona su server Linux?**  
R: Sì. La libreria è pure Java e gira su qualsiasi OS con una JRE compatibile.

## Conclusione
Seguendo questa guida hai imparato a **creare presentazioni con grafici a colonne impilate** usando Aspose.Slides per Java, dalla configurazione dell'ambiente alla personalizzazione visiva avanzata. Sperimenta con diversi set di dati, colori e formati delle etichette per far risaltare davvero i tuoi report.

---

**Ultimo aggiornamento:** 2026-02-22  
**Testato con:** Aspose.Slides 25.4 (classificatore jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}