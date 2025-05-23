---
"date": "2025-04-17"
"description": "Impara a creare ed esportare grafici utilizzando Aspose.Slides in Java. Padroneggia le tecniche di visualizzazione dei dati con guide dettagliate ed esempi di codice."
"title": "Aspose.Slides Java&#58; creazione ed esportazione di grafici per la visualizzazione dei dati"
"url": "/it/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creazione ed esportazione di grafici utilizzando Aspose.Slides Java

**Tecniche di visualizzazione dei dati master con Aspose.Slides per Java**

Nell'attuale panorama basato sui dati, una visualizzazione efficace dei dati è essenziale per prendere decisioni consapevoli. Integrare le funzionalità dei grafici nelle applicazioni Java può trasformare i dati grezzi in storie visive accattivanti. Questo tutorial ti guiderà nella creazione e nell'esportazione di grafici utilizzando Aspose.Slides per Java, garantendo che le tue presentazioni siano al contempo informative e visivamente coinvolgenti.

**Cosa imparerai:**
- Carica e manipola i file di presentazione senza sforzo
- Aggiungi vari tipi di grafici alle tue diapositive
- Esportare i dati del grafico in cartelle di lavoro esterne senza problemi
- Imposta un percorso di cartella di lavoro esterna per una gestione efficiente dei dati

Cominciamo!

## Prerequisiti
Prima di iniziare, assicurati di avere pronta la seguente configurazione:

### Librerie e versioni richieste
- **Aspose.Slides per Java** versione 25.4 o successiva

### Requisiti di configurazione dell'ambiente
- Java Development Kit (JDK) 16 o superiore
- Un editor di codice o IDE come IntelliJ IDEA o Eclipse

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione Java
- Familiarità con i sistemi di build Maven o Gradle

## Impostazione di Aspose.Slides per Java
Per iniziare a utilizzare Aspose.Slides, devi includerlo nel tuo progetto. Ecco come fare:

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

In alternativa, puoi [scarica direttamente l'ultima versione](https://releases.aspose.com/slides/java/).

### Fasi di acquisizione della licenza
Aspose.Slides offre una licenza di prova gratuita per esplorare tutte le sue funzionalità. Puoi anche richiedere una licenza temporanea o acquistarne una per un utilizzo prolungato. Segui questi passaggi:
1. Visita il [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per ottenere la patente.
2. Per una prova gratuita, scarica da [Comunicati stampa](https://releases.aspose.com/slides/java/).
3. Richiedi una licenza temporanea [Qui](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, inizializzalo nella tua applicazione Java:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guida all'implementazione
### Caratteristica 1: Carica presentazione
Caricare una presentazione è il primo passo per qualsiasi attività di manipolazione.

#### Panoramica
Questa funzionalità illustra come caricare un file PowerPoint esistente utilizzando Aspose.Slides per Java.

#### Implementazione passo dopo passo
**Aggiungi grafico alla diapositiva**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Imposta il percorso per la directory dei tuoi documenti
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Carica una presentazione esistente
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Pulisci le risorse
        if (pres != null) pres.dispose();
    }
}
```
**Spiegazione:**
- `Presentation` viene inizializzato con il percorso verso il tuo `.pptx` file.
- Smaltire sempre il `Presentation` opporsi alle risorse gratuite.

### Funzionalità 2: aggiungi grafico alla diapositiva
L'aggiunta di un grafico può migliorare notevolmente la presentazione dei dati.

#### Panoramica
Questa funzionalità mostra come aggiungere un grafico a torta alla prima diapositiva di una presentazione.

#### Implementazione passo dopo passo
**Aggiungi grafico alla diapositiva**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Imposta il percorso per la directory dei tuoi documenti
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Aggiungi un grafico a torta nella posizione (50, 50) con larghezza 400 e altezza 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Spiegazione:**
- `addChart` metodo viene utilizzato per inserire un grafico a torta.
- I parametri includono il tipo di grafico e la sua posizione/dimensione sulla diapositiva.

### Funzionalità 3: esportare i dati del grafico in una cartella di lavoro esterna
L'esportazione dei dati consente ulteriori analisi al di fuori di PowerPoint.

#### Panoramica
Questa funzionalità illustra come esportare i dati di un grafico da una presentazione a una cartella di lavoro Excel esterna.

#### Implementazione passo dopo passo
**Esporta dati**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Imposta il percorso per la directory dei documenti e la directory di output
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Accedi al grafico della prima diapositiva
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Definire il percorso per la cartella di lavoro esterna
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Esportare i dati del grafico in un flusso Excel
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Spiegazione:**
- `readWorkbookStream` estrae i dati del grafico.
- I dati vengono scritti in un file Excel utilizzando `FileOutputStream`.

### Funzionalità 4: Imposta cartella di lavoro esterna per i dati del grafico
Collegare grafici a cartelle di lavoro esterne può semplificare la gestione dei dati.

#### Panoramica
Questa funzionalità illustra come impostare un percorso di cartella di lavoro esterno per memorizzare i dati del grafico.

#### Implementazione passo dopo passo
**Imposta percorso cartella di lavoro esterna**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Imposta il percorso per la directory dei tuoi documenti
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Accedi al grafico della prima diapositiva
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Definire e impostare il percorso per la cartella di lavoro esterna
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Spiegazione:**
- `setExternalWorkbook` collega il grafico a un file Excel, consentendo aggiornamenti dinamici dei dati.

## Applicazioni pratiche
Aspose.Slides offre soluzioni versatili per diversi scenari:

1. **Rapporti aziendali:** Crea report dettagliati con grafici direttamente dalle applicazioni Java.
2. **Presentazioni accademiche:** Arricchisci i contenuti didattici con grafici interattivi.
3. **Analisi finanziaria:** Esporta i dati finanziari in Excel per un'analisi approfondita.
4. **Analisi di marketing:** Visualizza le prestazioni della campagna utilizzando grafici dinamici.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}