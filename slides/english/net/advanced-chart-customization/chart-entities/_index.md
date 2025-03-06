---
title: Creating Beautiful Charts with Aspose.Slides for .NET
linktitle: Chart Entities and Formatting
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn how to create stunning charts with Aspose.Slides for .NET. Elevate your data visualization game with our step-by-step guide.
weight: 13
url: /net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creating Beautiful Charts with Aspose.Slides for .NET


In today's data-driven world, effective data visualization is key to conveying information to your audience. Aspose.Slides for .NET is a powerful library that enables you to create stunning presentations and slides, including eye-catching charts. In this tutorial, we will walk you through the process of creating beautiful charts using Aspose.Slides for .NET. We will break down each example into multiple steps to help you understand and implement chart entities and formatting. So, let's get started!

## Prerequisites

Before we dive into creating beautiful charts with Aspose.Slides for .NET, you'll need to ensure that you have the following prerequisites in place:

1. Aspose.Slides for .NET: Make sure you have the Aspose.Slides for .NET library installed. You can download it from the [website](https://releases.aspose.com/slides/net/).

2. Development Environment: You should have a working development environment with Visual Studio or any other IDE that supports .NET development.

3. Basic C# Knowledge: Familiarity with C# programming is essential for this tutorial.

Now that we have our prerequisites sorted, let's proceed to create beautiful charts with Aspose.Slides for .NET.

## Import Namespaces

First, you need to import the necessary namespaces to work with Aspose.Slides for .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Step 1: Create a Presentation

We start by creating a new presentation to work with. This presentation will serve as the canvas for our chart.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create directory if it is not already present.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instantiating presentation
Presentation pres = new Presentation();
```

## Step 2: Access the First Slide

Let's access the first slide in the presentation where we will place our chart.

```csharp
// Accessing the first slide
ISlide slide = pres.Slides[0];
```

## Step 3: Add a Sample Chart

Now, we will add a sample chart to our slide. In this example, we'll create a line chart with markers.

```csharp
// Adding the sample chart
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Step 4: Set Chart Title

We'll give our chart a title, making it more informative and visually appealing.

```csharp
// Setting Chart Title
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Step 5: Customize Vertical Axis Grid Lines

In this step, we'll customize the vertical axis grid lines to make our chart more visually appealing.

```csharp
// Setting Major grid lines format for value axis
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Setting Minor grid lines format for value axis
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Setting value axis number format
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Step 6: Define Vertical Axis Range

In this step, we'll set the maximum, minimum, and unit values for the vertical axis.

```csharp
// Setting chart maximum, minimum values
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Step 7: Customize Vertical Axis Text

We will now customize the appearance of text on the vertical axis.

```csharp
// Setting Value Axis Text Properties
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Setting value axis title
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Step 8: Customize Horizontal Axis Grid Lines

Now, let's customize the grid lines for the horizontal axis.

```csharp
// Setting Major grid lines format for Category axis
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Setting Minor grid lines format for Category axis
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Setting Category Axis Text Properties
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Step 9: Customize Horizontal Axis Labels

In this step, we'll adjust the position and rotation of horizontal axis labels.

```csharp
// Setting category axis label position
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Setting category axis label rotation angle
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Step 10: Customize Legends

Let's enhance the legends in our chart for better readability.

```csharp
// Setting Legends Text Properties
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Set show chart legends without overlapping chart
chart.Legend.Overlay = true;
```

## Step 11: Customize Chart Background

We will customize the background colors of the chart, back wall, and floor.

```csharp
// Setting chart back wall color
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Setting Plot area color
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Step 12: Save the Presentation

Finally, let's save our presentation with the formatted chart.

```csharp
// Save Presentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Creating beautiful and informative charts in your presentations is now easier than ever with Aspose.Slides for .NET. In this tutorial, we've covered the essential steps to customize various aspects of a chart, making it visually appealing and informative. With these techniques, you can create stunning charts that effectively convey your data to your audience.

Start experimenting with Aspose.Slides for .NET and take your data visualization to the next level!

## Frequently Asked Questions

### 1. What is Aspose.Slides for .NET?

Aspose.Slides for .NET is a powerful library that allows .NET developers to create, manipulate, and convert Microsoft PowerPoint presentations. It provides a wide range of features for working with slides, shapes, charts, and more.

### 2. Where can I download Aspose.Slides for .NET?

You can download Aspose.Slides for .NET from the website [here](https://releases.aspose.com/slides/net/).

### 3. Is there a free trial available for Aspose.Slides for .NET?

Yes, you can get a free trial of Aspose.Slides for .NET from [here](https://releases.aspose.com/).

### 4. How can I get a temporary license for Aspose.Slides for .NET?

If you need a temporary license, you can obtain one from [this link](https://purchase.aspose.com/temporary-license/).

### 5. Is there a community or support forum for Aspose.Slides for .NET?

Yes, you can find the Aspose.Slides community and support forum [here](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
