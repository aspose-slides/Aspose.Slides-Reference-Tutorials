---
title: Exploring Chart Trend Lines in Aspose.Slides for .NET
linktitle: Chart Trend Lines
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to add various trend lines to charts using Aspose.Slides for .NET in this step-by-step guide. Enhance your data visualization skills with ease!
weight: 12
url: /net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


In the world of data visualization and presentation, incorporating charts can be a powerful way to convey information effectively. Aspose.Slides for .NET provides a feature-rich set of tools to work with charts, including the ability to add trend lines to your charts. In this tutorial, we will delve into the process of adding trend lines to a chart in a step-by-step manner using Aspose.Slides for .NET. 

## Prerequisites

Before we start working with Aspose.Slides for .NET, you'll need to ensure you have the following prerequisites in place:

1. Aspose.Slides for .NET: To access the library and use it, you must have Aspose.Slides for .NET installed. You can get the library from the [download page](https://releases.aspose.com/slides/net/).

2. Development Environment: You should have a development environment set up, preferably using a .NET integrated development environment like Visual Studio.

3. Basic Knowledge of C#: A fundamental understanding of C# programming is beneficial, as we will be using C# to work with Aspose.Slides for .NET.

Now that we've covered the prerequisites let's break down the process of adding trend lines to a chart step by step.

## Importing Namespaces

First, make sure you import the necessary namespaces into your C# project. These namespaces are essential for working with Aspose.Slides for .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Step 1: Create a Presentation

In this step, we create an empty presentation to work with.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create directory if it is not already present.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Creating empty presentation
Presentation pres = new Presentation();
```

## Step 2: Add a Chart to the Slide

Next, we add a clustered column chart to a slide.

```csharp
// Creating a clustered column chart
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Step 3: Add Trend Lines to the Chart

Now, we add various types of trend lines to the chart series.

### Adding an Exponential Trend Line

```csharp
// Adding exponential trend line for chart series 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Adding a Linear Trend Line

```csharp
// Adding linear trend line for chart series 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Adding a Logarithmic Trend Line

```csharp
// Adding logarithmic trend line for chart series 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Adding a Moving Average Trend Line

```csharp
// Adding moving average trend line for chart series 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Adding a Polynomial Trend Line

```csharp
// Adding polynomial trend line for chart series 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Adding a Power Trend Line

```csharp
// Adding power trend line for chart series 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Step 4: Save the Presentation

After adding trend lines to the chart, save the presentation.

```csharp
// Saving presentation
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

That's it! You've successfully added various trend lines to your chart using Aspose.Slides for .NET.

## Conclusion

Aspose.Slides for .NET is a versatile library that allows you to create and manipulate charts with ease. By following this step-by-step guide, you can add different types of trend lines to your charts, enhancing the visual representation of your data.

### FAQs

### Where can I find the documentation for Aspose.Slides for .NET?
You can access the documentation [here](https://reference.aspose.com/slides/net/).

### How can I download Aspose.Slides for .NET?
You can download Aspose.Slides for .NET from the download page [here](https://releases.aspose.com/slides/net/).

### Is there a free trial available for Aspose.Slides for .NET?
Yes, you can try Aspose.Slides for .NET for free by visiting [this link](https://releases.aspose.com/).

### Where can I purchase Aspose.Slides for .NET?
To purchase Aspose.Slides for .NET, visit the purchase page [here](https://purchase.aspose.com/buy).

### Do I need a temporary license for Aspose.Slides for .NET?
You can obtain a temporary license for Aspose.Slides for .NET from [this link](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
