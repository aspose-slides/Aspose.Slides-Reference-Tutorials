---
date: '2026-03-07'
description: Impara a creare un grafico a linee in Java usando Aspose.Slides, aggiungi
  il titolo del grafico, aggiungi le linee della griglia, formatta le etichette del
  grafico e salva presentazioni professionali.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Come creare un grafico a linee con Aspose.Slides in Java – Guida completa
url: /it/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a linee con Aspose.Slides in Java

## Come creare un grafico a linee in Java usando Aspose.Slides

### Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per una comunicazione efficace. Che tu sia un professionista aziendale o un educatore, spesso hai bisogno di **creare grafici a linee** visivi che siano sia informativi sia esteticamente gradevoli. In questo tutorial vedremo come utilizzare **Aspose.Slides for Java** per generare un grafico a linee, aggiungere il titolo del grafico, aggiungere linee di griglia, formattare le etichette del grafico e salvare il risultato come file PowerPoint.

#### Risposte rapide
- **Qual è la libreria migliore per creare grafici in Java?** Aspose.Slides for Java
- **Quale tipo di grafico è al centro di questa guida?** Grafico a linee con marcatori
- **È necessaria una licenza per eseguire l'esempio?** Una licenza temporanea gratuita funziona per la valutazione
- **Quale IDE posso usare?** Qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans
- **Come vengono formattati gli elementi del grafico?** Utilizzando chiamate API fluent per titoli, assi, linee di griglia, legende e sfondi

### Cos'è un grafico a linee e perché usare Aspose.Slides?
Un grafico a linee visualizza i punti dati collegati da linee rette, rendendolo ideale per mostrare le tendenze nel tempo. Aspose.Slides ti consente di creare e personalizzare completamente questi grafici in modo programmatico, eliminando la necessità di modificare manualmente PowerPoint.

### Prerequisiti
- **Java Development Kit (JDK) 8+** installato
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, ecc.)
- **Aspose.Slides for Java** library (added via Maven or Gradle)

#### Librerie e dipendenze richieste
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

In alternativa, scarica l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza
- Ottieni una [licenza di prova gratuita](https://purchase.aspose.com/temporary-license/) per i test.
- Acquista una licenza completa dal [sito ufficiale di Aspose](https://purchase.aspose.com/buy) per l'uso in produzione.

### Configurazione di Aspose.Slides per Java
1. **Aggiungi la dipendenza** mostrata sopra al tuo progetto.
2. **Applica la licenza** (se ne possiedi una) prima di creare qualsiasi oggetto `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Implementazione passo‑passo

### Passo 1: Creare la directory di output (create directory java)
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
*Perché è importante:* Assicurarsi che la cartella esista impedisce `FileNotFoundException` quando successivamente salvi la presentazione.

### Passo 2: Aggiungere una diapositiva e inserire un grafico a linee
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

### Passo 3: Aggiungere il titolo del grafico (add chart title)
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

### Passo 4: Formattare gli assi e aggiungere linee di griglia (add grid lines)
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
*Perché è importante:* Linee di griglia chiare ed etichette ruotate migliorano la leggibilità, soprattutto quando i punti dati sono numerosi.

### Passo 5: Personalizzare la legenda (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Passo 6: Impostare i colori di sfondo (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Passo 7: Salvare la presentazione
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Risultato:* Ora hai un file PowerPoint (`FormattedChart_out.pptx`) contenente un grafico a linee completamente formattato.

## Applicazioni pratiche
- **Report aziendali:** Mostra le performance trimestrali con linee di tendenza.
- **Diapositive educative:** Visualizza dati scientifici per le lezioni.
- **Proposte di progetto:** Evidenzia le tappe fondamentali e le previsioni.
- **Analisi di marketing:** Presenta le tendenze del ROI delle campagne.
- **Integrazione dashboard:** Esporta dati in tempo reale in PowerPoint per le riunioni con gli stakeholder.

## Considerazioni sulle prestazioni
- **Gestione della memoria:** Chiama sempre `dispose()` sull'oggetto `Presentation` per rilasciare prontamente le risorse native.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Licenza non applicata** | Carica la licenza di prova/completa prima di creare qualsiasi oggetto `Presentation`. |
| **Il grafico appare vuoto** | Verifica che la diapositiva contenga effettivamente serie di dati; aggiungi serie se necessario. |
| **File non salvato** | Assicurati che la directory di output esista (usa il passo “create directory java”). |
| **Colori non applicati** | Usa le costanti `Color` da `java.awt.Color` o `PresetColor`. |

## Domande frequenti

**Q: Posso creare altri tipi di grafico oltre ai grafici a linee?**  
A: Sì, Aspose.Slides supporta grafici a barre, a torta, a dispersione e molti altri tipi di grafico.

**Q: Come aggiungo più serie di dati al grafico a linee?**  
A: Usa `chart.getChartData().getSeries().add(...)` per inserire serie aggiuntive prima della formattazione.

**Q: È possibile esportare il grafico come immagine?**  
A: Assolutamente. Chiama `chart.getChartData().getChartDataWorkbook().save(...)` o rendi la diapositiva in un formato immagine.

**Q: È necessaria una licenza a pagamento per lo sviluppo?**  
A: Una licenza temporanea gratuita è sufficiente per la valutazione; è richiesta una licenza commerciale per le distribuzioni in produzione.

**Q: Quali versioni di Java sono supportate?**  
A: La libreria funziona con JDK 8 fino a JDK 22 (usa il classificatore appropriato, ad esempio `jdk16`). 

---

**Ultimo aggiornamento:** 2026-03-07  
**Testato con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}