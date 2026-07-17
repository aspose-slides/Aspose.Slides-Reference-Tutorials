---
date: '2026-07-17'
description: Scopri come ruotare un grafico a torta, personalizzare i colori del grafico
  a torta e esportare la diapositiva in PDF usando Aspose.Slides per Java – una guida
  completa alla visualizzazione dei dati.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Ruota il grafico a torta e personalizza i colori del grafico a torta
  usando Aspose.Slides per Java. Scopri come esportare la diapositiva in PDF e lavorare
  con il foglio dati del grafico.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Ruota il grafico a torta e personalizza i colori in Java – Guida Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Come ruotare un grafico a torta e personalizzare i colori in Java con Aspose.Slides
url: /it/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creare grafici a torta con Aspose.Slides per Java: un tutorial completo

## Introduzione
In questa guida imparerai a **ruotare gli elementi del grafico a torta**, personalizzare il colore di ogni fetta e esportare la diapositiva finale in PDF — tutto con Aspose.Slides per Java. Che tu stia costruendo un cruscotto di vendite, un report finanziario o qualsiasi presentazione basata sui dati, padroneggiare queste tecniche ti permette di fornire visualizzazioni chiare e accattivanti senza dipendere da Microsoft Office. Prepariamo gli strumenti e immergiamoci.

## Risposte rapide
- **Quale classe avvia una nuova presentazione?** `Presentation` from `com.aspose.slides`.
- **Quale chiamata API aggiunge un grafico a torta?** `slide.addChart(ChartType.Pie, …)`.
- **Come puoi assegnare a ogni fetta un colore unico?** Call `series.setColorVaried(true)` and set solid fills per data point.
- **Quale metodo ruota il grafico?** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **La diapositiva può essere esportata in PDF?** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Che cosa significa “personalizzare i colori del grafico a torta”?
Personalizzare i colori del grafico a torta significa assegnare colori di riempimento distinti a ciascuna fetta, migliorando la leggibilità e l'impatto visivo. In Aspose.Slides lo ottieni abilitando i colori variabili e poi impostando colori di riempimento solidi per i singoli punti dati. Questo approccio garantisce che ogni segmento di dati risalti chiaramente nella presentazione.

## Perché usare Aspose.Slides per Java per creare grafici a torta?
Aspose.Slides supporta **150+ tipi di grafico** e può renderizzare una presentazione di 300 pagine in meno di **5 secondi** su un server tipico, il tutto senza necessità di Microsoft Office installato. La libreria funziona su Windows, Linux e macOS, offrendoti flessibilità cross‑platform per qualsiasi progetto di visualizzazione dati basato su Java.

## Prerequisiti
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 o newer
- IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- Basic Java knowledge and familiarity with Maven or Gradle

## Configurazione di Aspose.Slides per Java
Aggiungi la libreria alla tua configurazione di build.

**Maven**  
Add this snippet to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Include the following in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
If you prefer a manual approach, download the latest JAR from [Rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

### Passaggi per l'acquisizione della licenza
- **Free Trial** – explore all features without cost.  
- **Temporary License** – extend trial limits for a short period.  
- **Purchase** – obtain a permanent license for production use.  

**Inizializzazione e configurazione di base**  
The `Presentation` class represents a PowerPoint file in memory and provides methods to manipulate slides.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guida all'implementazione
Below is a step‑by‑step walkthrough that covers everything from creating a slide to rotating the final pie chart.

### Inizializzare la presentazione e la diapositiva
Create a new `Presentation` instance and retrieve the first slide to serve as the chart canvas.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Aggiungere un grafico a torta alla diapositiva
`addChart` adds a chart shape of the specified type to the slide at given coordinates.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Impostare il titolo del grafico
`setTitle` assigns a text title to the chart and positions it centrally.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurare le etichette dei dati per la serie
`setShowValue(true)` enables numeric value labels on each data point of the series.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparare il foglio di lavoro dei dati del grafico
`ChartDataWorkbook` stores the underlying data table that feeds the chart series and categories.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Aggiungere categorie al grafico
`addCategory` creates a new category label for the chart's data series.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Aggiungere serie e popolare i punti dati
`addSeries` creates a data series, and `addDataPointForBarSeries` inserts numeric values for each category.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizzare i colori e i bordi della serie
`setColorVaried(true)` enables per-slice colors, and `setFillFormat` assigns a solid fill to each data point.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurare etichette dati personalizzate
`setDataLabelFormat` customizes label appearance, position, and font for clearer chart annotations.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Impostare l'angolo di rotazione e salvare la presentazione
`setRotationAngle` rotates the entire pie chart, and `save` writes the presentation to a file.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Come ruotare un grafico a torta?
Load the chart object, call `chart.setRotationAngle(45.0)` (or any degree value), and then save the presentation. Rotating a pie chart shifts the start angle, allowing you to emphasize a particular segment without altering the data. This single method call works for any `Chart` instance in Aspose.Slides. You can also combine rotation with varied slice colors to draw attention to the most important data point.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Le fette appaiono tutte dello stesso colore** | `setColorVaried(true)` non chiamato | Ensure you enable varied colors on the series group. |
| **Le etichette dei dati non vengono visualizzate** | flag `showValue` disabilitato | Call `setShowValue(true)` on the label format. |
| **La rotazione non ha effetto** | Utilizzo di una versione più vecchia di Aspose.Slides | Upgrade to version 25.4 or later. |
| **Eccezione di licenza a runtime** | File di licenza mancante o non valido | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## Domande frequenti

**Q: Come posso ottenere una licenza Aspose.Slides per Java?**  
A: Request a free trial from the Aspose website, then purchase a permanent license. Load it at runtime as shown in the Common Issues table.

**Q: Posso usare questo codice con versioni JDK più vecchie?**  
A: The API requires JDK 16 or higher; older versions are not supported.

**Q: È possibile esportare il grafico come immagine invece di PPTX?**  
A: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Cosa succede se ho bisogno di più di una serie in un grafico a torta?**  
A: Pie charts are designed for a single data series; for multiple series, consider using a doughnut chart.

**Q: Aspose.Slides funziona su server Linux?**  
A: Absolutely—Aspose.Slides for Java is platform‑independent and works on any OS with a compatible JDK.

---

**Ultimo aggiornamento:** 2026-07-17  
**Testato con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come creare grafici a torta nelle presentazioni Java usando Aspose.Slides: una guida completa](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Padroneggiare i grafici a torta in Java con Aspose.Slides: una guida completa](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Ruotare i testi del grafico in Java con Aspose.Slides: una guida completa](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}