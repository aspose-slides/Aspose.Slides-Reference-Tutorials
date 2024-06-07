---
title: Aggiungi errore personalizzato nelle diapositive Java
linktitle: Aggiungi errore personalizzato nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere barre di errore personalizzate ai grafici di PowerPoint in Diapositive Java utilizzando Aspose.Slides. Guida passo passo con codice sorgente per una visualizzazione precisa dei dati.
type: docs
weight: 11
url: /it/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Introduzione all'aggiunta di barre di errore personalizzate nelle diapositive Java utilizzando Aspose.Slides

In questo tutorial imparerai come aggiungere barre di errore personalizzate a un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Le barre di errore sono utili per visualizzare la variabilità o l'incertezza nei punti dati su un grafico.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Aspose.Slides per la libreria Java installata e configurata nel tuo progetto.
- Predisposizione di un ambiente di sviluppo Java.

## Passaggio 1: crea una presentazione vuota

Innanzitutto, crea una presentazione PowerPoint vuota.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi un grafico a bolle

Successivamente, aggiungeremo un grafico a bolle alla presentazione.

```java
// Creazione di un grafico a bolle
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Passaggio 3: aggiungi barre di errore personalizzate

Ora aggiungiamo barre di errore personalizzate alla serie di grafici.

```java
// Aggiunta di barre di errore personalizzate e impostazione del loro formato
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Passaggio 4: impostare i dati delle barre di errore

In questo passaggio, accederemo ai punti dati della serie di grafici e imposteremo i valori delle barre di errore personalizzate per ciascun punto.

```java
// Accesso ai punti dati delle serie di grafici e impostazione dei valori delle barre di errore per i singoli punti
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Impostazione delle barre di errore per i punti delle serie di grafici
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Passaggio 5: salva la presentazione

Infine, salva la presentazione con le barre di errore personalizzate.

```java
// Salvataggio della presentazione
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai aggiunto con successo barre di errore personalizzate a un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per aggiungere errori personalizzati nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
try
{
	// Creazione di un grafico a bolle
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Aggiunta di barre di errore personalizzate e impostazione del relativo formato
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Accesso ai punti dati della serie di grafici e impostazione dei valori delle barre di errore per i singoli punti
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Impostazione delle barre di errore per i punti delle serie di grafici
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Salvataggio della presentazione
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial completo, hai imparato come migliorare le tue presentazioni PowerPoint aggiungendo barre di errore personalizzate ai grafici utilizzando Aspose.Slides per Java. Le barre di errore forniscono informazioni preziose sulla variabilità e sull'incertezza dei dati, rendendo i tuoi grafici più informativi e visivamente accattivanti.

## Domande frequenti

### Come posso personalizzare l'aspetto delle barre di errore?

 È possibile personalizzare l'aspetto delle barre di errore modificando le proprietà del file`IErrorBarsFormat` oggetto, ad esempio stile della linea, colore della linea e larghezza della barra di errore.

### Posso aggiungere barre di errore ad altri tipi di grafici?

Sì, puoi aggiungere barre di errore a vari tipi di grafici supportati da Aspose.Slides per Java, inclusi grafici a barre, grafici a linee e grafici a dispersione.

### Come posso impostare valori diversi della barra di errore per ciascun punto dati?

Puoi scorrere i punti dati e impostare valori personalizzati della barra di errore per ciascun punto, come mostrato nel codice sopra.

### È possibile nascondere le barre di errore per punti dati specifici?

Sì, puoi controllare la visibilità delle barre di errore per i singoli punti dati impostando il file`setVisible` proprietà del`IErrorBarsFormat` oggetto.