---
date: '2026-08-06'
description: Scopri come cambiare legend font color e modificare chart legend text
  usando Aspose.Slides for Java. Segui le istruzioni step‑by‑step per personalizzare
  rapidamente chart legends.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Scopri come cambiare legend font color e modificare chart legend text
  con Aspose.Slides for Java. Questa guida ti mostra i passaggi esatti e le migliori
  pratiche.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Come cambiare il colore del font della legenda in Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Come cambiare il colore del font della legenda in Aspose.Slides for Java
url: /it/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come cambiare il colore del carattere della legenda in Aspose.Slides per Java

## Introduzione
Se hai bisogno di **cambiare il colore del carattere della legenda** in un grafico, Aspose.Slides per Java ti offre il pieno controllo su ogni voce della legenda. Questo tutorial ti guida nella personalizzazione degli stili del testo della legenda, nell'applicazione di caratteri grassetto o corsivo e nell'impostazione di colori solidi affinché i tuoi grafici appaiano esattamente come desideri. Alla fine di questa guida sarai in grado di modificare il testo della legenda del grafico con sicurezza e integrare le modifiche in qualsiasi presentazione esistente.

**Cosa imparerai**
- Come **cambiare il colore del carattere della legenda** programmaticamente.
- Modi per **modificare il testo della legenda del grafico** come grassetto, corsivo e dimensione.
- Suggerimenti per applicare le modifiche a più grafici in una presentazione.
- Come integrare questi passaggi in un flusso di lavoro di automazione più ampio.

## Risposte rapide
- **Posso cambiare il colore di una singola voce della legenda?** Sì – accedi alla voce tramite il suo indice e imposta il formato di riempimento su un colore solido.  
- **Ho bisogno di una licenza per utilizzare queste API?** È necessaria una licenza temporanea o a pagamento per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **Quale versione di Java è supportata?** Aspose.Slides per Java 25.4+ funziona con JDK 16 e versioni successive.  
- **Le modifiche influenzeranno altri elementi del grafico?** No, la formattazione della legenda è isolata dallo stile delle serie di dati.  
- **È possibile l'elaborazione batch?** Assolutamente – itera attraverso le diapositive e i grafici per applicare le stesse impostazioni della legenda a tutto il deck.

## Cos'è cambiare il colore del carattere della legenda?
`change legend font color` si riferisce all'operazione programmatica di impostare il colore del testo delle voci della legenda di un grafico utilizzando l'API Aspose.Slides. Questa operazione aggiorna l'aspetto visivo della legenda senza modificare i dati sottostanti.

## Perché personalizzare le legende dei grafici?
Aspose.Slides supporta **oltre 50 formati di input e output** e può gestire presentazioni con **oltre 500 diapositive** mantenendo l'uso della memoria sotto i 200 MB. Personalizzare le legende migliora la leggibilità, rafforza i colori del brand e garantisce che i punti dati chiave risaltino — soprattutto in deck aziendali o educativi dove la chiarezza visiva guida le decisioni.

## Prerequisiti
- Libreria **Aspose.Slides per Java** (Versione 25.4 o successiva).  
- Java Development Kit (JDK) 16 o superiore.  
- Un IDE come IntelliJ IDEA, Eclipse o NetBeans.  
- Maven o Gradle per la gestione delle dipendenze.  
- Conoscenze di base di programmazione Java.

## Configurazione di Aspose.Slides per Java
Per iniziare a personalizzare le legende dei tuoi grafici, aggiungi la libreria al tuo progetto usando uno dei metodi seguenti.

### Maven
Aggiungi la seguente dipendenza al tuo file `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inserisci questa riga nel tuo file `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto
Puoi anche ottenere l'ultimo JAR da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Passaggi per l'acquisizione della licenza
- **Prova gratuita:** Inizia con una prova gratuita per esplorare le funzionalità di Aspose.Slides.  
- **Licenza temporanea:** Richiedi una licenza temporanea per una valutazione estesa.  
- **Acquisto:** Per accesso completo, considera l'acquisto di una licenza da [Aspose Purchase](https://purchase.aspose.com/buy).

#### Inizializzazione e configurazione di base
Dopo aver aggiunto la libreria al tuo progetto:
1. Inizializza Aspose.Slides nella tua applicazione Java.  
2. Carica una presentazione esistente o creane una nuova.

## Come cambiare il colore del carattere della legenda?
Per cambiare il colore del carattere della legenda, carica la presentazione, recupera l'oggetto grafico, ottieni la sua legenda, e poi modifica il formato del testo di ogni voce della legenda impostando il tipo di riempimento su solido e specificando il colore desiderato. Questa singola operazione aggiorna immediatamente il colore del testo della legenda senza dover ridisegnare l'intera diapositiva. Esempio: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Questo approccio funziona per qualsiasi tipo di grafico e non richiede il re‑rendering dell'intera diapositiva.

### Accesso e modifica delle proprietà del testo della legenda

#### Ancora di definizione
L'interfaccia `IChart` rappresenta un oggetto grafico su una diapositiva, e il suo metodo `getLegend()` restituisce un oggetto `ILegend` che contiene una collezione di elementi `ILegendEntry`.

