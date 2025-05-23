---
"description": "Scopri come aggiungere barre di errore personalizzate ai grafici di PowerPoint in Java Slides utilizzando Aspose.Slides. Guida dettagliata con codice sorgente per una visualizzazione precisa dei dati."
"linktitle": "Aggiungi errore personalizzato in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungi errore personalizzato in Java Slides"
"url": "/it/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi errore personalizzato in Java Slides


## Introduzione all'aggiunta di barre di errore personalizzate in Java Slides utilizzando Aspose.Slides

In questo tutorial imparerai come aggiungere barre di errore personalizzate a un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Le barre di errore sono utili per visualizzare la variabilità o l'incertezza nei punti dati di un grafico.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Libreria Aspose.Slides per Java installata e configurata nel progetto.
- È stato configurato un ambiente di sviluppo Java.

## Passaggio 1: creare una presentazione vuota

Per prima cosa, crea una presentazione PowerPoint vuota.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di una presentazione vuota
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungere un grafico a bolle

Ora aggiungeremo un grafico a bolle alla presentazione.

```java
// Creazione di un grafico a bolle
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Passaggio 3: aggiungere barre di errore personalizzate

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

In questo passaggio, accederemo ai punti dati della serie del grafico e imposteremo i valori delle barre di errore personalizzate per ciascun punto.

```java
// Accesso ai punti dati delle serie di grafici e impostazione dei valori delle barre di errore per i singoli punti
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Impostazione delle barre di errore per i punti delle serie del grafico
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Passaggio 5: Salva la presentazione

Infine, salva la presentazione con le barre di errore personalizzate.

```java
// Salvataggio della presentazione
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai aggiunto con successo barre di errore personalizzate a un grafico in una presentazione di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per aggiungere un errore personalizzato nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
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
	// Impostazione delle barre di errore per i punti delle serie del grafico
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

In questo tutorial completo, hai imparato come migliorare le tue presentazioni PowerPoint aggiungendo barre di errore personalizzate ai grafici utilizzando Aspose.Slides per Java. Le barre di errore forniscono informazioni preziose sulla variabilità e l'incertezza dei dati, rendendo i tuoi grafici più informativi e visivamente accattivanti.

## Domande frequenti

### Come posso personalizzare l'aspetto delle barre di errore?

È possibile personalizzare l'aspetto delle barre di errore modificandone le proprietà `IErrorBarsFormat` oggetto, come lo stile della linea, il colore della linea e la larghezza della barra di errore.

### Posso aggiungere barre di errore ad altri tipi di grafici?

Sì, puoi aggiungere barre di errore a vari tipi di grafici supportati da Aspose.Slides per Java, inclusi grafici a barre, grafici a linee e grafici a dispersione.

### Come posso impostare valori diversi per la barra di errore per ogni punto dati?

È possibile scorrere i punti dati e impostare valori personalizzati della barra di errore per ciascun punto, come mostrato nel codice sopra.

### È possibile nascondere le barre di errore per punti dati specifici?

Sì, puoi controllare la visibilità delle barre di errore per i singoli punti dati impostando `setVisible` proprietà del `IErrorBarsFormat` oggetto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}