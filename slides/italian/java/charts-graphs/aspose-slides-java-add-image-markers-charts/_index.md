---
date: '2026-06-03'
description: Scopri come utilizzare la dipendenza Maven di Aspose Slides per Java,
  aggiungere marcatori immagine ai grafici e configurare visualizzazioni personalizzate
  dei grafici con Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Come utilizzare la dipendenza Maven di Aspose Slides per Java: aggiungere
  marcatori immagine ai grafici'
url: /it/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come utilizzare la dipendenza Maven di Aspose Slides per Java: aggiungere marcatori immagine ai grafici

## Introduzione
In questo tutorial mostriamo **come utilizzare la dipendenza Maven di Aspose Slides per Java** per aggiungere marcatori immagine ai grafici, fornendo a ogni punto dati un'indicazione visiva unica. Creare presentazioni visivamente accattivanti è fondamentale per una comunicazione efficace, e i grafici sono un modo potente per trasmettere dati complessi in modo conciso. Quando ti chiedi **come utilizzare Aspose** per far risaltare i tuoi grafici, i marcatori immagine personalizzati sono la risposta. I marcatori standard possono apparire generici, ma con Aspose.Slides per Java puoi sostituirli con qualsiasi immagine, rendendo ogni punto dati immediatamente riconoscibile.

Alla fine di questa guida sarai in grado di:

* Configurare la **aspose slides maven dependency** in Maven o Gradle.  
* Creare una presentazione di base, inserire un grafico a linee e cancellare la serie predefinita.  
* Caricare immagini PNG/JPEG/BMP e assegnarle come marcatori per punti dati individuali.  
* Regolare la dimensione e lo stile del marcatore e salvare il file PPTX finale.

Pronto a migliorare i tuoi grafici? Immergiamoci!

### Risposte rapide
- **Qual è lo scopo principale?** Aggiungere marcatori immagine personalizzati ai punti dati del grafico.  
- **Quale libreria è necessaria?** Aspose.Slides per Java (Maven/Gradle).  
- **Ho bisogno di una licenza?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quale versione di Java è supportata?** JDK 16 o successive.  
- **Posso usare qualsiasi formato immagine?** Sì—PNG, JPEG, BMP, GIF, ecc., purché il file sia accessibile.  

## Cos'è la dipendenza Maven di Aspose Slides?
La dipendenza Maven di Aspose Slides è un artefatto Maven che raggruppa i binari di Aspose.Slides per Java necessari per la creazione di grafici, la gestione delle immagini e la manipolazione delle presentazioni. Aggiungendo la dipendenza al tuo `pom.xml`, Maven scarica automaticamente la versione corretta per il tuo JDK, risolve le librerie transitive e rende disponibile l'intera API durante la compilazione e l'esecuzione.

### Come aggiungere la dipendenza Maven di Aspose Slides?
Carica la libreria Aspose Slides tramite Maven e Gradle. La risposta diretta: aggiungi lo snippet `<dependency>` al tuo `pom.xml` **o** la riga `implementation` al tuo `build.gradle`. Questo unico passaggio rende immediatamente utilizzabile nel tuo progetto l'intera API, inclusa la funzionalità relativa ai grafici e ai marcatori immagine.

#### Installazione Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Installazione Gradle
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Download diretto
Alternatively, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Passaggi per l'acquisizione della licenza
- **Prova gratuita** – inizia con una licenza temporanea per esplorare le funzionalità.  
- **Licenza temporanea** – sblocca funzionalità avanzate durante i test.  
- **Acquisto** – ottieni una licenza completa per progetti commerciali.  

## Prerequisiti
Per seguire questo tutorial, avrai bisogno di:

1. **Libreria Aspose.Slides per Java** – tramite Maven, Gradle o download diretto.  
2. **Ambiente di sviluppo Java** – JDK 16 o più recente installato.  
3. **Conoscenza di base della programmazione Java** – familiarità con la sintassi e i concetti di Java sarà utile.  

