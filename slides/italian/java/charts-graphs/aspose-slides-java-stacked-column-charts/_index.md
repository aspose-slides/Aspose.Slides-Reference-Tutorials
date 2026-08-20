---
date: '2026-07-22'
description: Scopri la Dipendenza Maven di Aspose Slides per creare un grafico a colonne
  impilate in Java, aggiungere etichette dati, modificare il formato numerico dell'asse
  verticale e esportare il risultato in un file PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: La Dipendenza Maven di Aspose Slides ti consente di creare un grafico
  a colonne impilate in Java, personalizzare le etichette dati, regolare il formato
  dell'asse verticale e salvare come PPTX – il tutto con codice conciso e pronto per
  la produzione.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Dipendenza Maven di Aspose Slides: Grafico a colonne impilate in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Dipendenza Maven di Aspose Slides: Grafico a colonne impilate in Java'
url: /it/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dipendenza Maven di Aspose Slides: Grafico a colonne impilate in Java

## Introduzione

Eleva le tue presentazioni incorporando visualizzazioni dati approfondite con la potenza di **Aspose.Slides for Java**. In questa guida **creerai un grafico a colonne impilate** dall'aspetto professionale, sia che tu stia preparando report aziendali sia che tu stia mostrando statistiche di progetto. Alla fine di questo tutorial sarai in grado di:

- Configurare l'ambiente con la **dipendenza Maven di Aspose Slides**
- Creare una presentazione da zero
- **Aggiungere un grafico a colonne percentuale‑impilato** e personalizzarne l'aspetto
- **Formattare le etichette dei dati del grafico** e **modificare il formato numerico dell'asse verticale**
- **Salvare la presentazione come PPTX** con una singola riga di codice

## Risposte rapide
- **Quale libreria è necessaria?** Aggiungi la dipendenza Maven/Gradle `aspose-slides` (vedi “Dipendenza Maven di Aspose Slides” di seguito).  
- **Quale tipo di grafico crea una visualizzazione impilata?** Usa `ChartType.PercentsStackedColumn` per un grafico a colonne percentuale‑impilato.  
- **Come posso modificare il formato numerico dell'asse?** Chiama `IAxis.setNumberFormat()` e imposta `setNumberFormatLinkedToSource(false)`.  
- **Posso personalizzare le etichette dei dati?** Sì – itera su ogni `IChartDataPoint` e assegna un `ITextFrame` personalizzato.  
- **Come salvo il file?** Invoca `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Cos'è un grafico a colonne impilate?
Un grafico a colonne impilate visualizza più serie di dati impilate verticalmente in ogni colonna di categoria, con la variante **percentuale‑impilata** che normalizza ogni colonna al 100 % per un facile confronto delle proporzioni. Questo formato consente agli spettatori di valutare rapidamente come ogni componente contribuisce al totale tra le diverse categorie, rendendo le tendenze e le dimensioni relative immediatamente chiare.

## Perché usare Aspose.Slides per Java?
Aspose.Slides per Java ti consente di generare, modificare e convertire file PowerPoint **senza necessità di Microsoft Office** e supporta **oltre 50 formati di output** su Windows, Linux e macOS. La libreria gira interamente su una JRE, consentendo automazione lato server e report ad alto rendimento. Fornisce inoltre un controllo dettagliato su oggetti grafico, layout delle diapositive e proprietà del documento, rendendola ideale per la generazione di presentazioni a livello aziendale.

## Prerequisiti
- **Java Development Kit (JDK):** 8 o superiore  
- **IDE:** IntelliJ IDEA, Eclipse o qualsiasi editor compatibile con Java  
- **Strumento di build:** Maven o Gradle (opzionale ma consigliato)  
- **Conoscenza di base di Java** – dovresti sentirti a tuo agio con classi e metodi  

## Configurazione di Aspose.Slides per Java
Per iniziare, aggiungi la libreria Aspose.Slides al tuo progetto.

### Dipendenza Maven di Aspose Slides
Aggiungi quanto segue al tuo `pom.xml` (questa è la **dipendenza Maven di Aspose Slides** di cui avrai bisogno):

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
In alternativa, scarica l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per rimuovere le limitazioni di valutazione, considera di ottenere una licenza temporanea o acquistata.

- **Prova gratuita:** Accesso a funzionalità limitate senza costi immediati.  
- **Licenza temporanea:** Richiedi tramite [sito di Aspose](https://purchase.aspose.com/temporary-license/).  
- **Acquisto:** Visita la pagina di acquisto per accesso completo.

### Inizializzazione di base
`Presentation` è la classe core di Aspose.Slides che rappresenta un file PowerPoint in memoria. Il seguente snippet minimale mostra come creare un oggetto `Presentation`:

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
Per prima cosa, creeremo una presentazione vuota e verificheremo che esista una diapositiva.

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

### Aggiunta di un grafico a colonne percentuale‑impilato a una diapositiva
**Panoramica:**  
Ora inseriremo un **grafico a colonne percentuale‑impilato** nella prima diapositiva.

`ChartType.PercentsStackedColumn` specifica un tipo di grafico a colonne percentuale‑impilato.

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
Per una migliore leggibilità, **modificheremo il formato dell'asse verticale** per mostrare le percentuali.

`IAxis` è l'interfaccia che rappresenta un asse del grafico, consentendo regolazioni di formato e scala.

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

#### Passo 2: Aggiungere serie di dati
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

`IChartDataPoint` rappresenta un singolo punto dati all'interno di una serie di grafico, e `ITextFrame` contiene il testo dell'etichetta.

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

**Q: Posso usare questo codice con Java 11 o versioni successive?**  
A: Sì. La libreria supporta JDK 8+; basta usare il classificatore appropriato (ad es., `jdk16` per JDK 16 o versioni successive).

**Q: Come esportare il grafico come immagine invece di un PPTX?**  
A: Usa `chart.getImage().save("chart.png", ImageFormat.Png);` dopo aver aggiunto il grafico alla diapositiva.

**Q: È possibile aggiungere una legenda al grafico a colonne impilate?**  
A: Assolutamente. Chiama `chart.getChartTitle().addTextFrameForOverriding("My Chart");` e configura `chart.getLegend()` secondo necessità.

**Q: Cosa succede se devo aggiornare i dati dopo che la presentazione è stata generata?**  
A: Puoi modificare le celle di `ChartDataWorkbook` e poi chiamare `chart.refresh();` per riflettere le modifiche.

**Q: Aspose.Slides funziona su server Linux?**  
A: Sì. La libreria è puramente Java e gira su qualsiasi OS con una JRE compatibile.

## Conclusione
Seguendo questa guida hai imparato a **creare un grafico a colonne impilate** in Java usando la **dipendenza Maven di Aspose Slides**, dalla configurazione dell'ambiente alla stilizzazione visiva fine. Sperimenta con diversi set di dati, colori e formati delle etichette per far risaltare davvero i tuoi report.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come creare un grafico a colonne raggruppate in Java con Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Come impostare i formati numerici nei punti dati del grafico usando Aspose.Slides per Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Come aggiungere e configurare grafici nelle presentazioni usando Aspose.Slides per Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}