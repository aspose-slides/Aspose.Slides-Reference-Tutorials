---
"date": "2025-04-17"
"description": "Scopri come creare e personalizzare un grafico a torta utilizzando Aspose.Slides per Java. Questa guida illustra la configurazione, l'implementazione e le applicazioni pratiche."
"title": "Creare un grafico a torta in Java con Aspose.Slides&#58; una guida completa"
"url": "/it/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creare un grafico a torta in Java con Aspose.Slides: una guida completa

## Grafici e diagrammi

### Introduzione

Nella visualizzazione dei dati, i grafici a torta rappresentano un modo intuitivo per rappresentare le proporzioni all'interno di un set di dati. Tuttavia, quando si ha a che fare con set di dati complessi in cui alcuni segmenti sono significativamente più piccoli di altri, i grafici a torta tradizionali possono risultare disordinati e difficili da interpretare. I grafici a torta risolvono questo problema suddividendo piccole porzioni in un grafico secondario, migliorando la leggibilità.

In questo tutorial imparerai a creare e manipolare un grafico a torta utilizzando Aspose.Slides per Java. Imparerai a configurare l'ambiente, a creare il grafico, a personalizzare proprietà come etichette dati e posizioni di suddivisione e a salvare la presentazione in formato PPTX. Al termine, avrai padroneggiato queste funzionalità con applicazioni pratiche e suggerimenti sulle prestazioni.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per Java
- Creazione di un grafico a torta
- Personalizzazione delle proprietà del grafico come etichette dati e configurazioni di divisione
- Salvataggio della presentazione su disco

Pronti a iniziare? Diamo prima un'occhiata ai prerequisiti!

## Prerequisiti

Prima di creare il nostro grafico a torta, assicurati di avere:

### Librerie, versioni e dipendenze richieste:
- **Aspose.Slides per Java**: Essenziale per la gestione programmatica delle presentazioni PowerPoint.

### Requisiti di configurazione dell'ambiente:
- Un Java Development Kit (JDK) installato sul computer. Si consiglia di utilizzare JDK 16 o versione successiva.
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA, Eclipse o NetBeans.

### Prerequisiti di conoscenza:
- Conoscenza di base della programmazione Java
- Familiarità con Maven o Gradle per la gestione delle dipendenze

## Impostazione di Aspose.Slides per Java

### Informazioni sull'installazione:

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

**Download diretto**: Puoi scaricare l'ultima versione da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

### Fasi di acquisizione della licenza:
- **Prova gratuita**: Inizia con una prova gratuita di 30 giorni per scoprire tutte le funzionalità.
- **Licenza temporanea**Richiedi una licenza temporanea per una valutazione estesa.
- **Acquistare**: Se Aspose.Slides soddisfa le tue esigenze, prendi in considerazione l'acquisto di una licenza.

### Inizializzazione e configurazione di base

Una volta impostata la libreria nel progetto, inizializzala creando un'istanza di `Presentation` classe:

```java
Presentation presentation = new Presentation();
```

Questo prepara il terreno per aggiungere vari grafici alle diapositive. Passiamo ora all'implementazione del nostro grafico a torta.

## Guida all'implementazione

### Creazione di un grafico a torta

#### Panoramica
Inizieremo creando un'istanza di un `Presentation` e aggiungi un grafico a torta nella prima diapositiva. Questo grafico visualizzerà efficacemente i dati separando i segmenti più piccoli in una torta secondaria, migliorando la leggibilità.

#### Passaggio 1: creare un'istanza della classe di presentazione
```java
// Crea una nuova presentazione
ePresentation presentation = new Presentation();
```
Questo codice inizializza la presentazione in cui aggiungeremo i nostri grafici.

#### Passaggio 2: aggiungere un grafico a torta nella prima diapositiva
```java
// Aggiungere un grafico a torta alla prima diapositiva nella posizione (50, 50) con dimensione (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Qui specifichiamo il tipo di grafico (`PieOfPie`) e la sua posizione e dimensioni sulla diapositiva.

#### Passaggio 3: impostare le etichette dati per mostrare i valori per la serie
```java
// Configurare le etichette dati per visualizzare i valori
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Questo passaggio garantisce che ogni segmento del nostro grafico a torta visualizzi il valore corrispondente, facilitando una rapida interpretazione dei dati.

#### Passaggio 4: configurare la seconda dimensione della torta e dividerla in percentuale
```java
// Imposta la dimensione della torta secondaria
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Dividi la torta in percentuale
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Imposta la posizione di divisione
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Queste configurazioni consentono di personalizzare il modo in cui il grafico viene suddiviso e visualizzato in segmenti più piccoli, migliorandone la chiarezza per chi lo visualizza.

#### Passaggio 5: salvare la presentazione sul disco in formato PPTX
```java
// Definisci la directory di output
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Salva la presentazione\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}