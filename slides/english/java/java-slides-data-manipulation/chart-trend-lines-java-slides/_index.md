---
title: Chart Trend Lines in Java Slides
linktitle: Chart Trend Lines in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add various trend lines to Java Slides using Aspose.Slides for Java. Step-by-step guide with code examples for effective data visualization.
weight: 15
url: /java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Chart Trend Lines in Java Slides: A Step-by-Step Guide

In this comprehensive guide, we will explore how to create chart trend lines in Java Slides using Aspose.Slides for Java. Chart trend lines can be a valuable addition to your presentations, helping to visualize and analyze data trends effectively. We'll walk you through the process with clear explanations and code examples.

## Prerequisites

Before we dive into creating chart trend lines, make sure you have the following prerequisites in place:

- Java Development Environment
- Aspose.Slides for Java Library
- A Code Editor of Your Choice

## Step 1: Getting Started

Let's begin by setting up the necessary environment and creating a new presentation:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Creating empty presentation
Presentation pres = new Presentation();
```

We've initialized our presentation, and now we're ready to add a clustered column chart:

```java
// Creating a clustered column chart
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Step 2: Adding Exponential Trend Line

Let's start by adding an exponential trend line to our chart series:

```java
// Adding exponential trend line for chart series 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Step 3: Adding Linear Trend Line

Next, we'll add a linear trend line to our chart series:

```java
// Adding linear trend line for chart series 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Step 4: Adding Logarithmic Trend Line

Now, let's add a logarithmic trend line to a different chart series:

```java
// Adding logarithmic trend line for chart series 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Step 5: Adding Moving Average Trend Line

We can also add a moving average trend line:

```java
// Adding moving average trend line for chart series 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Step 6: Adding Polynomial Trend Line

Adding a polynomial trend line:

```java
// Adding polynomial trend line for chart series 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Step 7: Adding Power Trend Line

Finally, let's add a power trend line:

```java
// Adding power trend line for chart series 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Step 8: Saving the Presentation

Now that we've added various trend lines to our chart, let's save the presentation:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Congratulations! You have successfully created a presentation with different types of trend lines in Java Slides using Aspose.Slides for Java.

## Complete Source Code For Chart Trend Lines in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Creating empty presentation
Presentation pres = new Presentation();
// Creating a clustered column chart
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Adding ponential trend line for chart series 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Adding Linear trend line for chart series 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Adding Logarithmic trend line for chart series 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Adding MovingAverage trend line for chart series 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Adding Polynomial trend line for chart series 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Adding Power trend line for chart series 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Saving presentation
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusion

In this tutorial, we've learned how to add different types of trend lines to charts in Java Slides using the Aspose.Slides for Java library. Whether you're working on data analysis or creating informative presentations, the ability to visualize trends can be a powerful tool.

## FAQ's

### How do I change the color of a trend line in Aspose.Slides for Java?

To change the color of a trend line, you can use the `getSolidFillColor().setColor(Color)` method, as shown in the example for adding a linear trend line.

### Can I add multiple trend lines to a single chart series?

Yes, you can add multiple trend lines to a single chart series. Simply call the `getTrendLines().add()` method for each trend line you want to add.

### How do I remove a trend line from a chart in Aspose.Slides for Java?

To remove a trend line from a chart, you can use the `removeAt(int index)` method, specifying the index of the trend line you want to remove.

### Is it possible to customize the trend line equation display?

Yes, you can customize the trend line equation display using the `setDisplayEquation(boolean)` method, as demonstrated in the example.

### How can I access more resources and examples for Aspose.Slides for Java?

You can access additional resources, documentation, and examples for Aspose.Slides for Java on the [Aspose website](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
