---
date: '2026-01-24'
description: Guida passo‑passo per creare un grafico a dispersione in Java usando
  Aspose.Slides, aggiungere punti dati a dispersione e lavorare con grafici a dispersione
  a più serie.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Crea un grafico a dispersione Java con Aspose.Slides – Personalizza e salva
url: /it/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea un grafico a dispersione Java con Aspose.Slides

In questo tutorial **creerai un grafico a dispersione Java** da zero, aggiungerai punti dati scatter e imparerai a lavorare con grafici a dispersione a più serie, il tutto utilizzando Aspose.Slides per Java. Ti guideremo attraverso la configurazione della directory, l'inizializzazione della presentazione, la creazione del grafico, la gestione dei dati, la personalizzazione dei marcatori e, infine, il salvataggio della presentazioni usando Aspose.Slides  
- Creare un grafico a dispersione su una diapositiva  
 serie  
- Personalizzare i tipi di serie, i marcatori e gestire grafici a dispersione a più serie  
- Salvare la presentazione finale  

Iniziamo con i prerequisiti.

## Risposte rapide
- **Qual è la libreria principale?** Aspose.Slides for Java  
- **Quale versione di Java è richiesta?** JDK 8 or higher (JDK 16 recommended)  
- **Posso aggiungere più di due serie?** Yes – you can add any number of series to a scatter chart  
- **Come cambiare i colori dei marcatori?** Use `series.getMarker().getFillFormat().setFillColor(Color)`  
- **È necessaria una licenza per la produzione?** Yes, a commercial license removes evaluation limits  

## Prerequisiti

Per seguire questo tutorial, assicurati di avere:
- **Aspose.Slides for Java** – versione 25.4 o successiva.  
- **Java Development Kit (JDK)** – JDK 8 o più recente.  
- Conoscenze di base di Java e familiarità con Maven o Gradle.  

## Configurare Aspose.Slides per Java

Integra Aspose.Slides nel tuo progetto con uno dei seguenti metodi.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Oppure scarica il pacchetto più recente da [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
- **Free Trial** – valutazione di 30 giorni.  
- **Temporary License** – test esteso.  
- **Commercial License** – utilizzo in produzione completo.

Ora immergiamoci nel codice.

## Guida all'implementazione

### Passo 1: Configurazione della directory
Prima, assicurati che la cartella di output esista in modo che la presentazione possa essere salvata senza errori.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Passo 2: Inizializzazione della presentazione
Crea una nuova presentazione e ottieni la prima diapositiva.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Passo 3: Aggiungi un grafico a dispersione
Inserisci un grafico a dispersione con linee fluide nella diapositiva.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Passo 4: Gestire i dati del grafico (cancellare e aggiungere serie)
Rimuovi eventuali serie predefinite e aggiungi le nostre serie per il **grafico a dispersione a più serie**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Passo 5: Aggiungi punti dati scatter
Popola ogni serie con valori X‑Y usando **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Passo 6: Personalizzare i tipi di serie e i marcatori
Regola lo stile visivo—passa a linee rette con marcatori e imposta simboli di marcatore distinti.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Passo 7: Salva la presentazione
Salva il file su disco.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Applicazioni pratiche
- **Financial Analysis** – Traccia i movimenti dei prezzi delle azioni con un grafico a dispersione a più serie.  
- **Scientific Research** – Visualizza le misurazioni sperimentali usando **add data points scatter** per una rappresentazione dati precisa.  
- **Project Management** – Mostra le tendenze di allocazione delle risorse attraverso diversi progetti su un unico grafico a dispersione.

## Considerazioni sulle prestazioni
- Disporre dell'oggetto `Presentation` dopo il sal- Per grandi set di dati, popola il workbook in batch anziché uno per uno.  
- Evita stilizzazioni eccessive all'interno di loop stretti; applica gli stili dopo l'inserimento dei dati.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Il grafico appare vuoto** | Verifica che i punti dati siano aggiunti alla serie corretta e che gli indici del workbook corrispondano. |
| **I marcatori non sono visibili** | il simbolo del marcat **OutOfMemoryError su grafici grandi** | Usa `pres.dispose()` Posso aggiungere più di due serie a un grafico a dispersione?
Assolutamente. Ripeti il blocco di creazione della serie (Passo 4) per ogni serie aggiuntiva necessaria.

### È possibile esportare il grafico come immagine?
S dati.

### Aspattivi sui punti di dispersione?
Sebbene PowerPoint non fornisca tooltip in fase di esecuzione, è possibile incorporare etichette dati usando `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### Come posso animare le serie a dispersione?
Usa `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` per aggiungere una semplice animazione di apparizione.

---

**Ultimo aggiornamento:** 2026-01-24  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}