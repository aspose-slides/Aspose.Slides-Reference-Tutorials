---
title: "How to Create and Customize Pie Charts in .NET Presentations Using Aspose.Slides"
description: "Learn how to automate pie chart creation in .NET presentations with Aspose.Slides, enhancing data visualization effortlessly."
date: "2025-04-15"
weight: 1
url: "/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
keywords:
- Aspose.Slides for .NET
- create pie charts in .NET
- customize presentations with Aspose

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create and Customize Pie Charts in .NET Presentations Using Aspose.Slides

## Introduction
Creating engaging and informative presentations is crucial for effective communication, whether you're presenting data at work or showcasing your latest project findings. One powerful way to visualize data is through pie charts, which can succinctly represent parts of a whole. However, manually crafting these charts in presentation software like PowerPoint can be time-consuming and may lack the flexibility required for dynamic updates.

That's where Aspose.Slides for .NET comes into play. This comprehensive library allows you to create, modify, and style presentations programmatically, making it an invaluable tool for developers who want to automate their workflow and ensure consistency across presentations.

In this tutorial, we'll explore how to use Aspose.Slides for .NET to create and customize pie charts in your presentations. You’ll learn how to:
- **Create a presentation and access slides**
- **Add and configure pie charts**
- **Customize chart data and series**
- **Style pie chart sectors**
- **Add custom labels**
- **Configure display properties and save the presentation**

Ready to dive into creating stunning pie charts with ease? Let’s get started!

## Prerequisites
Before we begin, ensure you have the following setup in place:

### Required Libraries
- Aspose.Slides for .NET (version 21.11 or later recommended)

### Environment Setup
- A development environment running .NET Framework or .NET Core/5+/6+
- A code editor such as Visual Studio

### Knowledge Prerequisites
- Basic understanding of C# programming
- Familiarity with object-oriented concepts

## Setting Up Aspose.Slides for .NET
To get started, you'll need to install the Aspose.Slides library. You can do this using any of the following methods:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Package Manager Console**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager UI**
- Open your project in Visual Studio.
- Go to "Tools" > "NuGet Package Manager" > "Manage NuGet Packages for Solution."
- Search for "Aspose.Slides" and install the latest version.

### License Acquisition Steps
To use Aspose.Slides, you can start with a free trial by downloading a temporary license. Visit [Aspose's website](https://purchase.aspose.com/temporary-license/) to obtain it. For ongoing usage, consider purchasing a full license.

### Basic Initialization and Setup
Once installed, initialize the Presentation class, which represents your PPTX file:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Implementation Guide
We will break down the pie chart creation process into manageable sections. Each section is designed to focus on a specific feature, allowing you to build up your knowledge incrementally.

### Create a Presentation and Access Slides
**Overview:** Start by creating a new presentation and accessing its first slide. This sets the stage for adding charts and other elements.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Instantiate Presentation class that represents a PPTX file
    Presentation presentation = new Presentation();
    
    // Access first slide
    ISlide slides = presentation.Slides[0];
}
```

### Add and Configure Pie Chart
**Overview:** Learn how to add a pie chart to your slide and set its title for context.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Instantiate Presentation class that represents a PPTX file
    Presentation presentation = new Presentation();
    
    // Access first slide
    ISlide slides = presentation.Slides[0];
    
    // Add chart with default data to the slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Setting chart Title
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Customize Chart Data and Series
**Overview:** Customize the data categories and series to fit your specific requirements.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Instantiate Presentation class that represents a PPTX file
    Presentation presentation = new Presentation();
    
    // Access first slide
    ISlide slides = presentation.Slides[0];
    
    // Add chart with default data to the slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Set first series to Show Values
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Setting the index of chart data sheet
    int defaultWorksheetIndex = 0;
    
    // Getting the chart data worksheet
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Delete default generated series and categories
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Adding new categories
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Adding new series
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Now populating series data
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Customize Pie Chart Sector Styles
**Overview:** Style individual sectors of your pie chart to enhance visual appeal and emphasize key data points.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Instantiate Presentation class that represents a PPTX file
    Presentation presentation = new Presentation();
    
    // Access first slide
    ISlide slides = presentation.Slides[0];
    
    // Add chart with default data to the slide
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Get series from chart
    IChartSeries series = chart.ChartData.Series[0];
    
    // Customizing sector styles for each data point in the series
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Setting Sector border
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Setting Sector border
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Setting Sector border
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Add Custom Labels to Pie Chart
**Overview:** Enhance your pie chart by adding custom labels for clearer data representation.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Adjust label position as needed
    }
}
```

### Conclusion
You have now learned how to create and customize pie charts in .NET presentations using Aspose.Slides. This automation can significantly enhance your data visualization efforts, saving time and ensuring consistency across presentations.

To further explore the capabilities of Aspose.Slides for .NET, consider diving into additional features such as creating other chart types or integrating more complex design elements into your slides.

Happy coding!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}