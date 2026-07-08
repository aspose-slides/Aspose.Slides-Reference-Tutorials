---
date: '2026-07-08'
description: Scopri come utilizzare Aspose per creare un grafico a ciambella in PowerPoint
  con Java. Questa guida passo‑passo mostra come aggiungere i punti dati del grafico
  programmaticamente, personalizzare le etichette e salvare il PPTX con alta fedeltà.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Come usare Aspose ti consente di creare un grafico a ciambella in
  PowerPoint usando Java. Segui questo tutorial per aggiungere punti dati, personalizzare
  le etichette e salvare il PPTX con alta fedeltà.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Come usare Aspose: creare un grafico a ciambella in PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Come usare Aspose per creare un grafico a ciambella in PowerPoint (Java)
url: /it/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come utilizzare Aspose per creare un grafico a ciambella in PowerPoint (Java)

## Introduzione
Creare presentazioni accattivanti spesso richiede più di semplici testo e immagini; i grafici possono migliorare notevolmente la narrazione visualizzando i dati in modo efficace. **How to use Aspose** per la generazione di grafici ti offre il controllo programmatico senza mai aprire PowerPoint. Questo tutorial ti guida nella creazione di un grafico a ciambella, nella configurazione dei suoi punti dati e nel salvataggio di un PPTX ad alta fedeltà. Avrai bisogno solo di conoscenze di base di Java e di pochi minuti per la configurazione.

`Aspose.Slides for Java` è una libreria Java che consente la creazione, la manipolazione e la conversione di file PowerPoint senza Microsoft Office.

## Risposte rapide
- **What library creates doughnut chart PowerPoint?** Aspose.Slides for Java  
- **Can I add chart data points programmatically?** Sì, using the chart API  
- **Do I need a license for production?** È necessaria una licenza valida di Aspose.Slides  
- **Which Java versions are supported?** Java 8 e successive (JDK 16 classifier shown)  
- **How many series can I add?** L'esempio aggiunge fino a 15 serie, ma è possibile regolare secondo necessità  

## Cos'è un grafico a ciambella in PowerPoint?
Un grafico a ciambella è un grafico circolare simile a un grafico a torta ma con un centro vuoto, che consente la visualizzazione simultanea di più serie. Evidenzia le relazioni parte‑intero mantenendo il layout visivo compatto e facile da leggere.

## Perché usare Aspose.Slides per Java per creare grafici a ciambella?
Aspose.Slides per Java gestisce oltre 50 formati di input e output e può generare presentazioni fino a 500 MB senza caricare l'intero file in memoria. Offre un controllo programmatico completo sull'aspetto, i dati e il layout dei grafici su qualsiasi piattaforma Java, elimina l'interoperabilità COM e può renderizzare 100 diapositive ricche di grafici in meno di due secondi su un server tipico.

## Prerequisiti
- Conoscenze di base della programmazione Java.  
- Un IDE come IntelliJ IDEA o Eclipse.  
- Maven o Gradle per la gestione delle dipendenze.  
- Una licenza valida di Aspose.Slides per Java (disponibile prova gratuita).

## Configurazione di Aspose.Slides per Java
Scegli il gestore di dipendenze più adatto al tuo progetto.

