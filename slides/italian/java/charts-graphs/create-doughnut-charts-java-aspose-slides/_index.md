---
date: '2026-03-07'
description: Scopri come creare un grafico a ciambella in Java usando Aspose.Slides.
  Questa guida passo passo copre la configurazione della dipendenza Maven di Aspose
  Slides, la configurazione del grafico e il salvataggio delle presentazioni.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Crea un grafico a ciambella Java con la guida Aspose.Slides
url: /it/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea un grafico a ciambella Java con la Guida Aspose.Slides

## Introduzione

Creare un **grafico a ciambella** programmaticamente può trasformare numeri grezzi in un visual accattivante che racconta subito una storia. In Java, **Aspose.Slides** rende questo processo semplice, permettendoti di generare grafici pronti per le presentazioni senza mai aprire PowerPoint. In questo tutorial imparerai a **creare un grafico a ciambella in Java** passo dopo passo — dalla configurazione della dipendenza Maven di Aspose Slides alla personalizzazione di serie, categorie e, infine, al salvataggio della presentazione.

Al termine di questa guida sarai in grado di incorporare grafici a ciambella dinamici in qualsiasi file PPTX, perfetti per report, dashboard o presentazioni automatizzate.

### Risposte rapide
- **Quale libreria viene usata?** Aspose.Slides per Java  
- **Compito principale?** Creare un grafico a ciambella in Java in un file PPTX  
- **Come aggiungere la libreria?** Usa la dipendenza Maven di Aspose Slides (o Gradle)  
- **Versione minima di Java?** JDK 16 o superiore  
- **Posso personalizzare colori ed etichette?** Sì, l'API fornisce il pieno controllo di formattazione  

## Cos'è un grafico a ciambella e perché usarlo?

Un grafico a ciambella è una variante del grafico a torta con un centro vuoto, che consente di visualizzare più serie di dati in anelli concentrici. Questo lo rende ideale per confrontare parti di un intero attraverso diverse categorie — ad esempio vendite per regione su più trimestri o allocazioni di budget tra dipartimenti.

## Perché usare Aspose.Slides per Java?

- **Nessuna installazione di Office richiesta** – genera file PPTX su qualsiasi server.  
- **API ricca** – controllo completo su tipi di grafico, punti dati e stile.  
- **Alte prestazioni** – ottimizzato per presentazioni di grandi dimensioni.  
- **Cross‑platform** – funziona su Windows, Linux e macOS.

## Prerequisiti

- **Librerie richieste:**  
  - Aspose.Slides per Java versione 25.4 o successiva.  

- **Configurazione dell'ambiente:**  
  - JDK 16 o superiore.  
  - Il tuo IDE preferito (IntelliJ IDEA, Eclipse, NetBeans, ecc.).  

- **Conoscenze preliminari:**  
  - Programmazione Java di base.  
  - Familiarità con Maven o Gradle per la gestione delle dipendenze.

## Dipendenza Maven di Aspose Slides

Aggiungi la seguente dipendenza Maven al tuo `pom.xml`. Questa è la **dipendenza Maven di Aspose Slides** necessaria per includere la libreria nel tuo progetto.

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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Puoi anche scaricare il JAR direttamente dalla pagina di rilascio ufficiale:  
[ Rilasci di Aspose.Slides per Java ](https://releases.aspose.com/slides/java/)

### Ottenere una licenza

Per rimuovere la filigrana di valutazione e sbloccare l'intero set di funzionalità:

- **Versione di prova** – inizia con una licenza temporanea.  
- **Licenza temporanea** – richiedila dal [sito web Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licenza commerciale** – acquista per l'uso in produzione.

Applica la licenza nel tuo codice:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guida all'implementazione

### Inizializzare la presentazione e aggiungere un grafico a ciambella

Per prima cosa, crea o carica una presentazione e aggiungi un grafico a ciambella alla prima diapositiva.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurare il workbook dei dati del grafico e cancellare i dati esistenti

Successivamente, ottieni il workbook che supporta il grafico e rimuovi eventuali serie o categorie predefinite.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Aggiungere serie al grafico

Ora aggiungeremo fino a 15 serie. Ogni serie può essere personalizzata — qui impostiamo l'esplosione, la dimensione del foro della ciambella e l'angolo della prima fetta.

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

### Aggiungere categorie e punti dati

Creeremo 15 categorie e popoleremo ogni serie con un punto dati. L'ultima serie riceve una formattazione speciale delle etichette.

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

### Salvare la presentazione

Infine, scrivi la presentazione aggiornata su disco.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Problemi comuni e soluzioni

- **Licenza non trovata** – Verifica che il percorso verso `license.lic` sia corretto e che il file sia leggibile.  
- **Il grafico appare vuoto** – Assicurati di aver cancellato le serie/categorie esistenti prima di aggiungerne di nuove.  
- **Colori errati** – Controlla che `FillType.Solid` sia impostato sia per il riempimento che per il formato linea.  
- **Prestazioni con molte serie** – Limita il numero di serie/categorie o riutilizza le celle del workbook.

## Domande frequenti

**D: Posso generare un grafico a ciambella senza un file PPTX preesistente?**  
R: Sì, istanzia `new Presentation()` per partire da una presentazione vuota.

**D: Aspose.Slides supporta l'esportazione in PDF?**  
R: Assolutamente. Dopo aver creato il grafico, chiama `pres.save("output.pdf", SaveFormat.Pdf);`.

**D: Come modifico la dimensione del foro della ciambella?**  
R: Usa `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` dove *value* è compreso tra 0‑100.

**D: È possibile aggiungere etichette dati a tutte le serie, non solo all'ultima?**  
R: Sì, sposta il blocco di formattazione delle etichette fuori dalla condizione `if (i == ...)` e applicalo a ogni `dataPoint`.

**D: Quali versioni di Java sono supportate?**  
R: Aspose.Slides 25.4 supporta JDK 16 e versioni successive. Versioni Java precedenti richiedono il classifier appropriato.

---

**Ultimo aggiornamento:** 2026-03-07  
**Testato con:** Aspose.Slides per Java 25.4 (classifier jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}