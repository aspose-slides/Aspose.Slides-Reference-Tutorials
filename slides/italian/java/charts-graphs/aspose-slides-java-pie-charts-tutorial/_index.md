---
date: '2026-02-19'
description: Scopri come creare un grafico a torta in Java con Aspose.Slides, personalizzare
  i colori del grafico a torta, aggiungere serie di dati, lavorare con il foglio di
  dati del grafico e impostare l'angolo di rotazione.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Come personalizzare i colori dei grafici a torta in Java con Aspose.Slides
  – Guida completa
url: /it/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

 rows content.

Also FAQ questions and answers.

Also bullet lists.

Let's produce.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creare Grafici a Torta con Aspose.Slides per Java: Un Tutorial Completo

## Introduzione
Creare presentazioni dinamiche e visivamente accattivanti è fondamentale per trasmettere informazioni di impatto. Con Aspose.Slides per Java, puoi integrare senza sforzo grafici complessi come i grafici a torta nelle tue slide, **personalizzare i colori del grafico a torta** e migliorare la visualizzazione dei dati in modo semplice. Questa guida completa ti accompagnerà passo passo nella creazione e personalizzazione di un grafico a torta usando Aspose.Slides Java, risolvendo con facilità le comuni sfide delle presentazioni.

**Cosa Imparerai:**
- Inizializzare una presentazione e aggiungere slide.
- Creare e configurare un grafico a torta nella tua slide.
- Impostare titoli del grafico, etichette dei dati e **personalizzare i colori del grafico a torta**.
- Ottimizzare le prestazioni e gestire le risorse in modo efficace.
- Integrare Aspose.Slides nei progetti Java usando Maven o Gradle.

Iniziamo assicurandoci di avere tutti gli strumenti e le conoscenze necessarie per seguirci!

## Risposte Rapide
- **Qual è la classe principale per avviare una presentazione?** `Presentation` da `com.aspose.slides`.
- **Quale metodo aggiunge un grafico a torta a una slide?** `addChart(ChartType.Pie, …)`.
- **Come si abilitano colori diversi per ogni fetta?** Imposta `setColorVaried(true)` sul gruppo di serie.
- **È possibile ruotare il grafico a torta?** Sì, usa `setRotationAngle(double)` sull'oggetto chart.
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza Aspose.Slides per le distribuzioni commerciali.

## Cos'è “personalizzare i colori del grafico a torta”?
Personalizzare i colori del grafico a torta significa assegnare colori di riempimento distinti a ciascuna fetta della torta, migliorando la leggibilità e l'impatto visivo. In Aspose.Slides lo ottieni abilitando i colori variabili e poi impostando colori di riempimento solidi per i singoli punti dati.

## Perché usare Aspose.Slides per Java per creare grafici a torta?
- **Controllo totale** sull'aspetto del grafico senza necessità di Microsoft Office.
- **Compatibilità cross‑platform** – funziona su Windows, Linux e macOS.
- **API ricca** per il binding dei dati, lo styling e l'esportazione in PPTX, PDF o immagini.
- **Flessibilità di licenza** – inizia con una prova gratuita e passa a una licenza completa quando ti servono tutte le funzionalità.

## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere pronto quanto segue:

### Librerie, Versioni e Dipendenze Richieste
- **Aspose.Slides per Java**: versione 25.4 o successiva.
- **Java Development Kit (JDK)**: versione 16 o superiore.

### Requisiti per la Configurazione dell'Ambiente
- Un ambiente di sviluppo con Java installato e configurato.
- Un Integrated Development Environment (IDE) come IntelliJ IDEA, Eclipse o NetBeans.

### Conoscenze Preliminari
- Comprensione di base della programmazione Java.
- Familiarità con Maven o Gradle per la gestione delle dipendenze.

## Configurare Aspose.Slides per Java
Per iniziare a usare Aspose.Slides nei tuoi progetti Java, devi aggiungere la libreria come dipendenza. Ecco come fare con diversi strumenti di build:

