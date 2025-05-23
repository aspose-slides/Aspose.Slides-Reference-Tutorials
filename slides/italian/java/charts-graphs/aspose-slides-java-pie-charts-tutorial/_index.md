---
"date": "2025-04-17"
"description": "Scopri come creare e personalizzare grafici a torta utilizzando Aspose.Slides per Java. Questo tutorial copre tutto, dalla configurazione alla personalizzazione avanzata."
"title": "Creazione di grafici a torta in Java con Aspose.Slides&#58; una guida completa"
"url": "/it/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creazione di grafici a torta con Aspose.Slides per Java: un tutorial completo

## Introduzione
Creare presentazioni dinamiche e visivamente accattivanti è fondamentale per trasmettere informazioni di grande impatto. Con Aspose.Slides per Java, puoi integrare perfettamente grafici complessi come i grafici a torta nelle tue diapositive, migliorando la visualizzazione dei dati senza sforzo. Questa guida completa ti guiderà attraverso il processo di creazione e personalizzazione di un grafico a torta utilizzando Aspose.Slides Java, risolvendo facilmente le più comuni sfide di presentazione.

**Cosa imparerai:**
- Inizializzazione di una presentazione e aggiunta di diapositive.
- Creazione e configurazione di un grafico a torta sulla diapositiva.
- Impostazione di titoli di grafici, etichette dati e colori.
- Ottimizzare le prestazioni e gestire efficacemente le risorse.
- Integrazione di Aspose.Slides in progetti Java utilizzando Maven o Gradle.

Cominciamo assicurandoci che tu abbia tutti gli strumenti e le conoscenze necessarie per seguire il tutorial!

## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere pronta la seguente configurazione:

### Librerie, versioni e dipendenze richieste
- **Aspose.Slides per Java**: Assicurati di avere la versione 25.4 o successiva.
- **Kit di sviluppo Java (JDK)**: È richiesta la versione 16 o successiva.

### Requisiti di configurazione dell'ambiente
- Un ambiente di sviluppo con Java installato e configurato.
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA, Eclipse o NetBeans.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione Java.
- Familiarità con Maven o Gradle per la gestione delle dipendenze.

## Impostazione di Aspose.Slides per Java
Per iniziare a utilizzare Aspose.Slides nei tuoi progetti Java, devi aggiungere la libreria come dipendenza. Ecco come puoi farlo utilizzando diversi strumenti di build:

**Esperto**
Aggiungi questo frammento al tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Includi quanto segue nel tuo `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download diretto**
Se preferisci non utilizzare uno strumento di compilazione, scarica l'ultima versione da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Fasi di acquisizione della licenza
- **Prova gratuita**: Inizia con una prova gratuita per esplorare le funzionalità di Aspose.Slides.
- **Licenza temporanea**: Ottieni una licenza temporanea per un utilizzo prolungato senza limitazioni.
- **Acquistare**: Valuta l'acquisto se hai bisogno di un accesso a lungo termine.

**Inizializzazione e configurazione di base**
Per iniziare a utilizzare Aspose.Slides, inizializza il progetto creando un nuovo oggetto presentazione:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guida all'implementazione
Ora scomponiamo il processo di aggiunta e personalizzazione di un grafico a torta in passaggi gestibili.

### Inizializza presentazione e diapositiva
Inizia impostando una nuova presentazione e accedendo alla prima diapositiva. Questa è la tua tela per creare grafici:
```java
import com.aspose.slides.*;

// Crea una nuova istanza di presentazione.
Presentation presentation = new Presentation();
// Accedi alla prima diapositiva della presentazione.
islide slides = presentation.getSlides().get_Item(0);
```

### Aggiungi grafico a torta alla diapositiva
Inserisci un grafico a torta nella posizione specificata con un set di dati predefinito:
```java
import com.aspose.slides.*;

// Aggiungere un grafico a torta nella posizione (100, 100) con dimensione (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Imposta il titolo del grafico
Personalizza il tuo grafico impostando e centrando il titolo:
```java
import com.aspose.slides.*;

// Aggiungere un titolo al grafico a torta.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurare le etichette dati per le serie
Per maggiore chiarezza, assicurarsi che le etichette dei dati mostrino i valori:
```java
import com.aspose.slides.*;

// Mostra i valori dei dati sulla prima serie.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparare il foglio di lavoro dei dati del grafico
Imposta il foglio di lavoro dei dati del grafico cancellando le serie e le categorie esistenti:
```java
import com.aspose.slides.*;

// Preparare la cartella di lavoro dei dati del grafico.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Aggiungi categorie al grafico
Definisci le categorie per il tuo grafico a torta:
```java
import com.aspose.slides.*;

// Aggiungi nuove categorie.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Aggiungi serie e popola punti dati
Crea una serie e inserisci i punti dati:
```java
import com.aspose.slides.*;

// Aggiungi una nuova serie e impostane il nome.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizza i colori e i bordi della serie
Migliora l'aspetto visivo impostando i colori e personalizzando i bordi:
```java
import com.aspose.slides.*;

// Imposta colori diversi per i settori della serie.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ripetere la stessa operazione per altri punti dati, utilizzando colori e stili diversi.
```

### Configura etichette dati personalizzate
Ottimizza le etichette per ogni punto dati:
```java
import com.aspose.slides.*;

// Configura etichette personalizzate.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Abilita le linee guida per le etichette.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Imposta l'angolo di rotazione e salva la presentazione
Completa il tuo grafico a torta impostando un angolo di rotazione e salvando la presentazione:
```java
import com.aspose.slides.*;

// Imposta l'angolo di rotazione.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Salva la presentazione in un file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, hai imparato a creare e personalizzare grafici a torta utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi migliorare le tue presentazioni con visualizzazioni di dati visivamente accattivanti. Per qualsiasi domanda o ulteriore assistenza, non esitare a contattarci.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}