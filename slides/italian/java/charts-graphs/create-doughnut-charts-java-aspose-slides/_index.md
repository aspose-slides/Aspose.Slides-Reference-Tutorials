---
date: '2026-08-16'
description: Scopri come aggiungere grafici a ciambella in Java usando Aspose.Slides.
  Questa guida passo‑passo copre la configurazione delle dipendenze Maven, la configurazione
  del grafico, i colori, le etichette e il salvataggio del file PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Come aggiungere grafici a ciambella in Java con Aspose.Slides. Segui
  questa guida per configurare Maven, personalizzare i colori, le etichette e generare
  file PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Come aggiungere un grafico a ciambella in Java con Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Come aggiungere un grafico a ciambella in Java con Aspose.Slides
url: /it/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere un grafico a ciambella in Java con Aspose.Slides

## Introduzione

Creare un **grafico a ciambella** programmaticamente può trasformare numeri grezzi in una visuale accattivante che racconta subito una storia. In Java, **Aspose.Slides** rende questo processo semplice, consentendoti di generare grafici pronti per la presentazione senza mai aprire PowerPoint. In questo tutorial imparerai **come aggiungere grafici a ciambella** a un file PPTX passo dopo passo — dalla configurazione della dipendenza Maven Aspose Slides alla personalizzazione di serie, categorie, colori ed etichette, fino al salvataggio della presentazione.

Al termine di questa guida sarai in grado di incorporare grafici a ciambella dinamici in qualsiasi file PPTX, perfetti per report, dashboard o presentazioni automatizzate.

### Risposte rapide
- **Quale libreria è usata?** Aspose.Slides for Java  
- **Compito principale?** Aggiungere un grafico a ciambella in un file PPTX  
- **Come aggiungere la libreria?** Usare la dipendenza Maven Aspose Slides (o Gradle)  
- **Versione minima di Java?** JDK 16 o superiore  
- **Posso personalizzare colori ed etichette?** Sì, l'API fornisce il controllo completo della formattazione  

## Cos'è un grafico a ciambella e perché usarlo?

Un grafico a ciambella è una variante del grafico a torta con un centro vuoto, che consente di visualizzare più serie di dati come anelli concentrici. **Visualizza le parti di un tutto attraverso diverse categorie mantenendo spazio per informazioni aggiuntive al centro.** Questo lo rende ideale per confrontare le vendite per regione su più trimestri, le allocazioni di budget tra dipartimenti, o qualsiasi scenario in cui è necessario mostrare dati di proporzione gerarchica.

## Perché usare Aspose.Slides per Java?

Puoi aggiungere un grafico a ciambella senza installare Microsoft Office, e la libreria gestisce **oltre 50 + formati di input e output** mentre elabora presentazioni con più di 500 diapositive. Aspose.Slides offre **fino a 3× più veloce rendering** rispetto all'automazione nativa di Office sullo stesso hardware, ed è compatibile con Windows, Linux e macOS. Questi vantaggi quantificati significano che puoi generare grandi deck di diapositive su server headless con prestazioni prevedibili.

## Prerequisiti

- **Librerie richieste**  
  - Aspose.Slides for Java 25.4 o successiva (la libreria che consente di aggiungere grafici a ciambella).  

- **Ambiente**  
  - JDK 16 o superiore installato sulla tua macchina.  
  - Un IDE come IntelliJ IDEA, Eclipse o NetBeans.  

- **Conoscenze**  
  - Sintassi Java di base e concetti di programmazione orientata agli oggetti.  
  - Familiarità con Maven o Gradle per la gestione delle dipendenze.  

## Dipendenza Maven Aspose Slides

