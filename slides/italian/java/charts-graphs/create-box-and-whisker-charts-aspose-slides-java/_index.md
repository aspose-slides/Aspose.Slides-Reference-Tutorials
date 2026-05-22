---
date: '2026-03-02'
description: Impara come creare un box plot in Java, aggiungere un grafico alla diapositiva
  e generare un grafico a scatola e baffi in PowerPoint usando Aspose.Slides per Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Crea un box plot in Java usando Aspose.Slides per PowerPoint
url: /it/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici a scatola e baffi in PowerPoint usando Aspose.Slides per Java

In questa guida **creerai un box plot java** con Aspose.Slides, quindi incorporerai il grafico direttamente in una diapositiva PowerPoint. Creare presentazioni dati visivamente accattivanti è fondamentale nel mondo odierno guidato dai dati, e i grafici sono strumenti essenziali a questo scopo. Se desideri generare grafici a scatola e baffi all'interno di PowerPoint usando Java, la libreria Aspose.Slides offre una soluzione solida. Questo tutorial ti guiderà nella creazione e configurazione di questi grafici in modo fluido con Aspose.Slides per Java.

## Cosa imparerai

- Configurare l'ambiente per Aspose.Slides per Java
- Passaggi per **aggiungere un grafico alla diapositiva** e generare un grafico a scatola‑baffi in PowerPoint usando Java
- Best practice per ottimizzare le prestazioni quando si lavora con Aspose.Slides
- Applicazioni reali dei grafici a scatola‑baffi

## Risposte rapide
- **Quale libreria crea un box plot in Java?** Aspose.Slides for Java.
- **Quale tipo di grafico è usato?** `ChartType.BoxAndWhisker`.
- **Ho bisogno di una licenza?** Una prova gratuita è sufficiente per la valutazione; è necessaria una licenza commerciale per la produzione.
- **Posso aggiungere più serie?** Sì – ripeti il blocco di creazione della serie per ogni set di dati.
- **Qual è il formato del file finale?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Prerequisiti

Per seguire questo tutorial, assicurati di avere:

- **Java Development Kit (JDK)**: JDK 8 o superiore dovrebbe essere installato.
- **Libreria Aspose.Slides per Java**: Essenziale per gestire presentazioni PowerPoint in Java.
- **IDE**: Un Ambiente di Sviluppo Integrato come IntelliJ IDEA o Eclipse per scrivere ed eseguire il tuo codice.

## Configurazione di Aspose.Slides per Java

Per usare Aspose.Slides, aggiungila come dipendenza. Puoi gestirla tramite Maven, Gradle o scaricandola direttamente.

### Maven

Aggiungi la seguente dipendenza nel tuo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Nel tuo `build.gradle`, includi:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto

In alternativa, scarica l'ultima versione da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisizione della licenza

- **Prova gratuita**: Inizia con una prova gratuita per esplorare le funzionalità.  
- **Licenza temporanea**: Ottieni una licenza temporanea per scopi di valutazione.  
- **Acquisto**: Per funzionalità complete, considera l'acquisto di una licenza.

Per inizializzare Aspose.Slides, assicurati di avere la libreria nel tuo classpath e configura eventuali requisiti di licenza secondo necessità.

## Guida all'implementazione

Ora immergiamoci nel codice passo‑per‑passo. Ogni blocco è spiegato prima dello snippet così sai esattamente cosa fa.

### Cos'è un box plot e perché usarlo in Java?

Un grafico a scatola‑baffi (spesso chiamato *box plot*) visualizza la distribuzione dei dati — mediana, quartili e outlier — in forma compatta. In Java, generare questo grafico programmaticamente ti permette di incorporare intuizioni statistiche direttamente nelle presentazioni PowerPoint, eliminando la creazione manuale dei grafici.

### Perché aggiungere un grafico alla diapositiva con Aspose.Slides?

Aspose.Slides astrae i dettagli OpenXML a basso livello, fornendoti un'API fluida per creare, stilizzare ed esportare grafici. Questo significa che puoi automatizzare la generazione di report, produrre un branding coerente e integrare i grafici in flussi di lavoro Java più ampi.

### Passo 1: Creare o aprire una presentazione

Per prima cosa, apri un PPTX esistente o avviane uno nuovo:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Suggerimento:** Se il file non esiste, Aspose.Slides creerà una nuova presentazione vuota per te.

### Passo 2: Aggiungere un grafico a scatola‑baffi alla diapositiva

Posiziona il grafico dove ti serve specificando la posizione e le dimensioni (in punti):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Passo 3: Cancellare i dati esistenti

Prima di inserire nuovi dati, rimuovi eventuali categorie o serie segnaposto:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Passo 4: Configurare le categorie

