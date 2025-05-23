---
"date": "2025-04-17"
"description": "Scopri come usare Aspose.Slides per Java per creare grafici ad anello dinamici in PowerPoint. Migliora le tue presentazioni con passaggi semplici ed esempi di codice."
"title": "Crea grafici ad anello dinamici in PowerPoint utilizzando Aspose.Slides per Java"
"url": "/it/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea grafici ad anello dinamici in PowerPoint utilizzando Aspose.Slides per Java

## Introduzione
Creare presentazioni accattivanti spesso richiede più di testo e immagini; i grafici possono migliorare significativamente la narrazione visualizzando i dati in modo efficace. Tuttavia, molti sviluppatori faticano a integrare le funzionalità dei grafici dinamici nei file di PowerPoint a livello di codice. Questo tutorial illustra come utilizzare Aspose.Slides per Java per creare un grafico ad anello in PowerPoint, un potente strumento che unisce flessibilità e facilità d'uso.

**Cosa imparerai:**
- Come inizializzare una presentazione utilizzando Aspose.Slides per Java
- Una guida passo passo per aggiungere un grafico a ciambella alle diapositive
- Configurazione dei punti dati e personalizzazione delle proprietà delle etichette
- Salvataggio della presentazione modificata con alta fedeltà

Scopriamo come sfruttare queste funzionalità per migliorare le tue presentazioni. Prima di iniziare, assicurati di avere familiarità con i concetti base della programmazione Java.

## Prerequisiti
Per seguire questo tutorial in modo efficace, assicurati di avere:
- Conoscenza di base della programmazione Java.
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse.
- Maven o Gradle installati per la gestione delle dipendenze.
- Una licenza valida per Aspose.Slides per Java. Puoi ottenere una prova gratuita per testarne le funzionalità.

## Impostazione di Aspose.Slides per Java
Inizia integrando Aspose.Slides nel tuo progetto. Scegli tra Maven e Gradle, a seconda delle tue preferenze:

**Esperto**
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

Se preferisci scaricare direttamente, visita il sito [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/) pagina.

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per un utilizzo prolungato, acquista una licenza o richiedine una temporanea da [Il sito web di Aspose](https://purchase.aspose.com/temporary-license/)Segui le istruzioni fornite per configurare il tuo ambiente e inizializzare Aspose.Slides nella tua applicazione.

## Guida all'implementazione
Analizziamo i passaggi necessari per creare un grafico a ciambella in PowerPoint utilizzando Aspose.Slides per Java. Ogni sezione è dedicata a una funzionalità specifica, garantendo chiarezza e concentrazione.

### Inizializza la presentazione
Inizia caricando o creando un nuovo file PowerPoint. Questo passaggio configura l'ambiente di presentazione.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verificare il caricamento riuscito salvando la presentazione iniziale
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Aggiungi grafico ad anello
Aggiungi un grafico a ciambella alla tua diapositiva, personalizzandone le dimensioni e l'aspetto.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configurare le proprietà della serie
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Configurare punti dati ed etichette
Personalizza l'aspetto di ogni punto dati e configura le etichette per una migliore leggibilità.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Formattare il punto dati
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Personalizza le proprietà dell'etichetta per l'ultima serie in ogni categoria
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Salva la presentazione
Dopo aver configurato il grafico, salva la presentazione per conservare le modifiche.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Applicazioni pratiche
I grafici ad anello possono essere utilizzati in vari scenari:
- **Relazioni finanziarie:** Visualizza le allocazioni di budget o le metriche finanziarie.
- **Analisi di mercato:** Mostra la distribuzione della quota di mercato tra i concorrenti.
- **Risultati del sondaggio:** Presentare in modo efficace i dati categoriali ricavati dalle risposte al sondaggio.

L'integrazione con altri sistemi, come database e applicazioni web, consente la generazione di grafici dinamici basati su dati in tempo reale.

## Considerazioni sulle prestazioni
Per prestazioni ottimali:
- Gestire l'utilizzo della memoria eliminando tempestivamente le risorse.
- Limitare il numero di grafici o diapositive se non necessario per risparmiare potenza di elaborazione.
- Utilizzare strutture dati efficienti per gestire set di dati di grandi dimensioni.

Il rispetto delle best practice garantisce il corretto funzionamento dell'applicazione, soprattutto quando si tratta di presentazioni complesse.

## Conclusione
Creare grafici ad anello dinamici in PowerPoint utilizzando Aspose.Slides per Java è un processo semplice, una volta compresi i passaggi chiave. Con questa guida, sarai pronto a migliorare le tue presentazioni integrando grafici visivamente accattivanti che comunicano efficacemente informazioni sui dati.

Per esplorare ulteriormente le funzionalità di Aspose.Slides e conoscerne più a fondo le potenzialità, puoi provare a sperimentare diversi tipi di grafici o funzionalità avanzate come animazioni e transizioni.

## Sezione FAQ
**D: Posso utilizzare Aspose.Slides per Java in applicazioni commerciali?**
R: Sì, ma è necessario acquistare una licenza. Puoi iniziare con una prova gratuita per valutarne le funzionalità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}