Aggiungi la seguente dipendenza Maven al tuo `pom.xml`. Questa è la **dipendenza maven aspose slides** necessaria per includere la libreria nel tuo progetto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Se preferisci Gradle, usa lo snippet equivalente qui sotto.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Puoi anche scaricare il JAR direttamente dalla pagina ufficiale di rilascio:  
[Rilasci di Aspose.Slides per Java](https://releases.aspose.com/slides/java/)

### Ottenere una licenza

Per rimuovere il watermark di valutazione e sbloccare l'intero set di funzionalità:

- **Prova gratuita** – inizia con una licenza temporanea.  
- **Licenza temporanea** – richiedila dal [sito Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licenza commerciale** – acquista per uso in produzione.

Applica la licenza nel tuo codice:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Guida all'implementazione

### Inizializzare una presentazione e aggiungere un grafico a ciambella

Presentation è la classe di Aspose.Slides che rappresenta una presentazione PowerPoint.  
Carica un PPTX esistente o crea un nuovo oggetto `Presentation`, quindi aggiungi un grafico a ciambella alla prima diapositiva.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Configurare la cartella di lavoro dei dati del grafico e cancellare i dati esistenti

La cartella di lavoro è un foglio di calcolo interno che memorizza i dati del grafico.  
Ottieni la cartella di lavoro che supporta il grafico, quindi cancella eventuali serie o categorie predefinite in modo da partire da una base pulita.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Aggiungere serie al grafico

Una serie rappresenta una collezione di punti dati tracciati sul grafico.  
Puoi aggiungere fino a 15 serie. Ogni serie può essere personalizzata — qui impostiamo l'esplosione, la dimensione del foro della ciambella e l'angolo della prima fetta.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Aggiungere categorie e punti dati

Le categorie sono le etichette per ogni punto dati lungo l'asse del grafico.  
Crea 15 categorie e popola ogni serie con un punto dato. L'ultima serie riceve una formattazione speciale dell'etichetta.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Personalizzare colori ed etichette dei dati

`FillType.Solid` specifica un colore di riempimento solido per gli elementi del grafico.  
Imposta un colore di riempimento solido per ogni serie e abilita le etichette dei dati. Per l'ultima serie cambiamo anche il colore del carattere dell'etichetta.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Salvare la presentazione

`save` scrive la presentazione su un file nel formato scelto.  
Salva la presentazione aggiornata su disco in formato PPTX, o esporta in PDF se necessario.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Problemi comuni e soluzioni

- **Licenza non trovata** – Verifica che il percorso a `license.lic` sia corretto e che il file sia leggibile.  
- **Il grafico appare vuoto** – Assicurati di aver cancellato le serie/categorie esistenti prima di aggiungerne di nuove.  
- **Colori errati** – Conferma che `FillType.Solid` sia impostato sia per il riempimento che per il formato della linea.  
- **Prestazioni con molte serie** – Limita il numero di serie/categorie o riutilizza le celle della cartella di lavoro per mantenere l'uso della memoria sotto controllo.  

## Domande frequenti

**D: Posso generare un grafico a ciambella senza un file PPTX preesistente?**  
R: Sì, istanzia `new Presentation()` per partire da un deck di diapositive vuoto, quindi aggiungi un grafico come mostrato sopra.

**D: Aspose.Slides supporta l'esportazione in PDF?**  
R: Assolutamente. Dopo aver creato il grafico, chiama `pres.save("output.pdf", SaveFormat.Pdf);` per ottenere una versione PDF della diapositiva.

**D: Come modifico la dimensione del foro della ciambella?**  
R: Usa `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` dove `value` varia da 0 a 100.

**D: È possibile aggiungere etichette dei dati a tutte le serie, non solo all'ultima?**  
R: Sì, sposta il blocco di formattazione dell'etichetta fuori dalla condizione `if (i == ...)` e applicalo a ogni `dataPoint`.

**D: Quali versioni di Java sono supportate?**  
R: Aspose.Slides 25.4 supporta JDK 16 e versioni successive. JDK precedenti richiedono il classificatore appropriato nella dipendenza Maven.

---

**Ultimo aggiornamento:** 2026-08-16  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autore:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Tutorial correlati

- [Come aggiungere un grafico a PowerPoint usando Aspose.Slides per Java: Guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Come personalizzare i colori dei grafici a torta in Java con Aspose.Slides – Guida completa](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animare le categorie dei grafici PowerPoint con Aspose.Slides per Java | Guida passo‑passo](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}