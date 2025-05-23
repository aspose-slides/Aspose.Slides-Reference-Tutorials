---
"date": "2025-04-17"
"description": "Scopri come creare e formattare grafici utilizzando Aspose.Slides per Java. Questa guida illustra la configurazione, la creazione di grafici, la formattazione e il salvataggio delle presentazioni."
"title": "Crea e formatta grafici in Java usando Aspose.Slides&#58; una guida completa"
"url": "/it/java/charts-graphs/create-format-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e formatta grafici con Aspose.Slides in Java

## Come creare e formattare grafici in Java utilizzando Aspose.Slides

### Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per una comunicazione efficace. Che tu sia un professionista o un docente, garantire che le immagini dei dati siano allo stesso tempo informative ed esteticamente gradevoli può essere una sfida. Questo tutorial ti guida nell'utilizzo di **Aspose.Slides per Java** per creare e formattare grafici nelle presentazioni PowerPoint in modo semplice.

Questa guida si concentra sulla configurazione dell'ambiente, sulla creazione di un grafico, sulla configurazione di proprietà come titoli, formattazione degli assi, linee della griglia, etichette, impostazioni della legenda e sul salvataggio della presentazione. Seguendo questo tutorial, imparerai come:
- Imposta il tuo ambiente con Aspose.Slides per Java
- Controllare e creare directory a livello di programmazione in Java
- Crea e configura un grafico utilizzando Aspose.Slides
- Formatta titoli, assi, linee della griglia, etichette, legende e sfondi dei grafici
- Salva la presentazione con i grafici formattati

Prima di iniziare a scrivere il codice, assicuriamoci che tutto sia pronto.

### Prerequisiti
Prima di iniziare, assicurati di avere:
1. **Kit di sviluppo Java (JDK)**: Assicurati che sul tuo sistema sia installato JDK 8 o versione successiva.
2. **Ambiente di sviluppo integrato (IDE)**: utilizzare qualsiasi IDE compatibile con Java come IntelliJ IDEA, Eclipse o NetBeans.
3. **Aspose.Slides per Java**:Questa libreria sarà centrale nel nostro tutorial.

#### Librerie e dipendenze richieste
Per utilizzare Aspose.Slides nel tuo progetto, aggiungilo tramite Maven o Gradle:

**Esperto**
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

In alternativa, scaricare l'ultimo JAR da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

#### Requisiti di configurazione dell'ambiente
- Installa una versione recente di JDK.
- Imposta il tuo IDE e assicurati che sia configurato per utilizzare Maven o Gradle (in base alla tua scelta).
  
### Prerequisiti di conoscenza
È richiesta una conoscenza di base della programmazione Java. La familiarità con i principi orientati agli oggetti sarà utile.

## Impostazione di Aspose.Slides per Java
Per iniziare a utilizzare Aspose.Slides, includi la libreria nel tuo progetto:
1. **Aggiungi dipendenza**: includere la dipendenza Maven o Gradle necessaria come mostrato sopra.
2. **Acquisizione della licenza**:
   - Ottieni un [licenza di prova gratuita](https://purchase.aspose.com/temporary-license/) a scopo di test.
   - Per l'uso in produzione, si consiglia di acquistare una licenza completa da [Sito ufficiale di Aspose](https://purchase.aspose.com/buy).

### Inizializzazione e configurazione di base
Per inizializzare Aspose.Slides nella tua applicazione Java:
```java
import com.aspose.slides.Presentation;
// Inizializza l'oggetto Presentazione
Presentation pres = new Presentation();
```

## Guida all'implementazione
Questa sezione illustra ogni funzionalità passo dopo passo, utilizzando sottotitoli logici per maggiore chiarezza.

### Impostazione della directory
**Panoramica**: Prima di salvare i grafici in una presentazione, assicurati che la struttura delle directory sia corretta.

#### Controlla e crea directory
```java
import java.io.File;
// Definire la directory di destinazione
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Controlla se la directory esiste; creala in caso contrario
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Creare directory in modo ricorsivo
}
```
**Spiegazione**: Questo frammento verifica se una directory specificata esiste. In caso contrario, crea le cartelle necessarie.

### Creazione e configurazione del grafico
**Panoramica**: Creeremo un grafico in PowerPoint utilizzando Aspose.Slides, ne personalizzeremo l'aspetto e lo salveremo in un file.

#### Creazione di una diapositiva di presentazione con un grafico
```java
import com.aspose.slides.*;
// Crea una nuova presentazione
Presentation pres = new Presentation();
try {
    // Accedi alla prima diapositiva
    ISlide slide = pres.getSlides().get_Item(0);

    // Aggiungere un grafico alla diapositiva
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
**Spiegazione**:Inizializziamo una nuova presentazione e aggiungiamo un grafico a linee con marcatori in corrispondenza di coordinate specifiche.

#### Imposta il titolo del grafico
```java
// Abilita e formatta il titolo
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
**Spiegazione**: Questo codice imposta e assegna uno stile al titolo del grafico. La personalizzazione delle proprietà del testo ne migliora la leggibilità.

#### Formato assi
##### Formattazione dell'asse verticale
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Formattare le linee principali della griglia
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configurare le proprietà dell'asse
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```
**Spiegazione**:Personalizziamo le linee della griglia dell'asse verticale e impostiamo la formattazione numerica per maggiore chiarezza.

##### Formattazione dell'asse orizzontale
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Formattare le linee principali della griglia
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Imposta le posizioni e le rotazioni delle etichette
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
**Spiegazione**: L'asse orizzontale è formattato in modo simile, con ulteriori regolazioni per il posizionamento dell'etichetta.

#### Personalizza la legenda
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Impedisci la sovrapposizione con l'area del grafico
chart.getLegend().setOverlay(true);
```
**Spiegazione**: L'impostazione delle proprietà della legenda garantisce chiarezza ed evita confusione visiva.

#### Configura gli sfondi
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```
**Spiegazione**: I colori di sfondo sono impostati per un effetto estetico gradevole, migliorando l'aspetto generale del grafico.

### Salvataggio della presentazione
```java
// Salva la presentazione su disco
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Pulisci le risorse
}
```
**Spiegazione**: Ciò garantisce che tutte le modifiche vengano salvate e che le risorse vengano gestite correttamente.

## Applicazioni pratiche
1. **Rapporti aziendali**: Crea report dettagliati con grafici formattati per presentare i risultati trimestrali.
2. **Materiali didattici**: Sviluppa presentazioni coinvolgenti per gli studenti utilizzando elementi visivi basati sui dati.
3. **Proposte di progetto**: Migliora le proposte integrando grafici visivamente accattivanti che evidenziano le metriche chiave.
4. **Analisi di marketing**: Utilizzare grafici nei materiali di marketing per illustrare in modo efficace le tendenze e i risultati delle campagne.
5. **Integrazione della dashboard**: Incorpora grafici nei dashboard per visualizzare i dati in tempo reale.

## Considerazioni sulle prestazioni
- **Gestione della memoria**: Eliminare sempre gli oggetti Presentazione per liberare rapidamente le risorse.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}