---
date: '2026-08-27'
description: Scopri come aggiungere linee della griglia a un grafico in Java usando
  Aspose.Slides, formattare gli assi, i titoli e esportare un grafico a linee PowerPoint
  rifinito.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Scopri come aggiungere linee della griglia a un grafico in Java usando
  Aspose.Slides, formattare gli assi, i titoli e esportare un grafico a linee PowerPoint
  rifinito.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Come aggiungere linee della griglia a un grafico con Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Come aggiungere linee della griglia a un grafico con Aspose.Slides for Java
url: /it/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come aggiungere linee della griglia a un grafico con Aspose.Slides per Java

## Introduzione
Se hai bisogno di **aggiungere linee della griglia al grafico** in una presentazione PowerPoint in modo programmatico, Aspose.Slides per Java ti offre un'API pulita e completa. Che tu stia preparando una revisione aziendale trimestrale, una lezione accademica o una presentazione di vendita basata sui dati, puoi generare un grafico a linee, personalizzare ogni elemento visivo e salvare il risultato in pochi secondi, il tutto senza aprire manualmente PowerPoint.

## Risposte rapide
- **Quale libreria crea grafici in Java?** Aspose.Slides for Java.
- **Quale tipo di grafico copre questa guida?** Un grafico a linee con marcatori e linee della griglia.
- **È necessaria una licenza per eseguire l'esempio?** Una licenza temporanea gratuita funziona per la valutazione; è richiesta una licenza commerciale per la produzione.
- **Quale IDE posso usare?** Qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
- **Come vengono formattati gli elementi del grafico?** Utilizzando chiamate API fluent per titoli, assi, linee della griglia, legende e colori di sfondo.

## Come aggiungere linee della griglia al grafico in Java usando Aspose.Slides
Carica una nuova `Presentation`, inserisci una diapositiva, aggiungi un grafico a linee e poi abilita le linee della griglia principali sull'asse verticale – il tutto in meno di dieci righe di codice. Questa risposta diretta mostra la sequenza esatta di cui hai bisogno, così puoi copiare‑incollare e vedere immediatamente un grafico completamente formattato.

### Ancora di definizione
`Presentation` è la classe principale di Aspose.Slides che rappresenta un file PowerPoint in memoria; tutte le operazioni a livello di diapositiva partono da questo oggetto.

## Cos'è un grafico a linee e perché usare Aspose.Slides?
Un grafico a linee traccia una serie di punti dati collegati da linee rette, rendendo le tendenze nel tempo immediatamente visibili. Aspose.Slides supporta **oltre 50 tipi di grafico** e può gestire **fino a 10.000 punti dati per serie** senza rallentamenti evidenti, offrendoti prestazioni di livello enterprise per grandi set di dati.

### Ancora di definizione
`Chart` è l'oggetto di livello superiore di Aspose.Slides per qualsiasi grafico; memorizza serie, categorie e informazioni di formattazione.

## Prerequisiti
- **Java Development Kit (JDK) 8+** installato.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, ecc.).
- **Aspose.Slides for Java** libreria aggiunta tramite Maven o Gradle (vedi la sezione *aspose.slides maven dependency* di seguito).

### Dipendenza Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dipendenza Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

