---
"description": "Scopri come creare grafici radar nelle presentazioni Java di PowerPoint utilizzando Aspose.Slides per Java API."
"linktitle": "Creazione di grafici radar in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Creazione di grafici radar in Java Slides"
"url": "/it/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Creazione di grafici radar in Java Slides


## Introduzione alla creazione di un grafico radar in Java Slides

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico radar utilizzando l'API Aspose.Slides per Java. I grafici radar sono utili per visualizzare i dati in uno schema circolare, facilitando il confronto di più serie di dati. Forniremo istruzioni dettagliate insieme al codice sorgente Java.

## Prerequisiti

Prima di iniziare, assicurati di aver integrato la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Fase 1: Impostazione della presentazione

Iniziamo creando una nuova presentazione PowerPoint e aggiungendovi una diapositiva.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiunta di un grafico radar

Successivamente, aggiungeremo un grafico radar alla diapositiva. Ne specificheremo la posizione e le dimensioni.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Passaggio 3: impostazione dei dati del grafico

Ora imposteremo i dati del grafico. Ciò comporta la creazione di una cartella di lavoro dati, l'aggiunta di categorie e l'aggiunta di serie.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Imposta il titolo del grafico
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Elimina le serie e le categorie generate di default
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Aggiunta di nuove categorie
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Aggiunta di nuove serie
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Fase 4: Popolamento dei dati della serie

Adesso popoleremo i dati della serie per il nostro grafico radar.

```java
// Popola i dati della serie per la serie 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Imposta il colore della serie
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Popola i dati della serie per la serie 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Imposta il colore della serie
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Passaggio 5: personalizzazione degli assi e delle legende

Personalizziamo gli assi e le legende del nostro grafico radar.

```java
// Imposta la posizione della legenda
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Impostazione delle proprietà del testo dell'asse delle categorie
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Impostazione delle proprietà del testo delle legende
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Impostazione delle proprietà del testo dell'asse dei valori
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Impostazione del formato del numero dell'asse dei valori
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Impostazione del valore dell'unità principale del grafico
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Passaggio 6: salvataggio della presentazione

Infine, salva la presentazione generata con il grafico radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Ecco fatto! Hai creato con successo un grafico radar in una presentazione PowerPoint utilizzando Aspose.Slides per Java. Ora puoi personalizzare ulteriormente questo esempio in base alle tue esigenze specifiche.

## Codice sorgente completo per la creazione di grafici radar in Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Accedi alla prima diapositiva
	ISlide sld = pres.getSlides().get_Item(0);
	// Aggiungi grafico radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Impostazione dell'indice del foglio dati del grafico
	int defaultWorksheetIndex = 0;
	// Ottenere i dati del grafico Foglio di lavoro
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Imposta il titolo del grafico
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Elimina le serie e le categorie generate di default
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Aggiunta di nuove categorie
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Aggiunta di nuove serie
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Ora popolamento dei dati della serie
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Imposta il colore della serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ora sto popolando un'altra serie di dati
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Imposta il colore della serie
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Imposta la posizione della legenda
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Impostazione delle proprietà del testo dell'asse delle categorie
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Impostazione delle proprietà del testo delle legende
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Impostazione delle proprietà del testo dell'asse dei valori
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Impostazione del formato del numero dell'asse dei valori
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Impostazione del valore dell'unità principale del grafico
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Salva la presentazione generata
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato a creare un grafico radar in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi applicare questi concetti per visualizzare e presentare i tuoi dati in modo efficace nelle tue applicazioni Java.

## Domande frequenti

### Come posso cambiare il titolo del grafico?

Per cambiare il titolo del grafico, modifica la seguente riga:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Posso aggiungere altre serie di dati al grafico radar?

Sì, puoi aggiungere altre serie di dati seguendo i passaggi del "Passaggio 3" e del "Passaggio 4" per ogni serie aggiuntiva che desideri includere.

### Come posso personalizzare i colori del grafico?

È possibile personalizzare i colori della serie modificando le linee che impostano il `SolidFillColor` proprietà per ogni serie. Ad esempio:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Come posso modificare le etichette e la formattazione degli assi?

Fare riferimento al "Passaggio 5" per personalizzare le etichette e la formattazione degli assi, inclusi colore e dimensione del carattere.

### Come posso salvare il grafico in un formato di file diverso?

È possibile modificare il formato di output modificando l'estensione del file in `outPath` variabile e utilizzando l'appropriato `SaveFormat`Ad esempio, per salvare come PDF, utilizzare `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}