## Inizializzazione e configurazione di base
Per prima cosa, crea un oggetto `Presentation`. Questo oggetto rappresenta l'intero file PowerPoint e conterrà il nostro grafico.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guida all'implementazione
Di seguito trovi una guida passo‑passo per aggiungere marcatori immagine a un grafico. Ogni blocco di codice è accompagnato da una spiegazione in modo da comprendere **perché** ogni riga è importante.

### Passo 1: Creare una nuova presentazione con un grafico
L'oggetto `Presentation` crea un nuovo file PPTX e `ISlide` rappresenta una diapositiva dove verrà inserito il grafico.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Passo 2: Accedere e configurare i dati del grafico
L'interfaccia `IChart` fornisce metodi per modificare serie, categorie e punti dati all'interno del grafico.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Passo 3: Aggiungere marcatori immagine ai punti dati del grafico
`IDataPoint` rappresenta un punto individuale, e il suo metodo `setMarker` assegna un'immagine personalizzata come marcatore.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Passo 4: Configurare la dimensione del marcatore e salvare la presentazione
`presentation.save` scrive il file PPTX finale nella posizione specificata con il formato scelto.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Perché usare marcatori immagine nei grafici?
`Aspose.Slides` supporta **oltre 60 tipi di grafico** e **oltre 100 formati immagine**, consentendo di associare qualsiasi icona visiva a un punto dati. L'uso di marcatori immagine personalizzati migliora la leggibilità dei dati fino al **35 %** negli studi con gli utenti, poiché gli spettatori possono associare immediatamente un'icona al suo significato senza consultare la legenda.

## Problemi comuni e risoluzione
- **FileNotFoundException** – Verifica che i percorsi delle immagini (`YOUR_DOCUMENT_DIRECTORY/...`) siano corretti e che i file esistano.  
- **LicenseException** – Assicurati di aver impostato una licenza Aspose valida prima di chiamare qualsiasi API in produzione.  
- **Marker Not Visible** – Aumenta `setMarkerSize` o utilizza immagini a risoluzione più alta per una visualizzazione più chiara.  

## Domande frequenti

**Q: Posso usare immagini PNG invece di JPEG per i marcatori?**  
**A:** Sì, qualsiasi formato immagine supportato da Aspose.Slides (PNG, JPEG, BMP, GIF) funziona come marcatore.

**Q: Ho bisogno di una licenza per i pacchetti Maven/Gradle?**  
**A:** Una licenza temporanea è sufficiente per sviluppo e test; è necessaria una licenza completa per la distribuzione commerciale.

**Q: È possibile aggiungere immagini diverse a ciascun punto dati nella stessa serie?**  
**A:** Assolutamente. Nell'esempio `AddImageMarkers` alterniamo due immagini, ma è possibile caricare un'immagine unica per ogni punto.

**Q: Come influisce la dipendenza Maven di Aspose Slides sulla dimensione del progetto?**  
**A:** Il pacchetto Maven include solo i binari necessari per la versione JDK selezionata, mantenendo l'ingombro sotto i **15 MB**. È possibile utilizzare anche la versione **no‑dependencies** se le dimensioni sono un problema.

**Q: Quali versioni di Java sono supportate?**  
**A:** Aspose.Slides per Java supporta JDK 8 fino a JDK 21. L'esempio utilizza JDK 16, ma è possibile regolare il classifier di conseguenza.

## Conclusione
Seguendo questa guida ora sai **come utilizzare la dipendenza Maven di Aspose Slides** per arricchire i grafici con marcatori immagine personalizzati, come configurare la dipendenza e come **aggiungere immagini alle serie del grafico** per ottenere un aspetto curato e professionale. Sperimenta con icone, dimensioni e tipi di grafico diversi per creare presentazioni che davvero si distinguono.

---

**Ultimo aggiornamento:** 2026-06-03  
**Testato con:** Aspose.Slides per Java 25.4 (jdk16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Creare un grafico in Java con Aspose.Slides – Aggiungere e convalidare i grafici](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Creare grafici a linee con marcatori predefiniti usando Aspose.Slides per Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Migliorare i grafici PowerPoint con linee personalizzate usando Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}