In alternativa, scarica l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## Acquisizione licenza (applica licenza aspose)
- Ottieni una **licenza di prova gratuita** dalla pagina [free trial license](https://purchase.aspose.com/temporary-license/) per i test.
- Acquista una licenza completa dal [sito ufficiale di Aspose](https://purchase.aspose.com/buy) per le distribuzioni in produzione.

## Configurazione di Aspose.Slides per Java
1. Aggiungi la dipendenza Maven o Gradle mostrata sopra al tuo progetto.
2. Carica il file di licenza **prima** di creare qualsiasi oggetto `Presentation` in modo che tutte le funzionalità siano sbloccate.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Implementazione passo‑passo

### Passo 1: crea la directory di output (crea directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Perché è importante:* Assicurarsi che la cartella esista evita `FileNotFoundException` quando si salva successivamente la presentazione.

### Passo 2: aggiungi una diapositiva e inserisci un grafico a linee
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Spiegazione:* Questo crea una nuova diapositiva e posiziona un **grafico a linee con marcatori** alle coordinate specificate.

### Passo 3: aggiungi il titolo del grafico (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*Suggerimento:* Usare un titolo in grassetto e grigio rende il grafico immediatamente riconoscibile.

### Passo 4: formatta gli assi e aggiungi linee della griglia (add grid lines)
#### Formattazione asse verticale
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Perché è importante:* Linee della griglia chiare e etichette ruotate migliorano la leggibilità, soprattutto quando i punti dati sono numerosi.

#### Formattazione asse orizzontale
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Passo 5: personalizza la legenda (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Passo 6: imposta i colori di sfondo (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Passo 7: salva la presentazione
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Risultato:* Ora hai un file PowerPoint (`FormattedChart_out.pptx`) contenente un grafico a linee completamente formattato.

## Applicazioni pratiche (generate line chart powerpoint)
- **Report aziendali:** Mostra le tendenze dei ricavi trimestrali con linee della griglia nitide.
- **Lezioni accademiche:** Visualizza i dati sperimentali su più sessioni.
- **Proposte di progetto:** Evidenzia i progressi delle tappe e le curve di previsione.
- **Analisi di marketing:** Presenta le tendenze del ROI della campagna affiancate ai dati dei concorrenti.
- **Integrazione dashboard:** Esporta le analisi in tempo reale in PowerPoint per le riunioni con gli stakeholder.

## Considerazioni sulle prestazioni
- **Gestione della memoria:** Chiama `presentation.dispose()` dopo il salvataggio per rilasciare rapidamente le risorse native.
- **Grandi set di dati:** Aspose.Slides elabora grafici con migliaia di punti usando lo streaming, mantenendo l'uso di memoria sotto i 100 MB su un server tipico.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Licenza non applicata** | Carica la licenza di prova o completa **prima** di istanziare qualsiasi oggetto `Presentation`. |
| **Il grafico appare vuoto** | Verifica che la diapositiva contenga almeno una serie di dati; aggiungi serie tramite `chart.getChartData().getSeries().add(...)` se necessario. |
| **File non salvato** | Assicurati che la directory di output esista (vedi Passo 1). |
| **Colori non applicati** | Usa le costanti `java.awt.Color` o l'enumerazione `PresetColor` per una resa dei colori affidabile. |

## Domande frequenti

**Q: Posso creare altri tipi di grafico oltre ai grafici a linee?**  
A: Sì, Aspose.Slides supporta grafici a barre, a torta, a dispersione, radar e più di 50 tipi di grafico aggiuntivi.

**Q: Come aggiungo più serie di dati al grafico a linee?**  
A: Usa `chart.getChartData().getSeries().add(...)` per inserire serie aggiuntive prima di applicare la formattazione.

**Q: È possibile esportare il grafico come immagine?**  
A: Assolutamente. Renderizza la diapositiva in PNG, JPEG o SVG con `presentation.save("slide.png", SaveFormat.Png)`.

**Q: È necessaria una licenza a pagamento per lo sviluppo?**  
A: Una licenza temporanea gratuita è sufficiente per la valutazione; è necessaria una licenza commerciale per l'uso in produzione.

**Q: Quali versioni di Java sono supportate?**  
A: La libreria funziona con JDK 8 fino a JDK 22; seleziona il classificatore appropriato (ad es., `jdk16`) quando aggiungi la dipendenza Maven/Gradle.

---

**Ultimo aggiornamento:** 2026-08-27  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
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
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Tutorial correlati

- [dipendenza maven di aspose slides: aggiungi e configura i grafici nelle presentazioni usando Aspose.Slides per Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Come aggiungere un grafico a PowerPoint usando Aspose.Slides per Java: una guida passo‑passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Crea e personalizza linee di tendenza nei grafici Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}