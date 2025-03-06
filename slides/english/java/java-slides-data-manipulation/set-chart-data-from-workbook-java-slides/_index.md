---
title: Set Chart Data From Workbook in Java Slides
linktitle: Set Chart Data From Workbook in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set chart data from an Excel workbook in Java Slides using Aspose.Slides. Step-by-step guide with code examples for dynamic presentations.
weight: 15
url: /java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Set Chart Data From Workbook in Java Slides

Aspose.Slides for Java is a powerful library that allows developers to work with PowerPoint presentations programmatically. It provides extensive features for creating, manipulating, and managing PowerPoint slides. One common requirement when working with presentations is to set chart data dynamically from an external data source, such as an Excel workbook. In this tutorial, we will demonstrate how to achieve this using Java.

## Prerequisites

Before we dive into the implementation, make sure you have the following prerequisites:

- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library added to your project.
- An Excel workbook with the data you want to use for the chart.

## Step 1: Create a Presentation

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

We start by creating a new PowerPoint presentation using Aspose.Slides for Java.

## Step 2: Add a Chart

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Next, we add a chart to one of the slides in the presentation. In this example, we are adding a pie chart, but you can choose the chart type that suits your needs.

## Step 3: Clear Chart Data

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

We clear any existing data from the chart to prepare it for new data from the Excel workbook.

## Step 4: Load Excel Workbook

```java
Workbook workbook = new Workbook("Your Document Directory";
```

We load the Excel workbook that contains the data we want to use for the chart. Replace `"book1.xlsx"` with the path to your Excel file.

## Step 5: Write Workbook Stream to Chart Data

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

We convert the Excel workbook data into a stream and write it to the chart data.

## Step 6: Set Chart Data Range

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

We specify the range of cells from the Excel workbook that should be used as data for the chart. Adjust the range as needed for your data.

## Step 7: Customize Chart Series

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

You can customize various properties of the chart series to match your requirements. In this example, we enable varied colors for the chart series.

## Step 8: Save the Presentation

```java
pres.save(outPath, SaveFormat.Pptx);
```

Finally, we save the presentation with the updated chart data to the specified output path.

## Complete Source Code For Set Chart Data From Workbook in Java Slides

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, we have learned how to set chart data from an Excel workbook in Java Slides using the Aspose.Slides for Java library. By following the step-by-step guide and using the provided source code examples, you can easily integrate dynamic chart data into your PowerPoint presentations.

## FAQ's

### How can I customize the appearance of the chart in my presentation?

You can customize the appearance of the chart by modifying properties such as colors, fonts, labels, and more. Refer to the Aspose.Slides for Java documentation for detailed information on chart customization options.

### Can I use data from a different Excel file for the chart?

Yes, you can use data from any Excel file by specifying the correct file path when loading the workbook in the code.

### What other types of charts can I create with Aspose.Slides for Java?

Aspose.Slides for Java supports various chart types, including bar charts, line charts, scatter charts, and more. You can choose the chart type that best suits your data representation needs.

### Is it possible to update the chart data dynamically in a running presentation?

Yes, you can update chart data dynamically in a presentation by modifying the underlying workbook and then refreshing the chart data.

### Where can I find more examples and resources for working with Aspose.Slides for Java?

You can explore additional examples and resources on the [Aspose website](https://www.aspose.com/). Additionally, the Aspose.Slides for Java documentation provides comprehensive guidance on working with the library.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