Aggiungi le categorie (etichette dell'asse X) che appariranno sotto ogni scatola:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Nota:** Regola il testo dell'etichetta per corrispondere al dominio dei tuoi dati (ad es., “Q1”, “Product A”).

### Passo 5: Creare e personalizzare la serie

Ora crea una serie, imposta le opzioni visive e fornisci i punti dati numerici:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Puoi sostituire l'array `int[] data` con valori letti da un database, file CSV o qualsiasi altra fonte.

### Passo 6: Salvare la presentazione

Salva le modifiche in un nuovo file PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Passo 7: Pulire le risorse

Disporre sempre dell'oggetto `Presentation` per liberare le risorse native:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Applicazioni pratiche

I grafici a scatola‑baffi sono inestimabili nell'analisi statistica e nella presentazione dei dati. Ecco alcuni scenari in cui brillano:

1. **Analisi finanziaria** – Visualizza la distribuzione dei ricavi tra le regioni.  
2. **Controllo qualità** – Individua gli outlier nelle misurazioni di produzione.  
3. **Ricerca accademica** – Mostra la variabilità dei risultati sperimentali.  
4. **Ricerca di mercato** – Confronta le prestazioni del prodotto tra le diverse demografie.

Integrare questi grafici nelle presentazioni PowerPoint consente agli stakeholder di comprendere i dati complessi a colpo d'occhio.

## Considerazioni sulle prestazioni

Quando lavori con Aspose.Slides in Java, tieni a mente questi consigli:

- **Gestione della memoria** – Disporre rapidamente degli oggetti `Presentation`.
- **Gestione dei dati** – Carica solo i dati necessari; evita di inserire set di dati massivi direttamente nel workbook del grafico.
- **Caricamento lazy** – Se generi molte diapositive, considera di creare grafici solo per quelle che saranno visualizzate.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **Il grafico appare vuoto** | Celle dei dati non popolate correttamente | Verifica che `wb.getCell` faccia riferimento alla riga/colonna corretta e che il valore non sia `null`. |
| **Outlier non mostrati** | `setShowOutlierPoints` impostato a `false` | Assicurati che `series.setShowOutlierPoints(true)` sia chiamato. |
| **Perdita di memoria** | Presentation non disposta | Avvolgi sempre l'uso in try/finally e chiama `dispose()`. |
| **Quartili errati** | Utilizzo del metodo predefinito `Inclusive` | Passa a `Exclusive` tramite `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Domande frequenti

**Q1: Che cos'è un grafico a scatola‑baffi?**  
Un grafico a scatola‑baffi, noto anche come box plot, visualizza la distribuzione dei dati basata su cinque statistiche riassuntive: minimo, primo quartile, mediana, terzo quartile e massimo, più eventuali outlier.

**Q2: Posso personalizzare l'aspetto del grafico a scatola‑baffi?**  
Sì. Aspose.Slides ti consente di modificare colori, stili di linea, forme dei marcatori e persino aggiungere etichette dati tramite l'API di formattazione del grafico.

**Q3: È possibile gestire più serie in un unico grafico?**  
Assolutamente. Ripeti il blocco di creazione della serie per ogni set di dati che desideri visualizzare.

**Q4: Come risolvo i problemi con dati che non vengono visualizzati correttamente?**  
Assicurati che i dati siano scritti correttamente nelle celle del workbook e che le proprietà di visibilità come `setShowMeanLine` siano abilitate.

**Q5: Dove posso ottenere supporto se incontro problemi?**  
Visita il [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per aiuto della community, o consulta la documentazione ufficiale.

**Q6: Aspose.Slides supporta altri tipi di grafico?**  
Sì, supporta grafici a linee, barre, torta, dispersione, radar e molti altri tipi di grafico.

**Q7: Posso generare grafici in un ambiente server senza interfaccia grafica?**  
La libreria funziona completamente in scenari server‑side; non è necessario alcun UI.

## Risorse

- **Documentazione**: Esplora i riferimenti API dettagliati su [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Accedi alle versioni di Aspose.Slides [qui](https://releases.aspose.com/slides/java/)  
- **Acquisto**: Acquista una licenza per sbloccare tutte le funzionalità su [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Prova gratuita & Licenza temporanea**: Inizia con una prova gratuita o richiedi una licenza temporanea [qui](https://releases.aspose.com/slides/java/)

Seguendo questa guida, ora sei pronto a generare programmaticamente grafici a scatola‑baffi perspicaci nelle tue applicazioni Java e incorporarli direttamente nelle presentazioni PowerPoint. Buon coding!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Author:** Aspose