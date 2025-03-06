---
title: Impostazione del formato della data per l'asse delle categorie nelle diapositive Java
linktitle: Impostazione del formato della data per l'asse delle categorie nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare un formato di data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con il codice sorgente.
weight: 26
url: /it/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'impostazione del formato della data per l'asse delle categorie nelle diapositive Java

In questo tutorial impareremo come impostare un formato di data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides per Java è una potente libreria che ti consente di creare, manipolare e gestire presentazioni PowerPoint a livello di codice.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Aspose.Slides per la libreria Java (puoi scaricarla da[Qui](https://releases.aspose.com/slides/java/).
2. Configurazione dell'ambiente di sviluppo Java.

## Passaggio 1: crea una presentazione PowerPoint

Innanzitutto, dobbiamo creare una presentazione PowerPoint in cui aggiungeremo un grafico. Assicurati di aver importato le classi Aspose.Slides necessarie.

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico alla diapositiva

Ora aggiungiamo un grafico alla diapositiva di PowerPoint. In questo esempio utilizzeremo un grafico ad area.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Passaggio 3: preparare i dati del grafico

Imposteremo i dati e le categorie del grafico. In questo esempio utilizzeremo le categorie di date.

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

## Passaggio 4: personalizza l'asse delle categorie
Ora personalizziamo l'asse delle categorie per visualizzare le date in un formato specifico (ad esempio, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Passaggio 5: salva la presentazione
Infine, salva la presentazione di PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Questo è tutto! Hai impostato correttamente un formato di data per l'asse delle categorie in un grafico di PowerPoint utilizzando Aspose.Slides per Java.

## Codice sorgente completo per impostare il formato della data per l'asse delle categorie nelle diapositive Java

```java
	// Il percorso della directory dei documenti.
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

Hai personalizzato con successo il formato della data per l'asse delle categorie in un grafico di Diapositive Java utilizzando Aspose.Slides per Java. Ciò ti consente di presentare i valori delle date nel formato desiderato sui tuoi grafici. Sentiti libero di esplorare ulteriori opzioni di personalizzazione in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso modificare il formato della data per l'asse delle categorie?

 Per modificare il formato della data per l'asse delle categorie, utilizzare il file`setNumberFormat` sull'asse delle categorie e fornire il modello di formato della data desiderato, ad esempio "aaaa-MM-gg" o "MM/aaaa". Assicurati di impostare`setNumberFormatLinkedToSource(false)` per sovrascrivere il formato predefinito.

### Posso utilizzare formati di data diversi per grafici diversi nella stessa presentazione?

Sì, puoi impostare formati di data diversi per gli assi delle categorie in grafici diversi all'interno della stessa presentazione. Personalizza semplicemente l'asse delle categorie per ciascun grafico in base alle esigenze.

### Come faccio ad aggiungere più punti dati al grafico?

 Per aggiungere più punti dati al grafico, utilizzare il file`getDataPoints().addDataPointForLineSeries`metodo sulla serie di dati e fornire i valori dei dati.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
