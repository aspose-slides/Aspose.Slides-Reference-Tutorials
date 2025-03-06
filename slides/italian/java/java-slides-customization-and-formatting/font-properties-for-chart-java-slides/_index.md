---
title: Proprietà dei caratteri per il grafico nelle diapositive Java
linktitle: Proprietà dei caratteri per il grafico nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Migliora le proprietà dei caratteri del grafico nelle diapositive Java con Aspose.Slides per Java. Personalizza la dimensione, lo stile e il colore del carattere per presentazioni di grande impatto.
weight: 11
url: /it/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione alle proprietà dei caratteri per il grafico nelle diapositive Java

Questa guida ti guiderà attraverso l'impostazione delle proprietà dei caratteri per un grafico in Java Slides utilizzando Aspose.Slides. Puoi personalizzare la dimensione del carattere e l'aspetto del testo del grafico per migliorare l'impatto visivo delle tue presentazioni.

## Prerequisiti

 Prima di iniziare, assicurati di avere Aspose.Slides per Java API integrato nel tuo progetto. Se non lo hai già fatto, puoi scaricarlo dal[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).

## Passaggio 1: crea una presentazione

Innanzitutto, crea una nuova presentazione utilizzando il seguente codice:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico

Ora aggiungiamo un istogramma a colonne raggruppate alla tua presentazione:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Qui stiamo aggiungendo un istogramma in cluster alla prima diapositiva alle coordinate (100, 100) con una larghezza di 500 unità e un'altezza di 400 unità.

## Passaggio 3: personalizzare le proprietà del carattere

Successivamente, personalizzeremo le proprietà del carattere del grafico. In questo esempio, impostiamo la dimensione del carattere su 20 per tutto il testo del grafico:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Questo codice imposta la dimensione del carattere su 20 punti per tutto il testo all'interno del grafico.

## Passaggio 4: mostra le etichette dati

Puoi anche mostrare le etichette dei dati sul grafico utilizzando il seguente codice:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Questa riga di codice abilita le etichette dati per la prima serie nel grafico, visualizzando i valori nelle colonne del grafico.

## Passaggio 5: salva la presentazione

Infine, salva la presentazione con le proprietà personalizzate del carattere del grafico:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Questo codice salverà la presentazione nella directory specificata con il nome file "FontPropertiesForChart.pptx".

## Codice sorgente completo per le proprietà dei caratteri per il grafico nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

In questo tutorial, hai imparato come personalizzare le proprietà del carattere per un grafico in Java Slides utilizzando Aspose.Slides per Java. Puoi applicare queste tecniche per migliorare l'aspetto dei tuoi grafici e delle tue presentazioni. Esplora più opzioni nel[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).

## Domande frequenti

### Come posso cambiare il colore del carattere?

 Per modificare il colore del carattere per il testo del grafico, utilizzare`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , sostituendo`Color.RED` con il colore desiderato.

### Posso cambiare lo stile del carattere (grassetto, corsivo, ecc.)?

 Sì, puoi cambiare lo stile del carattere. Utilizzo`chart.getTextFormat().getPortionFormat().setFontBold(true);` per rendere il carattere in grassetto. Allo stesso modo, puoi usare`setFontItalic(true)` per renderlo corsivo.

### Come posso personalizzare le proprietà dei caratteri per elementi specifici del grafico?

Per personalizzare le proprietà dei caratteri per elementi specifici del grafico, come le etichette degli assi o il testo della legenda, puoi accedere a tali elementi e impostare le relative proprietà dei caratteri utilizzando metodi simili a quelli mostrati sopra.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
