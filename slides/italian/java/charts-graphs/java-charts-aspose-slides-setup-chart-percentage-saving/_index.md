---
"date": "2025-04-17"
"description": "Scopri come creare, personalizzare e salvare grafici con etichette percentuali nelle presentazioni Java utilizzando Aspose.Slides. Migliora le tue capacità di presentazione oggi stesso!"
"title": "Crea e personalizza grafici nelle presentazioni Java utilizzando Aspose.Slides"
"url": "/it/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e personalizza grafici nelle presentazioni Java utilizzando Aspose.Slides

## Introduzione
Creare presentazioni accattivanti spesso non richiede solo testo: richiede grafici dinamici che trasmettano le informazioni in modo efficace. Se desideri migliorare le tue presentazioni basate su Java con funzionalità avanzate per i grafici utilizzando Aspose.Slides, questo tutorial fa al caso tuo. Ti guideremo nella creazione di una presentazione, nell'aggiunta e nella configurazione di grafici, nel calcolo dei totali, nella visualizzazione delle etichette percentuali e nel salvataggio del tuo lavoro, il tutto in pochi semplici passaggi.

**Cosa imparerai:**
- Come creare e personalizzare presentazioni con grafici utilizzando Aspose.Slides per Java
- Calcolo dei totali delle categorie nei grafici
- Visualizzazione dei dati come etichette percentuali sui grafici
- Salvataggio delle presentazioni con funzionalità di grafici migliorate

Analizziamo ora i prerequisiti necessari prima di iniziare.

## Prerequisiti
Per seguire questo tutorial, assicurati di avere quanto segue:

- **Kit di sviluppo Java (JDK)**: Versione 8 o superiore.
- **IDE**: Come IntelliJ IDEA, Eclipse o qualsiasi IDE supportato da Java.
- **Libreria Aspose.Slides per Java**:Questo è fondamentale per gestire le funzionalità di presentazione.

### Librerie e versioni richieste
Avrai bisogno di Aspose.Slides per Java. Ecco come includerlo nel tuo progetto:

**Esperto:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, puoi scaricare direttamente l'ultima versione da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Configurazione dell'ambiente
Assicurati che il tuo ambiente di sviluppo sia configurato per utilizzare JDK 8 o versione successiva e che il tuo IDE sia impostato per gestire le dipendenze tramite Maven o Gradle.

**Acquisizione della licenza:**
- **Prova gratuita**:Accedi alle funzionalità di base per scopi di test.
- **Licenza temporanea**: Testa le funzionalità avanzate senza limitazioni di valutazione.
- **Acquistare**: Per un utilizzo commerciale a lungo termine, si consiglia di acquistare una licenza.

## Impostazione di Aspose.Slides per Java
Inizia configurando la libreria Aspose.Slides nel tuo progetto Java. Ecco come inizializzarla e configurarla:

1. Aggiungere la dipendenza tramite Maven o Gradle come mostrato sopra.
2. Importare i pacchetti Aspose.Slides necessari:
   ```java
   import com.aspose.slides.*;
   ```

3. Inizializza un nuovo `Presentation` esempio:
   ```java
   Presentation presentation = new Presentation();
   ```

Questa configurazione ti consentirà di iniziare a creare presentazioni in modo programmatico.

## Guida all'implementazione

### Crea e personalizza grafici nella tua presentazione

#### Panoramica
Per creare un grafico è necessario inizializzare la presentazione, accedere alle diapositive e aggiungere un grafico con attributi specifici come tipo, posizione e dimensione.

**Passaggi:**
1. **Crea istanza di presentazione**: Inizia creando un'istanza di `Presentation` classe.
2. **Diapositiva di accesso**: Recupera la prima diapositiva utilizzando `get_Item(0)`.
3. **Aggiungi grafico**: Utilizzo `addChart()` per aggiungere un grafico a colonne impilate in base a coordinate specificate e con dimensioni definite.

```java
// Funzionalità: creare una presentazione con grafico
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Calcola i totali per le categorie

#### Panoramica
Per calcolare i totali delle categorie è necessario scorrere ogni serie del grafico per sommare i valori per categoria.

**Passaggi:**
1. **Inizializza array**: Crea un array per contenere i valori totali.
2. **Iterare attraverso categorie e serie**: Utilizzare cicli annidati per accumulare i totali per ciascuna categoria di tutte le serie.

```java
// Funzionalità: calcola i totali per le categorie in un grafico
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Visualizzare i dati come etichette percentuali su un grafico

#### Panoramica
Questa funzionalità si concentra sulla configurazione delle etichette dati per visualizzare i valori come percentuali, garantendo chiarezza nella visualizzazione.

**Passaggi:**
1. **Configurare le etichette delle serie**: Imposta le proprietà dell'etichetta, come la dimensione del carattere e la visibilità delle chiavi della legenda.
2. **Calcola le percentuali**: Calcola la percentuale per ciascun punto dati in base al valore totale della categoria.
3. **Imposta il testo dell'etichetta**: Formatta le etichette per mostrare le percentuali con due cifre decimali.

```java
// Funzionalità: visualizza i dati come etichette percentuali su un grafico
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Salva presentazione con grafico

#### Panoramica
Infine, salva la presentazione in un percorso specificato in formato PPTX.

**Passaggi:**
1. **Metodo di salvataggio**: Usa il `save()` metodo sul `Presentation` esempio.
2. **Smaltire le risorse**: Assicurarsi che le risorse vengano rilasciate dopo il salvataggio.

```java
// Funzionalità: salva la presentazione con il grafico
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Applicazioni pratiche

1. **Rendicontazione finanziaria**: Utilizza grafici per visualizzare le percentuali di crescita dei ricavi nei vari reparti.
2. **Analisi dei dati di vendita**: Visualizza i dati di vendita per regione con etichette percentuali per informazioni più chiare.
3. **Presentazioni educative**: Migliora le presentazioni accademiche con statistiche visive.
4. **Campagne di marketing**: Visualizza le metriche delle prestazioni della campagna come elementi visivi accattivanti.
5. **Riunioni di strategia aziendale**: Utilizzare grafici per trasmettere dati complessi nelle discussioni sulla pianificazione strategica.

## Considerazioni sulle prestazioni
- **Gestione della memoria**: Smaltire `Presentation` oggetti tempestivamente per liberare risorse.
- **Ottimizza il caricamento del grafico**: Se possibile, caricare nella memoria solo gli elementi essenziali del grafico.
- **Elaborazione batch**: Quando si elaborano più presentazioni, è consigliabile gestirle in batch per gestire in modo efficace il consumo delle risorse.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}