---
"description": "Scopri come aggiungere colore ai punti dati nelle diapositive Java utilizzando Aspose.Slides per Java."
"linktitle": "Aggiungere colore ai punti dati nelle diapositive Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere colore ai punti dati nelle diapositive Java"
"url": "/it/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere colore ai punti dati nelle diapositive Java


## Introduzione all'aggiunta di colore ai punti dati in Java Slides

In questo tutorial, mostreremo come aggiungere colore ai punti dati nelle diapositive Java utilizzando Aspose.Slides per Java. Questa guida passo passo include esempi di codice sorgente per aiutarti a raggiungere questo obiettivo.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Ambiente di sviluppo Java
- Libreria Aspose.Slides per Java

## Passaggio 1: creare una nuova presentazione

Per prima cosa, creeremo una nuova presentazione utilizzando Aspose.Slides per Java. Questa presentazione servirà da contenitore per il nostro grafico.

```java
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico a raggiera

Ora aggiungiamo un grafico Sunburst alla presentazione. Specifichiamo il tipo, la posizione e le dimensioni del grafico.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Passaggio 3: accedere ai punti dati

Per modificare i punti dati nel grafico, dobbiamo accedere a `IChartDataPointCollection` oggetto.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Passaggio 4: personalizzare i punti dati

In questa fase, personalizzeremo punti dati specifici. Qui, cambieremo il colore dei punti dati e configureremo le impostazioni delle etichette.

```java
// Personalizza il punto dati 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Personalizza il punto dati 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Passaggio 5: Salva la presentazione

Infine, salva la presentazione con il grafico personalizzato.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai aggiunto con successo il colore a punti dati specifici in una diapositiva Java utilizzando Aspose.Slides per Java.

## Codice sorgente completo per aggiungere colore ai punti dati in Java Slides

```java
Presentation pres = new Presentation();
try
{
	// Percorso verso la directory dei documenti.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//FARE
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come aggiungere colore ai punti dati nelle diapositive Java utilizzando Aspose.Slides per Java. Puoi personalizzare ulteriormente grafici e presentazioni in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso cambiare il colore di altri punti dati?

Per modificare il colore di altri punti dati, puoi seguire un approccio simile a quello mostrato nel passaggio 4. Accedi al punto dati che vuoi personalizzare e modificane le impostazioni di colore ed etichetta.

### Posso personalizzare altri aspetti del grafico?

Sì, puoi personalizzare vari aspetti del grafico, inclusi caratteri, etichette, titoli e altro ancora. Fai riferimento a [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/) per opzioni di personalizzazione dettagliate.

### Dove posso trovare altri esempi e documentazione?

Puoi trovare altri esempi e documentazione dettagliata sull'utilizzo di Aspose.Slides per Java su [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/) sito web.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}