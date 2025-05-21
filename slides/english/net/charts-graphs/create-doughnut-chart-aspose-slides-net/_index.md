---
title: "Step-by-Step Guide&#58; Create Doughnut Chart with Aspose.Slides .NET | Charts & Graphs"
description: "Learn how to create dynamic doughnut charts using Aspose.Slides for .NET. Follow this guide for step-by-step instructions, including setup and advanced features."
date: "2025-04-15"
weight: 1
url: "/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
keywords:
- Aspose.Aspose.Slides
- Net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Step-by-Step Guide: Create Doughnut Chart with Aspose.Slides .NET

## Introduction

Imagine you're tasked with presenting data analysis results to your team or clients, and you need an engaging way to visualize the information. Enter the doughnut chart—a versatile tool that can transform raw numbers into easily digestible insights. With Aspose.Slides for .NET, creating a custom doughnut chart in your presentation slides is straightforward and efficient. This guide will walk you through using Aspose.Slides to create a visually appealing doughnut chart, complete with tailored series configurations.

**What You'll Learn:**
- Setting up your development environment with Aspose.Slides for .NET
- Creating and customizing doughnut charts in presentations
- Implementing advanced features like category names and leader lines
- Optimizing performance for large data sets

Let's dive into the prerequisites you need to get started.

## Prerequisites

Before implementing this feature, ensure that your development environment is properly set up. This tutorial assumes basic knowledge of .NET programming and familiarity with Visual Studio or a similar IDE.

### Required Libraries and Versions
- **Aspose.Slides for .NET**: Ensure compatibility with the latest version by checking their [official documentation](https://reference.aspose.com/slides/net/).

### Environment Setup Requirements
- A working .NET environment.
- Access to a code editor, such as Visual Studio.

### Knowledge Prerequisites
- Basic understanding of C# and .NET framework.
- Familiarity with presentation software concepts (optional but helpful).

## Setting Up Aspose.Slides for .NET

To begin using Aspose.Slides in your project, you need to install it via NuGet. Here are the methods available:

**Using .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Using Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager UI:**
Search for "Aspose.Slides" and install the latest version.

### License Acquisition Steps

1. **Free Trial**: Start with a [free trial](https://releases.aspose.com/slides/net/) to explore basic functionalities.
2. **Temporary License**: Obtain a temporary license if you need access to full features for evaluation purposes by visiting [here](https://purchase.aspose.com/temporary-license/).
3. **Purchase**: For commercial use, purchase a license from the [Aspose website](https://purchase.aspose.com/buy).

Once installed and licensed, initialize Aspose.Slides in your project:
```csharp
using Aspose.Slides;

// Initialize Aspose.Slides for .NET
var presentation = new Presentation();
```

## Implementation Guide

### Creating a New Presentation and Adding a Doughnut Chart

#### Overview
We'll start by creating a new presentation and adding a doughnut chart to the first slide. This section covers loading an existing presentation, accessing slides, and inserting charts.

**Step 1: Load or Create a Presentation**
First, specify your document directory and load an existing presentation:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
If you don't have an existing file, create a new one with `new Presentation()`.

**Step 2: Access the First Slide**
Get access to the first slide where we'll add our chart:
```csharp
ISlide slide = pres.Slides[0];
```

**Step 3: Add a Doughnut Chart**
Add a doughnut chart at specified coordinates and dimensions:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuring the Data Workbook

#### Overview
This section explains how to configure the data workbook associated with your doughnut chart.

**Step 4: Access and Clear Existing Data**
Access the chart's data workbook. Then clear any existing series or categories:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Step 5: Disable Legend and Add Series**
Disable the legend to keep the chart clean, then add up to 15 series with custom configurations:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Adding Categories and Data Points

#### Overview
Now, let's populate the chart with categories and data points for each series.

**Step 6: Add Categories**
Loop through to add 15 categories:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Step 7: Populate Data Points**
Add data points for each series within the current category:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Customize appearance
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Configure label format for the last series
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Configure label display
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Saving the Presentation

**Step 8: Save the File**
Finally, save your presentation to a specified directory:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}