#### Aggiungere un grafico alla tua presentazione
1. **Carica la presentazione:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Aggiungi un grafico a colonne raggruppate:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Personalizzazione delle proprietà del carattere
3. **Accedi al formato del testo della voce della legenda:**  
   Qui, `legendEntry` è un oggetto `ILegendEntry` che rappresenta una singola voce nella legenda del grafico.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Imposta gli stili grassetto e corsivo con un'altezza specifica:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Cambia il tipo di riempimento a colore solido per una migliore visibilità:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Salvataggio della presentazione
6. **Salva le modifiche:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Problemi comuni e risoluzione dei problemi
- Verifica che l'indice della voce della legenda corrisponda all'ordine delle serie nel tuo grafico.  
- Assicurati di utilizzare una versione della libreria che supporti `setSolidFillColor` (disponibile dalla versione 20.9).  

## Applicazioni pratiche
Personalizzare il testo della legenda è utile in molti scenari reali:

1. **Presentazioni aziendali:** Allinea i colori della legenda con il brand aziendale per un aspetto curato.  
2. **Materiali educativi:** Evidenzia le serie di dati chiave usando colori della legenda contrastanti.  
3. **Deck di marketing:** Enfatizza le metriche di performance con legende in grassetto e colorate per catturare l'attenzione degli stakeholder.  

Puoi anche automatizzare gli aggiornamenti della legenda prelevando i valori di colore da un database o da un file di configurazione.

## Considerazioni sulle prestazioni
Quando si elaborano deck di grandi dimensioni, tieni presente questi consigli:

- **Gestione efficiente della memoria:** Chiama `presentation.dispose()` dopo il salvataggio per rilasciare le risorse native.  
- **Carica solo le diapositive necessarie:** Usa `Presentation.load(String path, LoadOptions options)` con `LoadOptions.setLoadOnlySlideIds()` se ti serve un sottoinsieme.  
- **Elaborazione batch:** Raggruppa gli aggiornamenti della legenda per diapositiva per ridurre il numero di chiamate API e migliorare il throughput.

## Conclusione
Ora sai come **cambiare il colore del carattere della legenda** e **modificare il testo della legenda del grafico** usando Aspose.Slides per Java. Queste personalizzazioni migliorano la chiarezza visiva e ti aiutano a trasmettere i dati in modo più efficace. Sperimenta con diversi caratteri, dimensioni e colori per adeguarli alla guida di stile della tua presentazione, ed esplora altre funzionalità di styling dei grafici per creare deck davvero professionali.

**Passi successivi**
- Prova ad applicare lo stesso stile della legenda a grafici a torta e a linee.  
- Combina la personalizzazione della legenda con la formattazione delle etichette dati per un grafico completamente brandizzato.  

Pronto a elevare le tue presentazioni? Implementa i passaggi sopra e vedrai la differenza immediatamente!

## Sezione FAQ
1. **Come cambio il colore del testo di una voce della legenda?**  
   Usa `getFillFormat().setFillType(FillType.Solid)` e poi `setSolidFillColor(Color.YOUR_COLOR)` sul formato del testo della voce della legenda.

2. **Posso applicare queste modifiche a tutte le legende in una presentazione?**  
   Sì – itera attraverso ogni diapositiva, individua ogni grafico e aggiorna le voci della legenda all'interno di un ciclo.

3. **È possibile regolare dinamicamente la dimensione del carattere in base alla lunghezza del testo?**  
   Puoi calcolare la dimensione necessaria con `TextFrame.getTextFrameFormat().getFontHeight()` e impostarla tramite `setFontHeight(double)`.

4. **Cosa fare se riscontro problemi con l'indicizzazione delle voci della legenda?**  
   Verifica che l'indice utilizzato corrisponda all'ordine delle serie; ricorda che gli indici partono da zero.

5. **Dove posso trovare più esempi di Aspose.Slides?**  
   Esplora la [Aspose Documentation](https://reference.aspose.com/slides/java/) per guide complete e riferimenti API.

**Domande aggiuntive**

**D: Cambiare il colore del carattere della legenda influisce sui file PDF esportati?**  
R: No, la modifica del colore è preservata in tutti i formati di esportazione supportati da Aspose.Slides, inclusi PDF e PPTX.

**D: Posso usare un gradiente invece di un colore solido?**  
R: Sì – imposta `FillType.Gradient` e configura le fermate del gradiente tramite `getGradientStyle()`.

**D: Quante voci della legenda può avere un grafico?**  
R: Un grafico può avere fino a 256 voci della legenda, limitato solo dal numero di serie di dati aggiunte.

## Risorse
- **Documentazione:** Guida completa sull'uso delle funzionalità di Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Accedi all'ultima versione di Aspose.Slides per Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Acquisto:** Acquista una licenza per sbloccare tutte le funzionalità ([Link](https://purchase.aspose.com/buy)).  
- **Prova gratuita & licenza temporanea:** Inizia con le prove gratuite e richiedi licenze temporanee ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Supporto:** Ottieni aiuto dalla community sul forum di supporto di Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Tutorial correlati

- [Migliorare i grafici PowerPoint: personalizzazione di caratteri e assi con Aspose.Slides per Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides per Java: guida a riquadri di testo dinamici e personalizzazione dei caratteri](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animare i grafici PowerPoint usando Aspose.Slides per Java – Guida passo‑passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}