**Maven**  
Aggiungi questo snippet al tuo file `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Inserisci quanto segue nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download Diretto**  
Se preferisci non usare uno strumento di build, scarica l'ultima release da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Passaggi per Ottenere la Licenza
- **Prova Gratuita**: Inizia con una prova gratuita per esplorare le funzionalità di Aspose.Slides.  
- **Licenza Temporanea**: Ottieni una licenza temporanea per un uso prolungato senza limitazioni.  
- **Acquisto**: Considera l'acquisto se ti serve un accesso a lungo termine.

**Inizializzazione di Base e Configurazione**  
Per cominciare a usare Aspose.Slides, inizializza il tuo progetto creando un nuovo oggetto presentation:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guida all'Implementazione
Ora suddividiamo il processo di aggiunta e personalizzazione di un grafico a torta in passaggi gestibili.

### Inizializzare Presentazione e Slide
Inizia impostando una nuova presentazione e accedendo alla prima slide. Questa sarà la tua tela per creare i grafici:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Aggiungere Grafico a Torta alla Slide
Inserisci un grafico a torta nella posizione specificata con un set di dati predefinito:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Impostare il Titolo del Grafico
Personalizza il grafico impostando e centrando il titolo:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurare le Etichette dei Dati per la Serie
Assicurati che le etichette dei dati mostrino i valori per maggiore chiarezza:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparare il Foglio Dati del Grafico
Configura il foglio dati del grafico cancellando le serie e le categorie esistenti:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Aggiungere Categorie al Grafico
Definisci le categorie per il tuo grafico a torta:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Aggiungere Serie e Popolare i Punti Dati
Crea una serie e popolala con i punti dati – è qui che **aggiungiamo la serie del grafico**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizzare i Colori e i Bordi della Serie
Migliora l'aspetto visivo impostando i colori e personalizzando i bordi – questo **personalizza i colori del grafico a torta**:
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

### Configurare Etichette Dati Personalizzate
Affina le etichette per ciascun punto dati:
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

### Impostare l'Angolo di Rotazione e Salvare la Presentazione
Completa il tuo grafico a torta **impostando l'angolo di rotazione** e salvando il file:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Problemi Comuni e Soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Le fette appaiono tutte dello stesso colore** | `setColorVaried(true)` non è stato chiamato | Assicurati di abilitare i colori variabili sul gruppo di serie. |
| **Le etichette dei dati non vengono visualizzate** | Flag `showValue` disabilitato | Chiama `setShowValue(true)` sul formato dell'etichetta appropriato. |
| **La rotazione non ha effetto** | Uso di una versione più vecchia di Aspose.Slides | Aggiorna alla versione 25.4 o successiva. |
| **Eccezione di licenza a runtime** | File di licenza mancante o non valido | Carica la licenza con `License license = new License(); license.setLicense("Aspose.Slides.lic");` prima di creare la `Presentation`. |

## Domande Frequenti

**D: Come posso ottenere una licenza Aspose.Slides per Java?**  
R: Puoi richiedere una prova gratuita dal sito Aspose, quindi acquistare una licenza permanente. Caricala a runtime come mostrato nella tabella Problemi Comuni.

**D: Posso usare questo codice con versioni JDK più vecchie?**  
R: L'API richiede JDK 16 o superiore; le versioni precedenti non sono supportate.

**D: È possibile esportare il grafico come immagine anziché PPTX?**  
R: Sì, chiama `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` dopo il rendering.

**D: Cosa succede se devo aggiungere più di una serie a un grafico a torta?**  
R: I grafici a torta mostrano tipicamente una sola serie; per più serie considera un grafico a ciambella.

**D: La libreria funziona su server Linux?**  
R: Assolutamente – Aspose.Slides per Java è indipendente dalla piattaforma e gira su qualsiasi OS con un JDK compatibile.

---

**Ultimo Aggiornamento:** 2026-02-19  
**Testato Con:** Aspose.Slides per Java 25.4 (jdk16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}