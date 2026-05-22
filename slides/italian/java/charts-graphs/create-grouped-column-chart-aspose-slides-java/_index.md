---
date: '2026-03-20'
description: Scopri come aggiungere un grafico a colonne raggruppate a una presentazione
  PowerPoint, personalizzare il grafico PowerPoint e inserire un grafico a serie di
  dati usando Aspose.Slides per Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Come aggiungere un grafico a colonne raggruppate in PowerPoint usando Aspose.Slides
  per Java
url: /it/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere un grafico a colonne raggruppate in PowerPoint usando Aspose.Slides per Java

## Introduzione

Quando è necessario **aggiungere un grafico a colonne raggruppate** a una presentazione PowerPoint, un’immagine chiara può trasformare numeri grezzi in una storia immediatamente comprensibile. Farlo manualmente in PowerPoint può richiedere molto tempo, soprattutto quando si devono generare molte diapositive in modo programmatico. **Aspose.Slides per Java** elimina l’ostacolo: consente di creare, personalizzare un grafico PowerPoint e inserire una serie di dati con poche righe di codice.

In questo tutorial imparerai a:
- Inizializzare una nuova presentazione PowerPoint con Aspose.Slides per Java.
- **Aggiungere un grafico alla diapositiva** e configurarlo come grafico a colonne raggruppate.
- **Creare un grafico a colonne raggruppate** definendo i livelli di raggruppamento per le categorie.
- **Inserire una serie di dati** in modo che i dati vengano visualizzati correttamente.
- Salvare la presentazione finale come file PPTX.

Assicuriamoci di avere tutto il necessario prima di immergerci nel codice.

## Risposte rapide
- **Qual è la classe principale?** `Presentation` da `com.aspose.slides`.
- **Quale tipo di grafico viene utilizzato?** `ChartType.ClusteredColumn`.
- **È necessaria una licenza per i test?** Una versione di prova gratuita funziona, ma una licenza rimuove i limiti di valutazione.
- **Quale versione di Java è supportata?** JDK 16 o successiva (l’esempio utilizza JDK 16).
- **Come eseguire il campione?** Aggiungere la dipendenza Maven/Gradle, compilare ed eseguire il metodo `main`.

## Cos’è “aggiungere un grafico a colonne raggruppate”?

Un *grafico a colonne raggruppate* (chiamato anche grafico a colonne raggruppate) visualizza più serie di dati affiancate per ciascuna categoria, facilitando il confronto dei valori tra gruppi. In PowerPoint questo tipo di grafico è ideale per vendite trimestrali, **risultati di sondaggi** o qualsiasi scenario in cui è necessario **confrontare più set di dati** all’interno della stessa categoria.

## Perché usare Aspose.Slides per aggiungere un grafico a colonne raggruppate?

- **Automazione completa** – genera decine di diapositive senza sforzo manuale.
- **Personalizzazione fine‑grained** – controlla colori, etichette, livelli di raggruppamento e **altro**.
- **Cross‑platform** – funziona su qualsiasi OS che supporti Java.
- **Nessuna installazione di Office richiesta** – genera file PPTX su server o pipeline CI.

## Prerequisiti

- Libreria **Aspose.Slides per Java** (si consiglia l’ultima versione).  
- JDK 16 o successiva.  
- Strumento di build Maven o Gradle (oppure è possibile aggiungere il JAR manualmente).  
- Un IDE **o** un editor di testo per eseguire il codice Java.

## Configurazione di Aspose.Slides per Java

Aggiungi la libreria al tuo progetto usando uno dei seguenti script di build.

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

In alternativa, puoi scaricare direttamente l’ultima release da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisizione della licenza

Prima di distribuire in produzione, ottieni una licenza:
- **Prova gratuita** – esplora tutte le funzionalità senza acquisto.
- **Licenza temporanea** – valuta capacità estese per un breve periodo.
- **Licenza completa** – sblocca l’uso illimitato. Ottienila dalla [pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

## Guida all’implementazione

Percorreremo ogni passaggio, spiegando **come aggiungere il grafico** e **personalizzare il grafico PowerPoint** lungo il percorso.

### Inizializzare la presentazione

Crea un nuovo oggetto `Presentation` e recupera la diapositiva predefinita.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Aggiungere il grafico alla diapositiva

Ora **aggiungiamo il grafico alla diapositiva** usando il tipo `ClusteredColumn` e cancelliamo eventuali dati predefiniti.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Preparare il workbook dei dati del grafico

Il grafico memorizza i dati in un workbook interno. Lo cancelliamo per partire da zero.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Aggiungere categorie con livelli di raggruppamento

Raggruppare le categorie crea l’effetto del **grafico a colonne raggruppate**. Ogni categoria può appartenere a un gruppo logico.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Aggiungere serie di dati al grafico

Qui **inseriamo le serie di dati** che verranno visualizzate come colonne separate.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Salvare la presentazione con il grafico

Infine, scrivi il file PPTX su disco.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Applicazioni pratiche

- **Report aziendali** – confronta i ricavi trimestrali tra regioni.  
- **Ricerca accademica** – mostra risultati sperimentali raggruppati per condizioni di test.  
- **Gestione progetti** – visualizza i tassi di completamento delle attività per più team in un’unica diapositiva.

## Considerazioni sulle prestazioni

- **Gestione della memoria** – rilascia i workbook di grandi dimensioni dopo l’uso.  
- **Operazioni batch** – evita di aggiornare il grafico all’interno di loop stretti; raccogli i dati prima, poi applicali.  
- **Ottimizzazioni integrate** – Aspose.Slides fornisce metodi come `Presentation.optimize()` per file di grandi dimensioni.

## Errori comuni e suggerimenti

- **Errore:** dimenticare di cancellare le serie/categorie esistenti può provocare dati duplicati.  
  **Suggerimento:** chiama sempre `clear()` prima di popolare nuovi dati.  
- **Errore:** usare l’indirizzo di cella sbagliato (ad es., `"c2"` invece di `"C2"`).  
  **Suggerimento:** i riferimenti alle celle non distinguono maiuscole/minuscole, ma mantienili coerenti per leggibilità.  
- **Suggerimento:** usa `setGroupingItem` per creare etichette di gruppo significative; appaiono automaticamente nella legenda del grafico.

## Domande frequenti

**D1: Come posso aggiungere più serie al mio grafico?**  
R1: Chiama ripetutamente `ch.getChartData().getSeries().add()`, fornendo un nome univoco e i punti dati per ciascuna serie.

**D2: Quali sono i problemi più comuni con i grafici Aspose.Slides?**  
R2: I problemi derivano spesso da intervalli di dati non corrispondenti o celle del workbook mancanti. Verifica che ogni categoria e punto dati abbia una cella corrispondente.

**D3: Posso usare Aspose.Slides con altri linguaggi di programmazione?**  
R3: Sì, Aspose fornisce librerie equivalenti per .NET, C++, Python e altri.

**D4: Come aggiorno un grafico esistente in una presentazione?**  
R4: Carica la presentazione, individua il grafico tramite `slide.getShapes().get_Item(index)`, quindi modifica le sue serie o la formattazione secondo necessità.

**D5: Ci sono limitazioni sui tipi di grafico con Aspose.Slides?**  
R5: La libreria supporta un’ampia gamma di tipi di grafico, ma controlla sempre la documentazione più recente per eventuali tipi aggiunti o deprecati.

## Risorse

- **Documentazione**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Acquisto**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Prova gratuita**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Licenza temporanea**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Forum di supporto**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-20  
**Testato con:** Aspose.Slides per Java 25.4 (JDK 16)  
**Autore:** Aspose