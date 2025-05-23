---
"description": "Migliora le proprietà dei caratteri dei grafici nelle diapositive Java con Aspose.Slides per Java. Personalizza dimensioni, stile e colore dei caratteri per presentazioni di grande impatto."
"linktitle": "Proprietà del carattere per il grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Proprietà del carattere per il grafico in Java Slides"
"url": "/it/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Proprietà del carattere per il grafico in Java Slides


## Introduzione alle proprietà dei caratteri per i grafici in Java Slides

Questa guida ti guiderà nell'impostazione delle proprietà del carattere per un grafico in Java Slides utilizzando Aspose.Slides. Puoi personalizzare le dimensioni e l'aspetto del carattere del testo del grafico per migliorare l'aspetto visivo delle tue presentazioni.

## Prerequisiti

Prima di iniziare, assicurati di aver integrato l'API Aspose.Slides per Java nel tuo progetto. Se non l'hai già fatto, puoi scaricarla da [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: creare una presentazione

Per prima cosa, crea una nuova presentazione utilizzando il seguente codice:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico

Ora aggiungiamo un grafico a colonne raggruppate alla tua presentazione:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Qui aggiungiamo un grafico a colonne raggruppate alla prima diapositiva alle coordinate (100, 100) con una larghezza di 500 unità e un'altezza di 400 unità.

## Passaggio 3: personalizzare le proprietà del carattere

Successivamente, personalizzeremo le proprietà del carattere del grafico. In questo esempio, imposteremo la dimensione del carattere a 20 per tutto il testo del grafico:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Questo codice imposta la dimensione del carattere a 20 punti per tutto il testo nel grafico.

## Passaggio 4: Mostra etichette dati

È anche possibile visualizzare le etichette dei dati sul grafico utilizzando il seguente codice:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Questa riga di codice abilita le etichette dati per la prima serie nel grafico, visualizzando i valori nelle colonne del grafico.

## Passaggio 5: Salva la presentazione

Infine, salva la presentazione con le proprietà personalizzate del carattere del grafico:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Questo codice salverà la presentazione nella directory specificata con il nome file "FontPropertiesForChart.pptx".

## Codice sorgente completo per le proprietà dei caratteri per i grafici in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato a personalizzare le proprietà del carattere per un grafico in Java Slides utilizzando Aspose.Slides per Java. Puoi applicare queste tecniche per migliorare l'aspetto di grafici e presentazioni. Esplora altre opzioni in [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

## Domande frequenti

### Come posso cambiare il colore del carattere?

Per cambiare il colore del carattere per il testo del grafico, utilizzare `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, sostituendo `Color.RED` con il colore desiderato.

### Posso cambiare lo stile del carattere (grassetto, corsivo, ecc.)?

Sì, puoi cambiare lo stile del carattere. Usa `chart.getTextFormat().getPortionFormat().setFontBold(true);` per rendere il carattere in grassetto. Allo stesso modo, puoi usare `setFontItalic(true)` per renderlo corsivo.

### Come posso personalizzare le proprietà dei caratteri per specifici elementi del grafico?

Per personalizzare le proprietà del carattere per specifici elementi del grafico, come le etichette degli assi o il testo della legenda, è possibile accedere a tali elementi e impostarne le proprietà del carattere utilizzando metodi simili a quelli mostrati sopra.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}