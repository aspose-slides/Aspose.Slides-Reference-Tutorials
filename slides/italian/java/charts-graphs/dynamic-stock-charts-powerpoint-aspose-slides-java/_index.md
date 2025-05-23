---
"date": "2025-04-17"
"description": "Scopri come creare e personalizzare grafici azionari dinamici in PowerPoint utilizzando Aspose.Slides per Java. Questa guida illustra come inizializzare le presentazioni, aggiungere serie di dati, formattare i grafici e salvare i file."
"title": "Creazione di grafici azionari dinamici in PowerPoint con Aspose.Slides per Java"
"url": "/it/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creazione di grafici azionari dinamici in PowerPoint con Aspose.Slides per Java

## Introduzione

Migliora le tue presentazioni PowerPoint integrando grafici azionari dinamici. Che tu sia un analista finanziario, un professionista o un docente che ha bisogno di visualizzare efficacemente i trend dei dati, questo tutorial ti guiderà nella creazione e personalizzazione di grafici azionari utilizzando Aspose.Slides per Java. Al termine di questa guida, sarai in grado di caricare file PowerPoint esistenti, aggiungere grafici azionari dettagliati con serie e categorie personalizzate, formattarli in modo impeccabile e salvare la tua presentazione migliorata.

**Cosa imparerai:**
- Inizializzare una presentazione in Java con Aspose.Slides
- Aggiungi e personalizza i grafici azionari
- Cancella serie di dati e categorie
- Inserisci nuovi punti dati per un'analisi completa
- Formattare efficacemente le linee e le barre del grafico
- Salva la presentazione aggiornata

Pronti a creare presentazioni visivamente accattivanti? Iniziamo!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- **Kit di sviluppo Java (JDK)**Assicurati che JDK sia installato sul tuo sistema.
- **IDE**: Utilizza qualsiasi IDE come IntelliJ IDEA o Eclipse per scrivere ed eseguire codice Java.
- **Libreria Aspose.Slides per Java**: Questo tutorial richiede la versione 25.4 di Aspose.Slides per Java.

### Impostazione di Aspose.Slides per Java

#### Esperto
Per integrare Aspose.Slides nel tuo progetto utilizzando Maven, aggiungi la seguente dipendenza al tuo `pom.xml`:

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

#### Download diretto
In alternativa, scaricare l'ultimo JAR da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

**Acquisizione della licenza**: Puoi iniziare con una prova gratuita o richiedere una licenza temporanea. Per un utilizzo prolungato, valuta l'acquisto di una licenza completa.

## Guida all'implementazione

Analizziamo passo dopo passo ciascuna funzionalità.

### Inizializza la presentazione
#### Panoramica
Per prima cosa carica un file PowerPoint esistente per prepararlo alle modifiche.

#### Guida passo passo
1. **Importa la libreria**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Carica il file di presentazione**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Pronto per eseguire operazioni su 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi grafico azionario alla diapositiva
#### Panoramica
Questo passaggio prevede l'aggiunta di un grafico azionario alla prima diapositiva della presentazione.

3. **Aggiungi il grafico**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Cancella serie di dati e categorie esistenti nel grafico
#### Panoramica
Per ricominciare da zero, rimuovere dal grafico tutte le serie di dati o le categorie preesistenti.

4. **Cancella dati**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi categorie ai dati del grafico
#### Panoramica
Aggiungi categorie personalizzate per una migliore segmentazione e comprensione dei dati.

5. **Inserisci categorie**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Aggiungi categorie
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi serie di dati al grafico
#### Panoramica
Integra diverse serie di dati, come Apertura, Massimo, Minimo e Chiusura, per un'analisi completa.

6. **Aggiungi serie di dati**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Aggiungi serie per 'Apertura', 'Alto', 'Basso' e 'Chiusura'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Aggiungi punti dati alla serie
#### Panoramica
Per una rappresentazione accurata, popolare ogni serie con punti dati specifici.

7. **Inserisci punti dati**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Aggiungi punti dati alla serie "Apri"
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Aggiungi punti dati alla serie "Alta"
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Aggiungi punti dati alla serie "Basso"
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Aggiungi punti dati alla serie "Chiudi"
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formato linee alte-basse e barre su/giù
#### Panoramica
Personalizza l'aspetto delle linee alte-basse e delle barre verticali per una migliore visualizzazione.

8. **Formato linee alte-basse**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Formato linee alto-basso per serie 'Chiudi'
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **Visualizza barre su/giù**:
   
   ```java
   // Visualizza barre su/giù per il gruppo di serie del grafico azionario
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personalizza le etichette dati sulle linee alto-basso
#### Panoramica
Aggiungere e formattare le etichette dati per visualizzare i valori su linee alte e basse.

10. **Mostra i valori sulle barre su/giù**:
    
    ```java
    // Mostra i valori sulle barre su/giù per ogni serie nel gruppo di grafici
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Imposta il colore di riempimento delle barre verticali
#### Panoramica
Imposta un colore di riempimento personalizzato per le barre su/giù per migliorarne la distinzione visiva.

11. **Cambia i colori della barra su/giù**:
    
    ```java
    // Cambia i colori delle barre su/giù per ogni serie nel gruppo di grafici
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // Serie 'Aperta'
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Barre in alto in ciano
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // Serie 'High'
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Barre verticali in verde mare scuro
        }
    }
    ```

### Salvare il file PowerPoint
#### Panoramica
Salva le modifiche in un nuovo file PowerPoint.

12. **Salva la presentazione**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Conclusione

Congratulazioni! Hai creato e personalizzato con successo grafici azionari dinamici in PowerPoint utilizzando Aspose.Slides per Java. Questo processo arricchisce le tue presentazioni con visualizzazioni di dati visivamente accattivanti, consentendoti di comunicare in modo efficace informazioni finanziarie. Se sei interessato a personalizzare ulteriormente o esplorare altri tipi di grafici, prendi in considerazione l'approfondimento della guida completa [Documentazione di Aspose.Slides](https://docs.aspose.com/slides/java/).

## Ulteriori letture e riferimenti
- Documentazione di Aspose.Slides per Java: esplora guide dettagliate sull'utilizzo delle varie funzionalità di Aspose.Slides.
- Panoramica sugli strumenti per la creazione di grafici di PowerPoint: scopri i diversi strumenti per la creazione di grafici disponibili in Microsoft PowerPoint.
- Buone pratiche per la visualizzazione dei dati: scopri come presentare i dati in modo efficace attraverso strumenti visivi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}