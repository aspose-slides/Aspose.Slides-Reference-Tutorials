---
"date": "2025-04-17"
"description": "Scopri come migliorare i tuoi grafici in Aspose.Slides per Java aggiungendo marcatori di immagini personalizzati. Aumenta il coinvolgimento con presentazioni visivamente distinte."
"title": "Master Aspose.Slides Java&#58; Aggiunta di marcatori di immagini ai grafici"
"url": "/it/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare Aspose.Slides Java: aggiungere marcatori di immagini ai grafici

## Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per una comunicazione efficace, e i grafici sono uno strumento potente per trasmettere dati complessi in modo conciso. I marcatori standard dei grafici a volte possono non essere sufficienti a far risaltare i dati. Con Aspose.Slides per Java, puoi migliorare i tuoi grafici aggiungendo immagini personalizzate come marcatori, rendendoli più coinvolgenti e informativi.

In questo tutorial, esploreremo come integrare i marcatori di immagine nei grafici utilizzando la libreria Aspose.Slides in Java. Padroneggiando queste tecniche, sarai in grado di creare presentazioni che catturano l'attenzione con i loro elementi visivi unici.

**Cosa imparerai:**
- Come configurare Aspose.Slides per Java
- Creazione di una presentazione e di un grafico di base
- Aggiunta di marcatori di immagini ai punti dati del grafico
- Configurazione delle impostazioni del marcatore per una visualizzazione ottimale

Pronti a migliorare i vostri grafici? Analizziamo i prerequisiti prima di iniziare!

### Prerequisiti
Per seguire questo tutorial, avrai bisogno di:
1. **Libreria Aspose.Slides per Java**: Ottienilo tramite le dipendenze Maven o Gradle oppure scaricandolo direttamente da Aspose.
2. **Ambiente di sviluppo Java**: Assicurati che JDK 16 sia installato sul tuo computer.
3. **Conoscenza di base della programmazione Java**: Sarà utile avere familiarità con la sintassi e i concetti Java.

## Impostazione di Aspose.Slides per Java
Prima di immergerci nel codice, configuriamo il nostro ambiente di sviluppo con le librerie necessarie.

### Installazione Maven
Aggiungi la seguente dipendenza al tuo `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installazione di Gradle
Includi questo nel tuo `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
In alternativa, scarica l'ultima versione da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

#### Fasi di acquisizione della licenza
- **Prova gratuita**: Inizia con una licenza temporanea per esplorare le funzionalità di Aspose.Slides.
- **Licenza temporanea**:Accedi alle funzionalità avanzate ottenendo una licenza temporanea.
- **Acquistare**: Per un utilizzo a lungo termine, si consiglia di acquistare una licenza completa.

### Inizializzazione e configurazione di base
Inizializzare il `Presentation` oggetto per iniziare a creare diapositive:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Qui puoi inserire il codice per aggiungere diapositive e grafici.
    }
}
```

## Guida all'implementazione
Ora analizziamo il processo di aggiunta di marcatori di immagini alla serie di grafici.

### Crea una nuova presentazione con un grafico
Per prima cosa, abbiamo bisogno di una diapositiva in cui possiamo aggiungere il nostro grafico:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Inizializza l'oggetto Presentazione
        Presentation presentation = new Presentation();

        // Ottieni la prima diapositiva dalla raccolta
        ISlide slide = presentation.getSlides().get_Item(0);

        // Aggiungi un grafico a linee predefinito con marcatori alla diapositiva
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Accesso e configurazione dei dati del grafico
Successivamente, accederemo al foglio di lavoro dei dati del nostro grafico per gestire le serie:

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

        // Cancella le serie esistenti e aggiungine una nuova
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Aggiungere marcatori di immagine ai punti dati del grafico
Ora arriva la parte interessante: aggiungere immagini come marcatori:

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

        // Carica e aggiungi immagini come marcatori
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Aggiungere punti dati con immagini come marcatori
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

### Configura il marcatore della serie di grafici e salva la presentazione
Infine, regoliamo la dimensione del marcatore per una migliore visibilità e salviamo la nostra presentazione:

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

        // Carica e aggiungi immagini come marcatori (ad esempio utilizzando percorsi segnaposto)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Conclusione
Seguendo questa guida, hai imparato a migliorare i tuoi grafici in Aspose.Slides per Java aggiungendo marcatori di immagini personalizzati. Questo approccio può aumentare significativamente il coinvolgimento e la chiarezza delle tue presentazioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}