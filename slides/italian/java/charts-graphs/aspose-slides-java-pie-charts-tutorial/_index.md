---
date: '2026-01-22'
description: Scopri come personalizzare i colori dei grafici a torta e aggiungere
  il titolo del grafico usando Aspose.Slides per Java. Include la configurazione di
  Aspose Slides per Maven e come salvare la presentazione pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Come personalizzare i colori dei grafici a torta in Java con Aspose.Slides:
  una guida completa'
url: /it/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creare grafici a torta con Aspose.Slides per Java: Come **personalizzare i colori del grafico a torta** – Un tutorial completo

## Introduction
Fornire storie è più semplice quando è possibile **personalizzare i colori del grafico a torta** per adattarli al proprio brand o evidenz del grafico, gestire i punti dati del grafico a tort progetto Java il titolo del grafico e gestire i punti dati del grafico a torta.
- Tecniche per **personalizzare i colori del grafico a torta** per un impatto visivo massimo.
- Configurazione della dipendenza Maven Aspose Slides.
- Salvataggio del file finale come presentazione PPTX.

Iniziamo!

## Quick Answers
- **Come aggiungo un titolo al grafico?** Usa `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **Quale strumento di build funziona meglio?** Sia Maven che Gradle sono supportati; Maven Aspose Slides è il più comune.
- **Posso cambiare i colori delle fette?** Sì—imposta `setColorVaried(true)` e regola il riempimento di ogni `DataPoint`.
- **In quale formato viene salvato il file?** Usa `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **Ho bisogno di una licenza?** Una prova gratuita funziona per lo sviluppo; è necessaria una licenza permanente per la produzione.

## Prerequisites
- **Aspose.Slides per Java** ≥ 25.4 (si consiglia l'ultima versione).
- **JDK 16+** installato e configurato.
- Un IDE come IntelliJ IDEA, Eclipse o NetBeans.
- Conoscenze di base di Java e familiarità con Maven o Gradle.

## Setting Up Aspose.Slides for Java
Per iniziare a usare Aspose.Slides, aggiungi la libreria al tuo progetto.

**Maven** (maven aspose slides)  
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

**Direct Download**  
Se preferisci non usare uno strumento di build, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Prova gratuita** – inizia a sperimentare senza licenza.
- **Licenza temporanea** – estendi l'uso della prova.
- **Acquisto** – ottieni una licenza completa per le distribuzioni in produzione.

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
Di seguito trovi una guida passo‑passo che mantiene il codice esattamente come si aspetta la libreria originale.

### Step 1: Initialize Presentation and Slide
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Step 2: Add a Pie Chart to the Slide
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Step 3: Add Chart Title
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Step 4: Show Data Labels for the First Series
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Step 5: Prepare the Chart Data Worksheet
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Step 6: Add Categories (pie chart data points)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Step 7: Add Series and Populate Data Points
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Step 8: **Customize Pie Chart Colors** – The Core of This Tutorial
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Step 9: Configure Custom Data Labels
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Step 10: Set Rotation Angle and **Save Presentation PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Common Issues & Troubleshooting
- **Colori mancanti dopo l'esportazione** – Assicurati che `setColorVaried(true)` sia chiamato prima di modificare i singoli punti dati.
- **I punti dati non vengono visualizzati** – Verifica che categorie e serie siano svuotate prima di aggiungerne di nuove (vedi Step 5).
- **Licenza non applicata** – Carica il file di licenza prima di creare l'oggetto `Presentation` per evitare filigrane di prova.

## Frequently Asked Questions

**Q: Posso usare questo codice con versioni JDK più vecchie?**  
A: La libreria richiede JDK 16 o superiore; le versioni più vecchie non sono supportate.

**Q: Come modifico il titolo del grafico dopo la creazione?**  
A: Chiama `chart.getChartTitle().addTextFrameForOverriding("New Title")` e regola il formato del testo secondo necessità.

**Q: È possibile esportare in formati diversi da PPTX?**  
A: Sì—Aspose.Slides supporta PDF, ODP e diversi formati immagine tramite l'enumerazione `SaveFormat`.

**Q: Cosa succede se voglio animare le fette del grafico a torta?**  
A: Usa l'API `SlideShow` per aggiungere transizioni diapositive o animazioni di forme dopo la creazione del grafico.

**Q: La dipendenza Maven include tutte le librerie transitive?**  
A: L'artefatto Maven Aspose Slides recupera automaticamente le dipendenze necessarie; non sono necessari passaggi aggiuntivi.

## Conclusion
Ora hai un esempio completo, pronto per la produzione, che mostra **come personalizzare i colori del grafico a torta**, aggiungere un titolo al grafico, gestire i punti dati del grafico a torta e **salvare una presentazione pptx** usando Aspose.Slides per Java. Sentiti libero di sperimentare con diverse palette di colori, set di dati e angoli di rotazione per adattarli allo stile del tuo brand.

---

**Ultimo aggiornamento:** 2026-01-22  
**Testato con:** Aspose.Slides 25.4 (JDK 16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}