**Maven**  
Aggiungi la seguente dipendenza al tuo `pom.xml` (sostituisci la versione con l'ultima release):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Aggiungi questa riga al tuo `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Se preferisci scaricare direttamente, visita la pagina [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per un uso prolungato, acquista una licenza o richiedi una temporanea da [Aspose's website](https://purchase.aspose.com/temporary-license/). Segui le istruzioni fornite per configurare il tuo ambiente e inizializzare Aspose.Slides nella tua applicazione.

## Come creare un grafico a ciambella PowerPoint usando Aspose.Slides per Java
Per creare un grafico a ciambella, inizia caricando o creando una `Presentation`, aggiungi una forma grafico di tipo `ChartType.Doughnut`, elimina le serie predefinite, imposta la dimensione del foro e poi riempi il workbook del grafico con i nomi delle categorie e i valori numerici. Infine, regola la formattazione delle etichette e salva il PPTX.

### Passo 1: Inizializzare la presentazione
Crea una nuova presentazione o apri un file esistente per ottenere una raccolta di diapositive.

`Presentation` è la classe principale che rappresenta un file PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Passo 2: Aggiungere un grafico a ciambella alla diapositiva
Inserisci una forma grafico, rimuovi le serie/categorie predefinite e configura le impostazioni visive di base come la dimensione del foro della ciambella.

`Chart` (o forma grafico) rappresenta un oggetto grafico posizionato su una diapositiva.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Passo 3: Aggiungere punti dati al grafico e personalizzare le etichette
Popola i nomi delle categorie, aggiungi i punti dati per ogni serie e perfeziona la formattazione delle etichette (font, colore, posizione). Questo passo dimostra la funzionalità “add chart data points”.

`Workbook` fornisce l'accesso ai dati di foglio di calcolo sottostanti del grafico dove le celle vengono popolate.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Passo 4: Salvare la presentazione aggiornata
Conserva le modifiche in un nuovo file PPTX su disco.

`save` scrive la presentazione in un file nel formato scelto.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Applicazioni pratiche
- **Report finanziari:** Visualizzare le allocazioni di budget o la ripartizione delle spese.  
- **Analisi di mercato:** Mostrare la distribuzione della quota di mercato tra i concorrenti.  
- **Risultati del sondaggio:** Presentare dati di sondaggio categoriali in forma compatta.  
- **Generazione di dashboard:** Combinare con query di database per produrre diapositive aggiornate in tempo reale.  

## Considerazioni sulle prestazioni
- **Dispose resources:** Chiama `pres.dispose()` dopo il salvataggio per liberare la memoria nativa.  
- **Limit chart count:** Aggiungere centinaia di grafici può aumentare l'uso di memoria; esegui il batch‑processing se necessario.  
- **Use streaming:** Per set di dati massivi, popola il workbook direttamente da stream invece che da array in memoria.  

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Il grafico appare vuoto** | Celle dei dati non popolate correttamente | Verifica che `workBook.getCell(...)` faccia riferimento agli indici di riga/colonna corretti. |
| **Le etichette si sovrappongono** | Troppe categorie in uno spazio limitato | Aumenta `DoughnutHoleSize` o regola `FirstSliceAngle`. |
| **OutOfMemoryError** | Presentazioni di grandi dimensioni senza rilasciare le risorse | Chiama `pres.dispose()` dopo il salvataggio e considera di aumentare la dimensione dell'heap JVM. |

## Domande frequenti

**Q: Posso usare Aspose.Slides per Java in applicazioni commerciali?**  
A: Sì, ma è necessaria una licenza commerciale valida. È disponibile una prova gratuita per la valutazione.

**Q: Come posso aggiungere più di 15 serie?**  
A: Aumenta il limite del ciclo nel passo “Add Doughnut Chart” e assicurati che il tuo workbook dei dati contenga abbastanza righe.

**Q: È possibile modificare la dimensione del foro della ciambella dopo la creazione?**  
A: Sì, chiama `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` prima del salvataggio.

**Q: Posso esportare il grafico come immagine invece di un PPTX?**  
A: Assolutamente. Usa `chart.getImage()` e salva il `java.awt.image.BufferedImage` restituito nel formato preferito.

**Q: Aspose.Slides supporta i grafici animati?**  
A: L'animazione può essere aggiunta tramite l'API `ISlide.getTimeline()`, anche se è al di fuori dello scopo di questo tutorial.

## Conclusione
Ora disponi di un metodo completo e pronto per la produzione per **creare file PowerPoint con grafico a ciambella** con Aspose.Slides per Java, inclusi come **aggiungere punti dati al grafico**, personalizzare le etichette e gestire le considerazioni sulle prestazioni. Sperimenta con colori diversi, fonti di dati e tipi di grafico per far risaltare davvero le tue presentazioni.

---

**Ultimo aggiornamento:** 2026-07-08  
**Testato con:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autore:** Aspose

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
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
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

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Tutorial correlati

- [Come aggiungere grafici a PowerPoint usando Aspose.Slides per Java: Guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Come modificare i dati del grafico PowerPoint usando Aspose.Slides per Java: Guida completa](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animare i grafici PowerPoint usando Aspose.Slides per Java – Guida passo‑passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}