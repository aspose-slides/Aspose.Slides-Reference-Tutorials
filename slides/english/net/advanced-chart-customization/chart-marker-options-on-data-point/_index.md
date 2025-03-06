---
title: Using Chart Marker Options on Data Point in Aspose.Slides .NET
linktitle: Chart Marker Options on Data Point
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to enhance your PowerPoint charts using Aspose.Slides for .NET. Customize data point markers with images. Create engaging presentations.
weight: 11
url: /net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


When working with presentations and data visualization, Aspose.Slides for .NET offers a wide range of powerful features to create, customize, and manipulate charts. In this tutorial, we will explore how to use chart marker options on data points to enhance your chart presentations. This step-by-step guide will walk you through the process, starting from the prerequisites and importing namespaces, to breaking down each example into multiple steps.

## Prerequisites

Before we dive into using chart marker options on data points, ensure that you have the following prerequisites in place:

- Aspose.Slides for .NET: Make sure you have Aspose.Slides for .NET installed. You can download it from the [website](https://releases.aspose.com/slides/net/).

- Sample Presentation: For this tutorial, we'll use a sample presentation named "Test.pptx." You should have this presentation in your document directory.

Now, let's start by importing the necessary namespaces.

## Import Namespaces

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

We've imported the required namespaces and initialized our presentation. Now, let's proceed to use chart marker options on data points.

## Step 1: Creating the Default Chart

```csharp

// The path to the documents directory.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Creating the default chart
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

We create a default chart of type "LineWithMarkers" on the slide at a specified location and size.

## Step 2: Getting the Default Chart Data Worksheet Index

```csharp
// Getting the default chart data worksheet index
int defaultWorksheetIndex = 0;
```

Here, we obtain the index of the default chart data worksheet.

## Step 3: Getting the Chart Data Worksheet

```csharp
// Getting the chart data worksheet
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

We fetch the chart data workbook to work with chart data.

## Step 4: Modifying the Chart Series

```csharp
// Delete demo series
chart.ChartData.Series.Clear();

// Add new series
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In this step, we remove any existing demo series and add a new series named "Series 1" to the chart.

## Step 5: Setting Picture Fill for Data Points

```csharp
// Set the picture for the markers
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Take the first chart series
IChartSeries series = chart.ChartData.Series[0];

// Add new data points with picture fill
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

We set picture markers for data points, allowing you to customize how each data point appears on the chart.

## Step 6: Changing the Chart Series Marker Size

```csharp
// Changing the chart series marker size
series.Marker.Size = 15;
```

Here, we adjust the size of the chart series marker to make it visually appealing.

## Step 7: Saving the Presentation

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Finally, we save the presentation with the new chart settings.

## Conclusion

Aspose.Slides for .NET empowers you to create stunning chart presentations with various customization options. In this tutorial, we focused on using chart marker options on data points to enhance the visual representation of your data. With Aspose.Slides for .NET, you can take your presentations to the next level, making them more engaging and informative.

If you have any questions or need assistance with Aspose.Slides for .NET, feel free to visit the [Aspose.Slides documentation](https://reference.aspose.com/slides/net/) or reach out to the [Aspose community](https://forum.aspose.com/) for support.

## Frequently Asked Questions (FAQs)

### Can I use custom images as markers for data points in Aspose.Slides for .NET?
Yes, you can use custom images as markers for data points in Aspose.Slides for .NET, as demonstrated in this tutorial.

### How can I change the chart type in Aspose.Slides for .NET?
You can change the chart type by specifying a different `ChartType` when creating the chart, such as "Bar," "Pie," or "Area."

### Is Aspose.Slides for .NET compatible with the latest versions of PowerPoint?
Aspose.Slides for .NET is designed to work with various PowerPoint formats and is regularly updated to maintain compatibility with the latest PowerPoint versions.

### Where can I find more tutorials and resources for Aspose.Slides for .NET?
You can explore additional tutorials and resources in the [Aspose.Slides documentation](https://reference.aspose.com/slides/net/).

### Is there a trial version of Aspose.Slides for .NET available?
Yes, you can try Aspose.Slides for .NET by downloading a free trial version from [here](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
