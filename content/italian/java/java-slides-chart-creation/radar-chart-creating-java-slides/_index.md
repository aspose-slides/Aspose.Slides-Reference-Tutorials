---
title: Creazione di grafici radar in diapositive Java
linktitle: Creazione di grafici radar in diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare grafici radar nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per l'API Java.
type: docs
weight: 10
url: /it/java/chart-creation/radar-chart-creating-java-slides/
---

## Introduzione alla creazione di un grafico radar in Diapositive Java

In questo tutorial, ti guideremo attraverso il processo di creazione di un grafico radar utilizzando l'API Aspose.Slides per Java. I grafici radar sono utili per visualizzare i dati in uno schema circolare, semplificando il confronto di più serie di dati. Forniremo istruzioni dettagliate insieme al codice sorgente Java.

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java integrata nel tuo progetto. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: impostazione della presentazione

Iniziamo configurando una nuova presentazione PowerPoint e aggiungendovi una diapositiva.

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiunta di un grafico radar

Successivamente, aggiungeremo un grafico radar alla diapositiva. Specificheremo la posizione e le dimensioni del grafico.

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

// Elimina le serie e le categorie generate predefinite
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

## Passaggio 4: popolamento dei dati della serie

Ora popoleremo i dati della serie per il nostro grafico radar.

```java
// Compilare i dati della serie per la serie 1
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

// Compilare i dati della serie per la serie 2
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

## Passaggio 5: personalizzazione di assi e leggende

Personalizziamo l'asse e le legende per il nostro grafico radar.

```java
//Imposta la posizione della legenda
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

// Impostazione del valore unitario principale del grafico
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Passaggio 6: salvataggio della presentazione

Infine, salva la presentazione generata con il grafico radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Questo è tutto! Hai creato con successo un grafico radar in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Ora puoi personalizzare ulteriormente questo esempio per adattarlo alle tue esigenze specifiche.

## Codice sorgente completo per la creazione di grafici radar in diapositive Java

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Accedi alla prima diapositiva
	ISlide sld = pres.getSlides().get_Item(0);
	// Aggiungi il grafico radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Impostazione dell'indice della scheda grafica
	int defaultWorksheetIndex = 0;
	// Ottenere il foglio di lavoro dei dati del grafico
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Imposta il titolo del grafico
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Elimina le serie e le categorie generate predefinite
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
	// Ora popolano i dati delle serie
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
	// Ora stiamo compilando un'altra serie di dati
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
	//Imposta la posizione della legenda
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
	// Impostazione del valore unitario principale del grafico
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

In questo tutorial hai imparato come creare un grafico radar in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Puoi applicare questi concetti per visualizzare e presentare i tuoi dati in modo efficace nelle tue applicazioni Java.

## Domande frequenti

### Come posso cambiare il titolo del grafico?

Per cambiare il titolo del grafico, modificare la seguente riga:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Posso aggiungere più serie di dati al grafico radar?

Sì, puoi aggiungere più serie di dati seguendo i passaggi del "Passaggio 3" e del "Passaggio 4" per ogni serie aggiuntiva che desideri includere.

### Come posso personalizzare i colori del grafico?

 È possibile personalizzare i colori della serie modificando le righe che impostano il`SolidFillColor` proprietà per ciascuna serie. Per esempio:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Come posso modificare le etichette e la formattazione degli assi?

Fare riferimento al "Passaggio 5" per personalizzare le etichette e la formattazione degli assi, inclusi la dimensione e il colore del carattere.

### Come faccio a salvare il grafico in un formato di file diverso?

 È possibile modificare il formato di output modificando l'estensione del file nel file`outPath`variabile e utilizzando l'appropriato`SaveFormat` . Ad esempio, per salvare come PDF, utilizzare`SaveFormat.Pdf`.