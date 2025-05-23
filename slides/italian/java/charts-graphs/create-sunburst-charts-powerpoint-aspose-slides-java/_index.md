---
"date": "2025-04-17"
"description": "Scopri come creare e personalizzare grafici a raggiera in PowerPoint con Aspose.Slides per Java. Questa guida dettagliata illustra la configurazione, la personalizzazione e le applicazioni pratiche."
"title": "Crea e personalizza grafici a raggiera in PowerPoint utilizzando Aspose.Slides per Java"
"url": "/it/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e personalizza grafici a raggiera in PowerPoint utilizzando Aspose.Slides per Java

## Introduzione

Creare presentazioni accattivanti spesso implica l'utilizzo di grafici di grande impatto visivo che trasmettano i dati in modo efficace. Uno di questi grafici è il grafico a raggiera, che offre un modo unico per rappresentare i dati gerarchici con il suo layout radiale. Tuttavia, aggiungere e personalizzare questi grafici può essere un compito arduo senza gli strumenti giusti. Questa guida vi guiderà nella creazione e modifica di grafici a raggiera nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java.

**Cosa imparerai:**
- Impostazione dell'ambiente per Aspose.Slides
- Creazione di una nuova presentazione con un grafico a raggiera
- Personalizzazione dei punti dati all'interno del grafico
- Applicazioni pratiche di queste competenze

Vediamo come semplificare questo processo utilizzando Aspose.Slides per Java.

## Prerequisiti

Prima di iniziare, assicurati che il tuo ambiente di sviluppo sia pronto. Avrai bisogno di:
- **Kit di sviluppo Java (JDK)** versione 16 o superiore
- UN **Ambiente di sviluppo integrato (IDE)** come IntelliJ IDEA o Eclipse
- Conoscenza di base di **Giava** e presentazioni PowerPoint

## Impostazione di Aspose.Slides per Java

### Dipendenza Maven

Per includere Aspose.Slides nel tuo progetto, aggiungi la seguente dipendenza al tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dipendenza da Gradle

Se stai utilizzando Gradle, includi quanto segue nel tuo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto

In alternativa, scaricare l'ultimo JAR da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza

Per utilizzare Aspose.Slides senza limitazioni di valutazione:
- **Prova gratuita:** Inizia con una licenza temporanea per esplorare tutte le funzionalità.
- **Licenza temporanea:** Richiedi una licenza temporanea su [Sito web di Aspose](https://purchase.aspose.com/temporary-license).
- **Acquistare:** Per i progetti in corso, valuta la possibilità di acquistare un abbonamento.

### Inizializzazione di base

Ecco come puoi inizializzare Aspose.Slides nella tua applicazione Java:
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Inizializza Aspose.Slides con una licenza, se disponibile
        Presentation pres = new Presentation();
        try {
            // Il tuo codice qui...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guida all'implementazione

### Crea una presentazione e aggiungi un grafico a raggiera

#### Panoramica

Questa funzionalità illustra come creare una presentazione PowerPoint da zero e aggiungere un grafico a raggiera.

#### Passaggi:
##### Passaggio 1: inizializzare la presentazione
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Sostituisci con il tuo percorso
```

##### Passaggio 2: aggiungere il grafico Sunburst
Aggiungere un grafico a raggiera alla prima diapositiva nella posizione (100, 100) con dimensione (450x400).
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### Passaggio 3: salva la presentazione
Salva la presentazione per assicurarti che tutte le modifiche vengano salvate.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modifica i punti dati nel grafico

#### Panoramica
Scopri come modificare i punti dati, comprese etichette e colori, in un grafico a raggiera.

#### Passaggi:
##### Passaggio 1: accedere alla raccolta di punti dati
Accedi alla raccolta di punti dati della prima serie dal grafico.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### Passaggio 2: mostrare il valore per un punto dati specifico
Modifica l'etichetta per mostrare i valori a un livello specifico.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### Passaggio 3: modificare i formati delle etichette
Regola le impostazioni delle etichette, come la visibilità del nome della categoria e il colore del testo.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### Passaggio 4: imposta il colore di riempimento per i punti dati
Personalizza il colore di riempimento di punti dati specifici.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### Passaggio 5: salvare la presentazione modificata
Salva sempre le modifiche per finalizzarle.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Applicazioni pratiche

1. **Analisi aziendale:** Utilizza i grafici sunburst per visualizzare gerarchie di dati complesse, come i dati di vendita per regione e categoria.
2. **Gestione del progetto:** Visualizza le attività del progetto suddivise in sottoattività utilizzando un grafico radiale per una facile visualizzazione.
3. **Istruzione:** Rappresentare i moduli del corso e le rispettive lezioni in presentazioni didattiche.

## Considerazioni sulle prestazioni

- **Ottimizzare l'utilizzo delle risorse:** Assicurati che la tua applicazione gestisca in modo efficiente la memoria, soprattutto quando si trattano grandi set di dati o più grafici.
- **Gestione della memoria Java:** Per evitare perdite di memoria, adottare le migliori pratiche, ad esempio smaltire tempestivamente gli oggetti.

## Conclusione

Creare e personalizzare grafici a raggiera utilizzando Aspose.Slides per Java è un modo efficace per migliorare le tue presentazioni. Seguendo questa guida, hai appreso le nozioni fondamentali per configurare l'ambiente, implementare le funzionalità dei grafici e modificare i punti dati in modo efficace.

**Prossimi passi:**
- Scopri altri tipi di grafici disponibili in Aspose.Slides.
- Sperimenta diverse opzioni di personalizzazione per i tuoi grafici.

**Invito all'azione:** Prova a implementare queste soluzioni nel tuo prossimo progetto di presentazione per vedere come possono migliorare i tuoi sforzi di visualizzazione dei dati!

## Sezione FAQ

1. **Cos'è un grafico a raggiera?**
   - Un grafico a raggiera visualizza i dati gerarchici in modo radiale, ideale per evidenziare relazioni nidificate.
2. **Come posso installare Aspose.Slides per Java utilizzando Maven?**
   - Aggiungi la dipendenza al tuo `pom.xml` file come mostrato nella sezione di configurazione sopra.
3. **Posso modificare altri tipi di grafici con Aspose.Slides?**
   - Sì, Aspose.Slides supporta vari tipi di grafici, come grafici a colonne, a linee e a torta.
4. **Cosa devo fare se la mia presentazione non viene salvata correttamente?**
   - Assicurati che il percorso del file sia corretto e di disporre dei permessi di scrittura per la directory.
5. **Come posso ottenere ulteriore assistenza con Aspose.Slides?**
   - Visita il [Forum di Aspose](https://forum.aspose.com/c/slides/11) oppure controlla la documentazione su [Riferimento Aspose.Slides](https://reference.aspose.com/slides/java/).

## Risorse
- **Documentazione:** [Riferimento Aspose.Slides](https://reference.aspose.com/slides/java)
- **Forum:** [Forum Aspose](https://forum.aspose.com/c/slides)
- **Scarica:** [Download di Aspose.Slides](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}