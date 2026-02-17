---
date: '2026-02-17'
description: Scopri come creare un grafico a ciambella in PowerPoint usando Aspose.Slides
  per Java e aggiungere i punti dati del grafico programmaticamente. Segui passaggi
  semplici ed esempi di codice.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Crea un grafico a ciambella in PowerPoint con Aspose.Slides per Java
url: /it/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea un grafico a ciambella PowerPoint con Aspose.Slides per Java

## Introduzione
Creare presentazioni accattivanti spesso richiede più di semplici testi e immagini; i grafici possono migliorare notevolmente la narrazione visualizzando i dati in modo efficace. Tuttavia, molti sviluppatori hanno difficoltà a integrare funzionalità di grafico dinamico nei file PowerPoint in modo programmatico. Questo tutorial dimostra come **creare un grafico a ciambella PowerPoint** usando Aspose.Slides per Java—uno strumento potente che combina flessibilità e facilità d'uso.

**Ciò che imparerai:**
- Come inizializzare una presentazione usando Aspose.Slides per Java
- Guida passo‑passo per aggiungere un grafico a ciambella alle tue diapositive
- Configurare i punti dati e personalizzare le proprietà delle etichette
- Salvare la presentazione modificata con alta fedeltà

Esploriamo come puoi sfruttare queste funzionalità per migliorare le tue presentazioni. Prima di iniziare, assicurati di conoscere i concetti di base della programmazione Java.

## Risposte rapide
- **Quale libreria crea un grafico a ciambella PowerPoint?** Aspose.Slides for Java
- **Posso aggiungere punti dati al grafico programmaticamente?** Sì, usando l'API del grafico
- **È necessaria una licenza per la produzione?** È richiesta una licenza valida di Aspose.Slides
- **Quali versioni di Java sono supportate?** Java 8 e successive (mostrato il classificatore JDK 16)
- **Quante serie posso aggiungere?** L'esempio aggiunge fino a 15 serie, ma è possibile regolare secondo necessità

## Che cos'è un grafico a ciambella in PowerPoint?
Un grafico a ciambella è una variante del grafico a torta con un centro vuoto, che consente di visualizzare più serie di dati in modo compatto e accattivante. È ideale per mostrare relazioni parte‑intero mantenendo un design pulito.

## Perché usare Aspose.Slides per Java per creare grafici a ciambella?
- **Controllo completo** sull'aspetto del grafico, dati e layout senza aprire PowerPoint
- **Nessuna interop COM** – funziona su qualsiasi piattaforma che supporta Java
- **Alte prestazioni** per generare deck di grandi dimensioni o integrare con servizi web
- **Ricca personalizzazione** come esplosione, dimensione del buco, angoli delle fette e formattazione delle etichette

## Prerequisiti
- Conoscenza di base della programmazione Java.
- Un IDE come IntelliJ IDEA o Eclipse.
- Maven o Gradle per la gestione delle dipendenze.
- Una licenza valida di Aspose.Slides per Java (disponibile prova gratuita).

## Configurazione di Aspose.Slides per Java
Scegli il gestore di dipendenze che si adatta al tuo progetto.

**Maven**
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

Se preferisci scaricare direttamente, visita la pagina [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) .

### Acquisizione della licenza
Puoi iniziare con una prova gratuita per esplorare le funzionalità di Aspose.Slides. Per un utilizzo prolungato, acquista una licenza o richiedi una licenza temporanea dal [sito di Aspose](https://purchase.aspose.com/temporary-license/). Segui le istruzioni fornite per configurare l'ambiente e inizializzare Aspose.Slides nella tua applicazione.

## Come creare un grafico a ciambella PowerPoint usando Aspose.Slides per Java
Di seguito è una guida completa passo‑passo. Ogni blocco di codice è spiegato subito prima, così sai esattamente cosa sta succedendo.

### Passo 1: Inizializzare la presentazione
Per prima cosa, carica un PPTX esistente o creane uno nuovo. Questo prepara la raccolta di diapositive per ulteriori modifiche.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Passo 2: Aggiungere un grafico a ciambella alla diapositiva
Aggiungiamo la forma del grafico, cancelliamo eventuali serie/categorie predefinite e impostiamo le proprietà visive di base.

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

### Passo 3: Aggiungere punti dati al grafico e personalizzare le etichette
Qui popoliamo le categorie, aggiungiamo i punti dati per ogni serie e perfezioniamo l'aspetto delle etichette. È qui che entra in gioco la parola chiave **add chart data points**.

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

### Passo 4: Salvare la presentazione aggiornata
Infine, persisti le modifiche in un nuovo file PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Applicazioni pratiche
- **Report finanziari:** Visualizzare le allocazioni di budget o la ripartizione delle spese.
- **Analisi di mercato:** Mostrare la distribuzione della quota di mercato tra i concorrenti.
- **Risultati dei sondaggi:** Presentare dati categoriali del sondaggio in forma compatta.
- **Generazione di dashboard:** Combinare con query di database per generare diapositive aggiornate in tempo reale.

## Considerazioni sulle prestazioni
- **Rilasciare le risorse**: Chiamare `pres.dispose()` al termine per liberare la memoria nativa.
- **Limitare il numero di grafici**: Aggiungere centinaia di grafici può aumentare l'uso della memoria; elaborare in batch se necessario.
- **Usare lo streaming**: Per set di dati massivi, popolare il workbook direttamente da stream invece che da array in memoria.

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Il grafico appare vuoto** | Data cells not populated correctly | Verify that `workBook.getCell(...)` references the correct row/column indices. |
| **Le etichette si sovrappongono** | Too many categories in limited space | Increase `DoughnutHoleSize` or adjust `FirstSliceAngle`. |
| **OutOfMemoryError** | Large presentations without disposing | Call `pres.dispose()` after saving and consider increasing JVM heap size. |

## Domande frequenti

**Q: Posso usare Aspose.Slides per Java in applicazioni commerciali?**  
A: Sì, ma è necessaria una licenza commerciale valida. È disponibile una prova gratuita per la valutazione.

**Q: Come aggiungo più di 15 serie?**  
A: Aumenta il limite del ciclo nel passo “Add Doughnut Chart” e assicurati che il tuo workbook di dati abbia sufficienti righe.

**Q: È possibile modificare la dimensione del buco della ciambella dopo la creazione?**  
A: Sì, chiama `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` in qualsiasi momento prima del salvataggio.

**Q: Posso esportare il grafico come immagine invece di un PPTX?**  
A: Assolutamente. Usa `chart.getImage()` e salva il `java.awt.image.BufferedImage` restituito nel formato preferito.

**Q: Aspose.Slides supporta grafici animati?**  
A: L'animazione può essere aggiunta tramite l'API `ISlide.getTimeline()`, anche se è al di fuori dello scopo di questo tutorial.

## Conclusione
Ora disponi di un metodo completo e pronto per la produzione per **creare un grafico a ciambella PowerPoint** con Aspose.Slides per Java, inclusa la possibilità di **add chart data points**, personalizzare le etichette e gestire le considerazioni sulle prestazioni. Sperimenta con colori diversi, fonti di dati e tipi di grafico per far risaltare davvero le tue presentazioni.

---

**Ultimo aggiornamento:** 2026-02-17  
**Testato con:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}