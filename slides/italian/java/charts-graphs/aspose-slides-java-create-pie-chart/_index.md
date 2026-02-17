---
date: '2026-02-17'
description: Scopri come aggiungere grafici a torta alle presentazioni PowerPoint
  usando Aspose.Slides per Java. Segui questa guida passo passo per creare e personalizzare
  grafici a torta professionali.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Come aggiungere un grafico a torta in PowerPoint con Aspose.Slides per Java
url: /it/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e personalizza grafici a torta in PowerPoint usando Aspose.Slides per Java

## Introduzione

Stai avendo difficoltà a visualizzare i dati in modo efficace nelle tue presentazioni PowerPoint? **Aggiungere una diapositiva con grafico a torta PowerPoint** può trasformare istantaneamente numeri grezzi in una chiara storia visiva. Con Aspose.Slides per Java, puoi **aggiungere grafici a torta PowerPoint** in modo programmatico, ottenendo il pieno controllo su design e dati senza mai aprire manualmente PowerPoint. In questo tutorial percorreremo l’intero processo—from la configurazione della libreria alla personalizzazione dei singoli punti dati—così potrai realizzare diapositive rifinite e guidate dai dati in pochi minuti.

### Risposte rapide
- **Quale libreria mi serve?** Aspose.Slides per Java (ultima versione).  
- **Posso creare un grafico senza PowerPoint installato?** Sì, l’API funziona completamente offline.  
- **Quale versione di Java è richiesta?** Si consiglia JDK 16 o successivo.  
- **Come cambio il colore di una fetta?** Usa i metodi `setFillType` e `setSolidFillColor` sul punto dati.  
- **È obbligatoria una licenza?** Una versione di prova funziona per lo sviluppo; una licenza permanente rimuove i limiti di valutazione.

### Cosa imparerai
- Come **aggiungere grafici a torta PowerPoint** in modo programmatico con Java.  
- Modi per personalizzare l’esplosione delle fette, i colori e altre proprietà visive.  
- Best practice per la gestione delle risorse e le prestazioni quando si trattano presentazioni di grandi dimensioni.

## Perché aggiungere un grafico a torta PowerPoint usando Aspose.Slides per Java?
Incorporare un grafico a torta direttamente dal codice ti consente di generare report sempre aggiornati, automatizzare dashboard mensili o creare deck diapositive personalizzati al volo. Elimina errori di copia‑incolla manuali, garantisce coerenza tra le presentazioni e si integra senza problemi con i back‑end Java esistenti.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Libreria Aspose.Slides per Java** – il tutorial fa riferimento alla versione 25.4 (l’ultima release al momento della stesura).  
- Un **Java Development Kit (JDK)** compatibile – è preferibile JDK 16+.  
- Familiarità di base con **Maven** o **Gradle** per la gestione delle dipendenze.  

## Configurazione di Aspose.Slides per Java

Per iniziare, includi la libreria Aspose.Slides nel tuo progetto.

### Maven
Aggiungi questa dipendenza al tuo file `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inserisci quanto segue nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, scarica l’ultima versione direttamente da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenza
Per utilizzare Aspose.Slides senza limitazioni:

- Inizia con una **prova gratuita** per valutare l’API.  
- Richiedi una **licenza temporanea** per test più prolungati nella pagina [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Acquista un abbonamento completo tramite la [Purchase page](https://purchase.aspose.com/buy).

## Come aggiungere un grafico a torta PowerPoint usando Aspose.Slides per Java

Di seguito trovi una guida passo‑a‑passo che mostra esattamente come creare e personalizzare un grafico a torta.

### Passo 1: Inizializzare la presentazione
Per prima cosa, crea un nuovo oggetto `Presentation`. Rappresenta un file PowerPoint vuoto.
```java
Presentation pres = new Presentation();
```

### Passo 2: Aggiungere il grafico a torta
Inserisci un grafico a torta nella prima diapositiva. Le coordinate (50, 50) e le dimensioni (600 × 400) funzionano bene per una diapositiva standard 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Passo 3: Salvare la presentazione
Scrivi la presentazione su disco. Sostituisci `YOUR_OUTPUT_DIRECTORY` con la cartella in cui desideri salvare il file.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Passo 4: Pulire le risorse
Rilascia l’oggetto `Presentation` per liberare le risorse native.
```java
if (pres != null) pres.dispose();
```

## Personalizzazione dell’esplosione della fetta e del colore

Personalizzare le singole fette rende il grafico più leggibile, soprattutto quando vuoi evidenziare un valore specifico.

### Passo 1: Caricare una presentazione esistente (o riutilizzare quella appena creata)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Passo 2: Accedere al grafico e al punto dati target
Qui recuperiamo il secondo punto dati (indice 1) dalla prima serie.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Passo 3: Applicare esplosione e colore
Separa visivamente la fetta e cambia il suo colore di riempimento in blu.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Passo 4: Salvare e rilasciare
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Applicazioni pratiche
- **Report di vendita:** Evidenzia i prodotti più venduti con fette esplose.  
- **Analisi di budget:** Assegna colori distinti ai dipartimenti per un confronto visivo rapido.  
- **Diapositive educative:** Scomponi concetti complessi in segmenti di grafico facilmente digeribili.

## Considerazioni sulle prestazioni
- **Rilascia gli oggetti** tempestivamente per evitare perdite di memoria, soprattutto quando generi molte diapositive in un ciclo.  
- **Monitora l’utilizzo dell’heap** per presentazioni di grandi dimensioni; considera lo streaming dell’output con le overload di `Save` che accettano `OutputStream`.  
- Rimani su **JDK 16+** per beneficiare dei più recenti miglioramenti della garbage collection.

## Conclusione
Ora disponi di un flusso di lavoro completo e pronto per la produzione per **aggiungere grafici a torta PowerPoint** usando Aspose.Slides per Java. Sperimenta con diverse distanze di esplosione, colori e set di dati per allineare il risultato al tuo brand. Quando sei pronto, esplora altri tipi di grafico—bar, line o scatter—per costruire un cruscotto analitico completo all’interno di PowerPoint.

## Sezione FAQ
1. **Qual è il principale vantaggio di usare Aspose.Slides per Java?**  
   - Semplifica la creazione e la manipolazione di file PowerPoint in modo programmatico, offrendo un’ampia gamma di funzionalità.  
2. **Posso personalizzare altri tipi di grafico con Aspose.Slides?**  
   - Assolutamente! Aspose.Slides supporta vari tipi di grafico come bar, line e scatter.  
3. **Come gestisco più diapositive quando creo grafici?**  
   - Accedi a ciascuna diapositiva per indice usando il metodo `get_Item()` per applicare modifiche su diapositive diverse.  
4. **Cosa succede se il mio grafico a torta non viene visualizzato correttamente dopo la personalizzazione?**  
   - Verifica le coordinate e le dimensioni usate in `addChart()`, assicurandoti che rientrino nel layout della diapositiva.  
5. **Dove posso trovare funzionalità più avanzate per Aspose.Slides?**  
   - Esplora la [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/) per scoprire ulteriori funzionalità e opzioni.

## Risorse
- **Documentazione:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download libreria:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Acquista licenza:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Prova gratuita:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Licenza temporanea:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum di supporto:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Ultimo aggiornamento:** 2026-02-17  
**Testato con:** Aspose.Slides per Java 25.4 (classificatore JDK 16)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}