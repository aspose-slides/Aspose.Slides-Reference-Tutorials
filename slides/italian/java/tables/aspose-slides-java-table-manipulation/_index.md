---
"date": "2025-04-18"
"description": "Impara a creare e manipolare tabelle nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Arricchisci le tue diapositive con tabelle dinamiche e ricche di dati senza sforzo."
"title": "Manipolazione delle tabelle master nelle presentazioni Java con Aspose.Slides per Java"
"url": "/it/java/tables/aspose-slides-java-table-manipulation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Manipolazione delle tabelle master nelle presentazioni Java con Aspose.Slides per Java
## Come creare e manipolare tabelle nelle presentazioni utilizzando Aspose.Slides per Java
Nel frenetico mondo digitale di oggi, creare presentazioni dinamiche è più cruciale che mai. Con Aspose.Slides per Java, puoi creare e manipolare tabelle all'interno delle tue diapositive di PowerPoint in modo semplice e intuitivo, utilizzando solo poche righe di codice. Questo tutorial ti guiderà attraverso la configurazione di Aspose.Slides per Java e l'implementazione di diverse funzionalità per migliorare le tue presentazioni.

### Introduzione
Hai mai avuto difficoltà a creare tabelle nelle presentazioni di PowerPoint che fossero visivamente accattivanti e ricche di dati? Con Aspose.Slides per Java, queste sfide diventano un ricordo del passato. Questa potente libreria ti consente di creare istanze di presentazione, accedere alle diapositive, definire le dimensioni delle tabelle, aggiungere e personalizzare tabelle, impostare il testo all'interno delle celle, modificare le cornici di testo, allineare il testo verticalmente e salvare il tuo lavoro in modo efficiente.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per Java
- Creazione di una nuova istanza di Presentazione
- Accesso alle diapositive in una presentazione
- Definizione delle dimensioni della tabella e aggiunta alle diapositive
- Personalizzazione delle tabelle mediante l'impostazione del testo delle celle e la modifica delle cornici di testo
- Allineamento verticale del testo all'interno delle celle della tabella
- Salvataggio delle presentazioni modificate
Cominciamo ad analizzare i prerequisiti richiesti per questo tutorial.

### Prerequisiti
Prima di immergerti nell'implementazione, assicurati di avere quanto segue:
- **Librerie e dipendenze:** Aspose.Slides per Java versione 25.4 o successiva.
- **Configurazione dell'ambiente:** Un JDK compatibile (preferibilmente JDK16 come nei nostri esempi).
- **Prerequisiti di conoscenza:** Conoscenza di base della programmazione Java e familiarità con gli strumenti di compilazione Maven o Gradle.

### Impostazione di Aspose.Slides per Java
Per iniziare, devi aggiungere le dipendenze necessarie al tuo progetto. Ecco come fare:

#### Esperto
Aggiungi la seguente dipendenza nel tuo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Per gli utenti di Gradle, includi questo nel tuo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
In alternativa, puoi scaricare l'ultimo JAR da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

**Acquisizione della licenza:** Aspose offre una licenza di prova gratuita per esplorare le sue funzionalità. È possibile richiedere una licenza temporanea o acquistarne una, se necessario.

### Inizializzazione di base
Dopo aver impostato il progetto, inizializzalo `Presentation` classe come mostrato di seguito:
```java
import com.aspose.slides.Presentation;
// Crea un'istanza di Presentazione
Presentation presentation = new Presentation();
try {
    // Il tuo codice qui
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Guida all'implementazione
Ora che il tuo ambiente è pronto, approfondiamo l'implementazione. Per maggiore chiarezza, la suddivideremo per funzionalità.

### Creare un'istanza di presentazione
Questa funzione dimostra l'inizializzazione di un `Presentation` esempio:
```java
import com.aspose.slides.Presentation;
// Inizializza una nuova presentazione
global slide;
presentation = new Presentation();
try {
    // Codice per manipolare diapositive e forme
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Scopo:** Assicura una corretta gestione delle risorse con l' `dispose()` metodo nel `finally` bloccare.

### Ottieni una diapositiva dalla presentazione
L'accesso alla prima diapositiva è semplice:
```java
import com.aspose.slides.Presentation;
global slide;
presentation = new Presentation();
try {
    // Accedi alla prima diapositiva
    ISlide slide = presentation.getSlides().get_Item(0);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Spiegazione:** `get_Item(0)` recupera la prima diapositiva, indicizzata a 0.

### Definisci le dimensioni della tabella e aggiungi la tabella alla diapositiva
Definisci la larghezza delle colonne e l'altezza delle righe prima di aggiungere una tabella:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120}; // Larghezze delle colonne
double[] dblRows = {100, 100, 100, 100}; // Altezze delle file

    // Aggiungi una tabella alla diapositiva nella posizione (x: 100, y: 50)
    ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Configurazione chiave:** Specificare le dimensioni utilizzando matrici per colonne e righe.

### Imposta il testo nelle celle della tabella
Personalizza la tua tabella impostando il testo all'interno delle celle:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // Imposta testo per celle specifiche
    tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Nota:** Utilizzo `getTextFrame().setText()` per impostare il contenuto della cella.

### Accesso e modifica della cornice di testo in una cella
L'accesso alle cornici di testo consente un'ulteriore personalizzazione:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // Accedi alla cornice di testo e modifica il contenuto
    ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);

portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Spiegazione:** Modifica il testo e le sue proprietà, come il colore, utilizzando `Portion` oggetti.

### Allinea verticalmente il testo in una cella
L'allineamento verticale del testo migliora la leggibilità:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // Allinea il testo verticalmente
    ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center); // Allineamento centrale
cell.setTextVerticalType(TextVerticalType.Vertical270);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Nota:** Utilizzo `setTextVerticalType()` per allineare verticalmente il testo.

### Salva la presentazione
Infine, salva la presentazione modificata:
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    // Codice per la manipolazione delle tabelle
    
    // Salva la presentazione come file PPTX
    presentation.save("ModifiedPresentation.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**Spiegazione:** IL `save()` Il metodo scrive le modifiche sul disco nel formato specificato.

### Conclusione
Ora hai imparato come configurare Aspose.Slides per Java, creare e manipolare tabelle all'interno di una diapositiva di PowerPoint, personalizzare il testo delle celle, allineare il testo verticalmente e salvare la presentazione. Padroneggiando queste competenze, potrai migliorare le tue presentazioni con tabelle dinamiche e ricche di dati senza sforzo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}