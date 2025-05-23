---
"date": "2025-04-17"
"description": "Scopri come creare splendidi grafici a ciambella in Java con Aspose.Slides. Questa guida completa illustra l'inizializzazione, la configurazione dei dati e il salvataggio delle presentazioni."
"title": "Crea grafici ad anello in Java usando Aspose.Slides&#58; una guida completa"
"url": "/it/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creare grafici ad anello in Java utilizzando Aspose.Slides: una guida passo passo

## Introduzione

Nell'attuale contesto basato sui dati, visualizzare le informazioni in modo efficace è fondamentale per migliorare la comprensione e il coinvolgimento. Sebbene creare grafici professionali tramite codice possa sembrare impegnativo, soprattutto con Java, questa guida vi guiderà nell'utilizzo di Aspose.Slides per Java per creare grafici ad anello senza sforzo.

Seguendo questi passaggi, gli sviluppatori acquisiranno esperienza pratica nella manipolazione delle diapositive delle presentazioni e nell'integrazione ottimale della visualizzazione dei dati.

**Punti chiave:**
- Inizializzare un oggetto Presentation utilizzando Aspose.Slides Java.
- Configura i dati del grafico e gestisci le serie o le categorie esistenti.
- Aggiungi e personalizza serie e categorie per i tuoi grafici.
- Formattare e visualizzare i punti dati in modo efficace.
- Salva facilmente la tua presentazione in vari formati.

Prima di immergerti nell'implementazione, assicurati di avere tutto il necessario per iniziare.

## Prerequisiti

Per seguire questo tutorial, assicurati di avere:

- **Librerie richieste:**
  - Aspose.Slides per Java versione 25.4 o successiva.
  
- **Configurazione dell'ambiente:**
  - JDK 16 o versione successiva installato sul sistema.
  - Un IDE come IntelliJ IDEA, Eclipse o NetBeans.

- **Prerequisiti di conoscenza:**
  - Comprensione di base dei concetti di programmazione Java.
  - Familiarità con la gestione delle dipendenze nei progetti Maven o Gradle.

## Impostazione di Aspose.Slides per Java

Per integrare Aspose.Slides nel tuo progetto, segui questi passaggi in base allo strumento di compilazione che utilizzi:

**Configurazione Maven:**
Aggiungi la seguente dipendenza al tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Configurazione Gradle:**
Includi quanto segue nel tuo `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download diretto:**
In alternativa, scarica l'ultima versione direttamente da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Acquisizione di una licenza

Per utilizzare Aspose.Slides senza limitazioni di valutazione:
- **Prova gratuita:** Inizia con una licenza temporanea per esplorare tutte le funzionalità.
- **Licenza temporanea:** Ottienine uno tramite il [Sito web di Aspose](https://purchase.aspose.com/temporary-license/).
- **Acquistare:** Si consiglia di acquistarlo per un uso continuativo.

Applica la tua licenza nella tua applicazione Java utilizzando:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guida all'implementazione

### Inizializzazione della presentazione e del grafico

#### Panoramica
Per iniziare, inizializziamo un oggetto di presentazione e aggiungiamo un grafico ad anello alla prima diapositiva.

**Passaggio 1: inizializzare la presentazione**
Carica un file PPTX esistente o creane uno nuovo:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Passaggio 2: aggiungere il grafico ad ciambella**
Crea un grafico nella prima diapositiva alle coordinate specificate:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurazione della cartella di lavoro dei dati del grafico e cancellazione delle serie/categorie esistenti

#### Panoramica
Configurare la cartella di lavoro dei dati del grafico e rimuovere tutte le serie o le categorie preesistenti.

**Passaggio 1: cartella di lavoro dei dati del grafico di accesso**
Recupera la cartella di lavoro collegata al tuo grafico:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Passaggio 2: cancellare le serie e le categorie esistenti**
Assicurarsi che non vi siano punti dati residui:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Aggiungere serie al grafico

#### Panoramica
Popola il tuo grafico con più serie, ciascuna personalizzata nell'aspetto e nel comportamento.

**Passaggio 1: aggiungere serie in modo iterativo**
Esegui un ciclo tra gli indici per aggiungere serie:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Personalizza la serie
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Aggiunta di categorie e punti dati al grafico

#### Panoramica
Configura le categorie e aggiungi punti dati con formattazione specifica per le etichette.

**Passaggio 1: aggiungere categorie**
Scorrere gli indici per ogni categoria:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Passaggio 2: aggiungere punti dati a ciascuna serie**
Scorrere ogni serie per la categoria corrente:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Impostazioni del formato dei punti dati
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formattazione delle etichette per l'ultima serie
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Regola le opzioni di visualizzazione
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Regola la posizione dell'etichetta
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Salvataggio della presentazione

#### Panoramica
Dopo aver configurato il grafico, salva la presentazione nella directory specificata.

**Passaggio 1: salvare la presentazione**
Utilizzare il `save` metodo per scrivere le modifiche:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusione

Ora hai imparato a creare e personalizzare grafici ad anello in Java utilizzando Aspose.Slides. Questi passaggi forniscono le basi per integrare visualizzazioni dati sofisticate nelle tue presentazioni.

**Prossimi passi:**
- Prova i diversi tipi di grafici disponibili in Aspose.Slides.
- Esplora ulteriori opzioni di personalizzazione, come colori, caratteri e stili, per soddisfare le tue esigenze di branding.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}