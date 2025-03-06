---
title: Setting Date Format For Category Axis in Java Slides
linktitle: Setting Date Format For Category Axis in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set a date format for the category axis in a PowerPoint chart using Aspose.Slides for Java. Step-by-step guide with source code.
weight: 26
url: /java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Setting Date Format For Category Axis in Java Slides

In this tutorial, we will learn how to set a date format for the category axis in a PowerPoint chart using Aspose.Slides for Java. Aspose.Slides for Java is a powerful library that allows you to create, manipulate, and manage PowerPoint presentations programmatically.

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.Slides for Java library (you can download it from [here](https://releases.aspose.com/slides/java/).
2. Java development environment set up.

## Step 1: Create a PowerPoint Presentation

First, we need to create a PowerPoint presentation where we will add a chart. Make sure you have imported the necessary Aspose.Slides classes.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Step 2: Add a Chart to the Slide

Now, let's add a chart to the PowerPoint slide. We will use an Area chart in this example.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Step 3: Prepare Chart Data

We will set up the chart data and categories. In this example, we will use date categories.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Adding date categories
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Adding data series
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Step 4: Customize Category Axis
Now, let's customize the category axis to display dates in a specific format (e.g., yyyy).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Step 5: Save the Presentation
Finally, save the PowerPoint presentation.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

That's it! You have successfully set a date format for the category axis in a PowerPoint chart using Aspose.Slides for Java.

## Complete Source Code For Setting Date Format For Category Axis in Java Slides

```java
	// The path to the documents directory.
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

##Conclusion

You have successfully customized the date format for the category axis in a Java Slides chart using Aspose.Slides for Java. This allows you to present date values in the desired format on your charts. Feel free to explore further customization options based on your specific requirements.

## FAQ's

### How do I change the date format for the category axis?

To change the date format for the category axis, use the `setNumberFormat` method on the category axis and provide the desired date format pattern, such as "yyyy-MM-dd" or "MM/yyyy". Make sure to set `setNumberFormatLinkedToSource(false)` to override the default format.

### Can I use different date formats for different charts in the same presentation?

Yes, you can set different date formats for category axes in different charts within the same presentation. Simply customize the category axis for each chart as needed.

### How do I add more data points to the chart?

To add more data points to the chart, use the `getDataPoints().addDataPointForLineSeries` method on the data series and provide the data values.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
