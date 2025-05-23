---
"date": "2025-04-17"
"description": "Impara a creare presentazioni professionali utilizzando Aspose.Slides per Java. Questa guida illustra la configurazione dell'ambiente, l'aggiunta di grafici a colonne impilate e la loro personalizzazione per una maggiore chiarezza."
"title": "Padroneggia i grafici a colonne impilate in Java con Aspose.Slides&#58; una guida completa"
"url": "/it/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggia i grafici a colonne impilate in Java con Aspose.Slides: una guida completa

## Introduzione

Migliora le tue presentazioni integrando visualizzazioni di dati approfondite con la potenza di Aspose.Slides per Java. Creare diapositive dall'aspetto professionale con grafici a colonne sovrapposte è semplice, sia che tu stia preparando report aziendali o presentando statistiche di progetto.

In questo tutorial, esploreremo come utilizzare Aspose.Slides per Java per creare presentazioni dinamiche e aggiungere grafici a colonne impilate visivamente accattivanti. Al termine di questa guida, avrai le competenze necessarie per:
- Imposta il tuo ambiente per utilizzare Aspose.Slides
- Crea una presentazione da zero
- Aggiungere e personalizzare grafici a colonne con percentuali sovrapposte
- Formattare gli assi del grafico e le etichette dei dati per maggiore chiarezza

Impariamo a creare presentazioni che catturino l'attenzione del pubblico.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- **Kit di sviluppo Java (JDK):** Versione 8 o superiore.
- **IDE:** Qualsiasi ambiente di sviluppo integrato come IntelliJ IDEA o Eclipse.
- **Maven/Gradle:** Per gestire le dipendenze (facoltativo ma consigliato).
- **Conoscenza di base di Java:** Familiarità con i concetti di programmazione Java.

## Impostazione di Aspose.Slides per Java
Per iniziare, devi includere la libreria Aspose.Slides nel tuo progetto. Ecco come fare:

**Esperto:**
Aggiungi questa dipendenza al tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Includi questo nel tuo `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download diretto:**
In alternativa, scaricare l'ultimo JAR da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per rimuovere le limitazioni della versione di valutazione, valuta la possibilità di acquistare una licenza temporanea o a pagamento.
- **Prova gratuita:** Accedi a funzionalità limitate senza costi immediati.
- **Licenza temporanea:** Richiedi tramite [Il sito di Aspose](https://purchase.aspose.com/temporary-license/).
- **Acquistare:** Per l'accesso completo, visita la pagina di acquisto.

### Inizializzazione di base
Ecco come inizializzare Aspose.Slides nella tua applicazione Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Crea un'istanza della classe Presentazione
        Presentation presentation = new Presentation();
        
        // Eseguire operazioni sull'oggetto di presentazione
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guida all'implementazione

### Creazione di una presentazione e aggiunta di una diapositiva
**Panoramica:**
Inizia creando una presentazione semplice con una diapositiva iniziale. Questa sarà la base per ulteriori miglioramenti.

#### Passaggio 1: inizializzare l'oggetto di presentazione
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Crea una nuova istanza di presentazione
        Presentation presentation = new Presentation();
        
        // Riferimento alla prima diapositiva (creata automaticamente)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Passaggio 2: salva la presentazione
```java
// Salva la presentazione in un file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Aggiungere un grafico a colonne in pila percentuale a una diapositiva
**Panoramica:**
Arricchisci la tua diapositiva aggiungendo un grafico a colonne con percentuali in pila, che consente un facile confronto dei dati.

#### Passaggio 1: inizializzare e accedere alla diapositiva
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Procedi ad aggiungere il grafico nel passaggio successivo
    }
}
```

#### Passaggio 2: aggiungere il grafico alla diapositiva
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalizzazione del formato dei numeri degli assi del grafico
**Panoramica:**
Personalizza il formato numerico dell'asse verticale del grafico per migliorarne la leggibilità.

#### Passaggio 1: aggiungere e accedere al grafico
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

#### Passaggio 2: imposta il formato numerico personalizzato
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Aggiunta di serie e punti dati al grafico
**Panoramica:**
Inserisci nel grafico serie di dati, rendendolo informativo e visivamente accattivante.

#### Passaggio 1: inizializzare la presentazione e il grafico
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

#### Passaggio 2: aggiungere serie di dati
```java
// Cancella le serie esistenti e aggiungine di nuove
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Aggiungere altri punti dati secondo necessità
```

### Colore di riempimento della serie di formattazione
**Panoramica:**
Migliora l'estetica del tuo grafico formattando il colore di riempimento di ogni serie.

#### Passaggio 1: inizializzare e accedere al grafico
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

#### Passaggio 2: imposta i colori di riempimento
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ripetere per altre serie con colori diversi
```

### Formattazione delle etichette dati
**Panoramica:**
Rendi più leggibili le etichette dei tuoi dati personalizzandone il formato.

#### Passaggio 1: accedere alle serie di grafici e ai punti dati
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

#### Passaggio 2: personalizzare le etichette dati
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

## Conclusione
Seguendo questa guida, hai imparato a configurare Aspose.Slides per Java e a creare presentazioni dinamiche con istogrammi a colonne con percentuali sovrapposte. Personalizza ulteriormente i tuoi grafici regolando colori ed etichette in base alle tue esigenze.

Buona programmazione!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}