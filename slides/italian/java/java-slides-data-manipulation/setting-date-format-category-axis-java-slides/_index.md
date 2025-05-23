---
"description": "Scopri come impostare un formato data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con codice sorgente."
"linktitle": "Impostazione del formato data per l'asse delle categorie in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Impostazione del formato data per l'asse delle categorie in Java Slides"
"url": "/it/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione del formato data per l'asse delle categorie in Java Slides


## Introduzione all'impostazione del formato data per l'asse delle categorie in Java Slides

In questo tutorial impareremo come impostare un formato data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che consente di creare, manipolare e gestire le presentazioni di PowerPoint a livello di codice.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Libreria Aspose.Slides per Java (puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
2. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: creare una presentazione PowerPoint

Per prima cosa, dobbiamo creare una presentazione PowerPoint in cui aggiungeremo un grafico. Assicuratevi di aver importato le classi Aspose.Slides necessarie.

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico alla diapositiva

Ora aggiungiamo un grafico alla diapositiva di PowerPoint. In questo esempio useremo un grafico ad area.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Passaggio 3: preparare i dati del grafico

Imposteremo i dati e le categorie del grafico. In questo esempio, useremo le categorie di data.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Aggiunta di categorie di date
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Aggiunta di serie di dati
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Passaggio 4: personalizzare l'asse delle categorie
Adesso personalizziamo l'asse delle categorie per visualizzare le date in un formato specifico (ad esempio, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Passaggio 5: Salva la presentazione
Infine, salva la presentazione PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Ecco fatto! Hai impostato correttamente un formato data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per l'impostazione del formato data per l'asse delle categorie in Java Slides

```java
	// Percorso verso la directory dei documenti.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Conclusione

Hai personalizzato con successo il formato della data per l'asse delle categorie in un grafico Java Slides utilizzando Aspose.Slides per Java. Questo ti consente di presentare i valori di data nel formato desiderato sui tuoi grafici. Non esitare a esplorare ulteriori opzioni di personalizzazione in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso modificare il formato della data per l'asse delle categorie?

Per modificare il formato della data per l'asse delle categorie, utilizzare `setNumberFormat` metodo sull'asse delle categorie e fornire il modello di formato data desiderato, ad esempio "aaaa-MM-gg" o "MM/aaaa". Assicurati di impostare `setNumberFormatLinkedToSource(false)` per sovrascrivere il formato predefinito.

### Posso utilizzare formati di data diversi per grafici diversi nella stessa presentazione?

Sì, puoi impostare formati di data diversi per gli assi delle categorie in grafici diversi all'interno della stessa presentazione. Personalizza semplicemente l'asse delle categorie per ogni grafico in base alle tue esigenze.

### Come posso aggiungere altri punti dati al grafico?

Per aggiungere più punti dati al grafico, utilizzare `getDataPoints().addDataPointForLineSeries` metodo sulla serie di dati e fornire i valori dei dati.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}