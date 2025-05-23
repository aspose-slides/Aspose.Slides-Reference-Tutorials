---
"date": "2025-04-17"
"description": "Scopri come creare grafici a dispersione dinamici utilizzando Aspose.Slides per Java. Migliora le tue presentazioni con funzionalità personalizzabili."
"title": "Crea e personalizza grafici a dispersione in Java con Aspose.Slides"
"url": "/it/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e personalizza grafici a dispersione in Java con Aspose.Slides

Migliora le tue presentazioni aggiungendo grafici a dispersione dinamici utilizzando Java con Aspose.Slides. Questo tutorial completo ti guiderà nella configurazione delle directory, nell'inizializzazione delle presentazioni, nella creazione di grafici a dispersione, nella gestione dei dati dei grafici, nella personalizzazione di tipi di serie e marcatori e nel salvataggio del tuo lavoro, il tutto con semplicità.

**Cosa imparerai:**
- Impostazione di una directory per l'archiviazione dei file di presentazione
- Inizializzazione e manipolazione di presentazioni utilizzando Aspose.Slides
- Creazione di grafici a dispersione nelle diapositive
- Gestione e aggiunta di dati alle serie di grafici
- Personalizzazione dei tipi di serie di grafici e dei marcatori
- Salvataggio della presentazione con modifiche

Cominciamo col verificare che tu abbia i prerequisiti necessari.

## Prerequisiti

Per seguire questo tutorial, assicurati di avere:
- **Aspose.Slides per Java**: È richiesta la versione 25.4 o successiva.
- **Kit di sviluppo Java (JDK)**: È necessario JDK 8 o versione successiva.
- Conoscenza di base della programmazione Java e familiarità con gli strumenti di compilazione Maven o Gradle.

## Impostazione di Aspose.Slides per Java

Prima di iniziare a scrivere il codice, integra Aspose.Slides nel tuo progetto utilizzando uno dei seguenti metodi:

### Esperto
Includi questa dipendenza nel tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Aggiungi questa riga al tuo `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, scarica l'ultima versione di Aspose.Slides per Java da [Rilasci di Aspose](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
- **Prova gratuita**: Inizia con una prova gratuita di 30 giorni per esplorare le funzionalità.
- **Licenza temporanea**: Ottieni una licenza temporanea per test più lunghi.
- **Acquistare**: Acquista una licenza per ottenere accesso e supporto completi.

Ora inizializza Aspose.Slides nella tua applicazione Java aggiungendo le importazioni necessarie come mostrato di seguito.

## Guida all'implementazione

### Impostazione della directory
Innanzitutto, assicurati che la nostra directory esista per archiviare i file di presentazione. Questo passaggio evita errori durante il salvataggio dei file.

#### Crea la directory se non esiste
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Crea la directory
    new File(dataDir).mkdirs();
}
```
Questo frammento controlla una directory specificata e la crea se non esiste. Utilizza `File.exists()` per verificare la presenza e `File.mkdirs()` per creare directory.

### Inizializzazione della presentazione

Successivamente, inizializza l'oggetto presentazione in cui aggiungerai il grafico a dispersione.

#### Inizializza la tua presentazione
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Qui, `new Presentation()` Crea una presentazione vuota. Accediamo direttamente alla prima diapositiva per lavorarci.

### Creazione di grafici
Il passo successivo è creare un grafico a dispersione sulla nostra diapositiva inizializzata.

#### Aggiungi grafico a dispersione alla diapositiva
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Questo frammento di codice aggiunge un grafico a dispersione con linee morbide alla prima diapositiva. I parametri definiscono la posizione e le dimensioni del grafico.

### Gestione dei dati del grafico
Ora gestiamo i dati del nostro grafico cancellando tutte le serie esistenti e aggiungendone di nuove.

#### Gestisci serie di grafici
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Aggiungere una nuova serie al grafico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Questa sezione cancella i dati esistenti e aggiunge due nuove serie al nostro grafico a dispersione.

### Aggiunta di punti dati per serie di dispersione
Per visualizzare i nostri dati, aggiungiamo punti a ciascuna serie nel grafico a dispersione.

#### Aggiungi punti dati
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Noi usiamo `addDataPointForScatterSeries()` Per aggiungere punti dati alla nostra prima serie. I parametri definiscono i valori X e Y.

### Tipo di serie e modifica del marcatore
Personalizza l'aspetto del tuo grafico modificando il tipo e lo stile dei marcatori in ogni serie.

#### Serie personalizzata
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifica della seconda serie
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Queste modifiche modificano il tipo di serie per utilizzare linee rette e marcatori. Abbiamo anche impostato la dimensione e il simbolo del marcatore per una distinzione visiva.

### Salvataggio della presentazione
Infine, salva la presentazione con tutte le modifiche apportate.

#### Salva la tua presentazione
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Utilizzo `SaveFormat.Pptx` per specificare il formato PowerPoint in cui salvare il file. Questo passaggio è fondamentale per preservare tutte le modifiche.

## Applicazioni pratiche
Ecco alcuni casi d'uso concreti:
1. **Analisi finanziaria**: Utilizza i grafici a dispersione per visualizzare l'andamento dei titoli azionari nel tempo.
2. **Ricerca scientifica**: Rappresenta i punti dati sperimentali per l'analisi.
3. **Gestione del progetto**: Visualizza l'allocazione delle risorse e le metriche di progresso.

L'integrazione di Aspose.Slides nel tuo sistema ti consente di automatizzare la generazione di report, migliorando la produttività e la precisione.

## Considerazioni sulle prestazioni
Per prestazioni ottimali:
- Gestisci l'utilizzo della memoria eliminando le presentazioni dopo averle salvate.
- Utilizzare strutture dati efficienti per set di dati di grandi dimensioni.
- Ridurre al minimo le operazioni che richiedono molte risorse all'interno dei cicli.

Le migliori pratiche garantiscono un'esecuzione fluida anche in caso di manipolazioni complesse dei grafici.

## Conclusione
In questo tutorial, hai imparato a configurare directory, inizializzare presentazioni Aspose.Slides, creare e personalizzare grafici a dispersione, gestire i dati delle serie, modificare i marcatori e salvare il tuo lavoro. Per esplorare ulteriormente le funzionalità di Aspose.Slides, prendi in considerazione l'idea di approfondire funzionalità più avanzate come animazioni e transizioni tra diapositive.

**Prossimi passi**: Sperimenta diversi tipi di grafici o integra queste tecniche in un progetto Java più ampio.

## Domande frequenti

### Come faccio a cambiare il colore dei pennarelli?
Per cambiare il colore del marcatore, utilizzare `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Dove `ColorObject` è il colore desiderato.

### Posso aggiungere più di due serie a un grafico a dispersione?
Sì, puoi aggiungere tutte le serie che desideri ripetendo il processo di aggiunta di nuove serie e punti dati.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}