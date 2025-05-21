---
title: "How to Create a Doughnut Chart in PowerPoint Using Aspose.Slides for .NET"
description: "Learn how to create dynamic and visually appealing doughnut charts in PowerPoint presentations using the powerful Aspose.Slides for .NET library."
date: "2025-04-15"
weight: 1
url: "/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
keywords:
- Aspose.Slides for .NET
- create doughnut chart
- PowerPoint data visualization

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create a Doughnut Chart in PowerPoint Using Aspose.Slides for .NET
Creating visually engaging charts is essential for effective data presentation. Doughnut charts are perfect for illustrating parts of a whole, making them ideal for percentage-based data visualization. This tutorial will guide you through creating a dynamic doughnut chart in PowerPoint using the powerful Aspose.Slides for .NET library.

## Introduction
Presentations often require visual representations of complex datasets where traditional bar or line charts may fall short. The doughnut chart emerges as a versatile tool to effectively communicate percentage-based data with style and clarity. In this tutorial, we'll explore how Aspose.Slides for .NET simplifies the process of creating these charts directly within PowerPoint.

**What You’ll Learn:**
- Setting up Aspose.Slides for .NET
- Step-by-step instructions on creating a doughnut chart
- Adding series and categories to your chart
- Configuring data labels for enhanced clarity
- Saving the final presentation

Let's dive into how you can leverage Aspose.Slides for .NET to enhance your presentations with custom doughnut charts.

## Prerequisites
Before we begin, ensure that you have the following in place:
- **Aspose.Slides for .NET library**: Available via NuGet or direct download.
- **Development Environment**: Visual Studio is recommended for .NET projects.
- Basic knowledge of C# and familiarity with PowerPoint's structure.

## Setting Up Aspose.Slides for .NET
To start creating charts, you first need to set up the Aspose.Slides library in your project. Here are several ways to install it:

**Using .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Using Package Manager Console:**

```powershell
Install-Package Aspose.Slides
```

**Through NuGet Package Manager UI:**
Search for "Aspose.Slides" and install the latest version.

Once installed, you can begin setting up your project. If you're new to Aspose.Slides, consider obtaining a temporary license or free trial to explore its full capabilities without limitations.

### Initialize Your Project
Here's how you can initialize Aspose.Slides in your application:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Your code to manipulate the presentation goes here
        
        // Save the presentation
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Implementation Guide
### Creating a Doughnut Chart
#### Overview
First, we'll create an empty doughnut chart in a PowerPoint slide. This serves as the foundation for adding data and customizing its appearance.

**Step 1: Add a Doughnut Chart**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Add a doughnut chart to the first slide at position (10, 10) with size (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Clear existing series and categories
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Disable the legend for a cleaner look
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explanation:**
- **addChart**: Inserts a new doughnut chart on the slide.
- **getChartDataWorkbook**: Provides access to data cells in the chart for manipulation.

### Adding Series and Categories
#### Overview
Next, we'll populate your chart with meaningful data by adding series and categories.

**Step 2: Add Data Series**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Add series
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Customizing the doughnut hole and starting angle
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Add categories
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formatting the data point's fill and line
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explanation:**
- **add**: Inserts new series and categories into the chart.
- **setDoughnutHoleSize**: Configures the size of the doughnut hole, enhancing its visual appeal.

### Configuring Data Labels
#### Overview
Data labels provide context to your chart data. Let's enhance readability by customizing them.

**Step 3: Customize Data Labels**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Customizing data labels
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explanation:**
- **IDataLabel**: Customizes the data labels for clarity and presentation.
- **setCenterText**, **showPercentage**: Enhance label readability by centering text and showing percentages.

## Conclusion
By following this guide, you've learned how to create a dynamic doughnut chart in PowerPoint using Aspose.Slides for .NET. This powerful library allows for extensive customization, enabling you to tailor your charts precisely to your presentation needs.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}