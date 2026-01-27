---
date: '2026-01-11'
description: Scopri come utilizzare Aspose Slides per Java, aggiungere marcatori immagine
  ai grafici e configurare la dipendenza Maven di Aspose Slides per visualizzazioni
  personalizzate dei grafici.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Come utilizzare Aspose Slides Java - aggiungere marcatori immagine ai grafici'
url: /it/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come utilizzare Aspose Slides Java: aggiungere marcatori immagine ai grafici

## Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per una comunicazione efficace, e i grafici sono uno strumento potente per trasmettere dati complessi in modo sintetico. Quando ti chiedi **come utilizzare Aspose** per far risaltare i tuoi grafici, i marcatori immagine personalizzati sono la risposta. I marcatori standard possono apparire generici, ma con Aspose.Slides per Java puoi sostituirli con qualsiasi immagine, rendendo ogni punto dati immediatamente riconoscibile.

In questo tutorial, ti guideremo attraverso l’intero processo di aggiunta di marcatori immagine a un grafico a linee, dalla configurazione della **dipendenza Maven di Aspose Slides** al caricamento delle immagini e alla loro applicazione ai punti dati. Alla fine sarai a tuo agio con **come aggiungere marcatori**, come **aggiungere immagini a una serie di grafico**, e avrai a disposizione un esempio di codice pronto all’uso.

**Cosa imparerai**
- Come configurare Aspose.Slides per Java (inclusi Maven/Gradle)
- Creare una presentazione di base e un grafico
- Aggiungere marcatori immagine ai punti dati del grafico
- Configurare dimensione e stile del marcatore per una visualizzazione ottimale

Pronto a migliorare i tuoi grafici? Iniziamo con i prerequisiti prima di cominciare!

### Risposte rapide
- **Qual è lo scopo principale?** Aggiungere marcatori immagine personalizzati ai punti dati del grafico.  
- **Quale libreria è necessaria?** Aspose.Slides per Java (Maven/Gradle).  
- **È necessaria una licenza?** Una licenza temporanea è sufficiente per la valutazione; una licenza completa è necessaria per la produzione.  
- **Quale versione di Java è supportata?** JDK 16 o successive.  
- **Posso usare qualsiasi formato immagine?** Sì—PNG, JPEG, BMP, ecc., purché il file sia accessibile.

### Prerequisiti
Per seguire questo tutorial, ti serviranno:
1. **Libreria Aspose.Slides per Java** – ottienila tramite Maven, Gradle o download diretto.  
2. **Ambiente di sviluppo Java** – JDK 16 o versioni successive installate.  
3. **Conoscenze di base di programmazione Java** – familiarità con la sintassi e i concetti di Java sarà utile.

## Cos’è la dipendenza Maven di Aspose Slides?
La dipendenza Maven scarica i binari corretti per la tua versione di Java. Aggiungerla al tuo `pom.xml` garantisce che la libreria sia disponibile sia in fase di compilazione che di esecuzione.

### Installazione Maven
Aggiungi la seguente dipendenza al tuo file `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installazione Gradle
Inserisci questa riga nel tuo file `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica l’ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Passaggi per l’acquisizione della licenza
- **Prova gratuita** – inizia con una licenza temporanea per esplorare le funzionalità.  
- **Licenza temporanea** – sblocca capacità avanzate durante i test.  
- **Acquisto** – ottieni una licenza completa per progetti commerciali.

## Inizializzazione di base e configurazione
Per prima cosa, crea un oggetto `Presentation`. Questo oggetto rappresenta l’intero file PowerPoint e conterrà il nostro grafico.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guida all’implementazione
Di seguito trovi una procedura passo‑passo per aggiungere marcatori immagine a un grafico. Ogni blocco di codice è accompagnato da una spiegazione così da capire **perché** ogni riga è importante.

### Passo 1: Creare una nuova presentazione con un grafico
Aggiungiamo un grafico a linee con marcatori predefiniti alla prima diapositiva.

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
Rimuoviamo eventuali serie predefinite e aggiungiamo le nostre, preparando il foglio di lavoro per i punti dati personalizzati.

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
Qui dimostriamo **come aggiungere marcatori** usando immagini. Sostituisci i percorsi segnaposto con la posizione reale delle tue immagini.

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
Regoliamo lo stile del marcatore per una migliore visibilità e scriviamo il file PPTX finale.

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

## Problemi comuni e risoluzione
- **FileNotFoundException** – Verifica che i percorsi delle immagini (`YOUR_DOCUMENT_DIRECTORY/...`) siano corretti e che i file esistano.  
- **LicenseException** – Assicurati di aver impostato una licenza Aspose valida prima di chiamare qualsiasi API in produzione.  
- **Marcatore non visibile** – Incrementa `setMarkerSize` o utilizza immagini a risoluzione più alta per una visualizzazione più chiara.

## Domande frequenti

**D: Posso usare immagini PNG invece di JPEG per i marcatori?**  
R: Sì, qualsiasi formato immagine supportato da Aspose.Slides (PNG, JPEG, BMP, GIF) funziona come marcatore.

**D: È necessaria una licenza per i pacchetti Maven/Gradle?**  
R: Una licenza temporanea è sufficiente per sviluppo e test; una licenza completa è richiesta per distribuzione commerciale.

**D: È possibile aggiungere immagini diverse a ciascun punto dati nella stessa serie?**  
R: Assolutamente. Nell’esempio `AddImageMarkers` alterniamo due immagini, ma puoi caricare un’immagine unica per ogni punto.

**D: Come influisce la `aspose slides maven dependency` sulla dimensione del progetto?**  
R: Il pacchetto Maven include solo i binari necessari per la versione JDK selezionata, mantenendo l’ingombro ragionevole. È possibile usare anche la versione **senza dipendenze** se lo spazio è un problema.

**D: Quali versioni di Java sono supportate?**  
R: Aspose.Slides per Java supporta JDK 8 fino a JDK 21. L’esempio utilizza JDK 16, ma puoi adeguare il classifier di conseguenza.

## Conclusione
Seguendo questa guida ora sai **come utilizzare Aspose** per arricchire i grafici con marcatori immagine personalizzati, come configurare la **dipendenza Maven di Aspose Slides**, e come **aggiungere immagini a una serie di grafico** per un aspetto professionale e curato. Sperimenta con icone, dimensioni e tipologie di grafico diverse per creare presentazioni che davvero si distinguono.

---

**Ultimo aggiornamento:** 2026-01-11  
**Testato con:** Aspose.Slides per Java 25.4 (jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}