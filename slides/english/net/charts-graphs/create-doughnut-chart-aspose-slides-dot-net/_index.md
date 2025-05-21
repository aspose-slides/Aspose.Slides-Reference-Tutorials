---
title: "How to Create a Doughnut Chart in PowerPoint Using Aspose.Slides for .NET&#58; A Step-by-Step Guide"
description: "Learn how to effortlessly create and customize doughnut charts in PowerPoint presentations using Aspose.Slides for .NET. Enhance your visual data presentation with this comprehensive guide."
date: "2025-04-15"
weight: 1
url: "/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
keywords:
- Aspose.Slides for .NET
- create doughnut chart PowerPoint
- customize PowerPoint charts

---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# How to Create a Doughnut Chart in PowerPoint Using Aspose.Slides for .NET: A Step-by-Step Guide

## Introduction

Enhancing your PowerPoint presentations with visually appealing doughnut charts can significantly improve how you present data. Aspose.Slides for .NET provides an efficient way to create and customize these charts. This tutorial will guide you through the steps of using Aspose.Slides for .NET to add a customizable doughnut chart, including adjusting hole sizes, to your PowerPoint slides.

**What You'll Learn:**
- Setting up Aspose.Slides for .NET
- Steps to add a doughnut chart to your slide
- Techniques to configure the hole size of your doughnut chart
- Practical applications and performance considerations

Let's get started with what you need before diving in!

## Prerequisites

Before we begin, ensure you have the following requirements:

### Required Libraries and Versions
- Aspose.Slides for .NET (latest version)
- Visual Studio or any compatible IDE that supports .NET development

### Environment Setup Requirements
- A Windows environment with .NET Framework installed
- Basic knowledge of C# programming

## Setting Up Aspose.Slides for .NET

To get started, you'll need to install the Aspose.Slides library. Here’s how you can do it using different methods:

**Using .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Using Package Manager Console:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager UI:**
Search for "Aspose.Slides" and install the latest version directly through your IDE's NuGet interface.

### License Acquisition Steps
1. **Free Trial:** Start by downloading a free trial to evaluate features.
2. **Temporary License:** If you need more time, request a temporary license from Aspose.
3. **Purchase:** For long-term use, consider purchasing the full version.

Once installed, initialize your project with this basic setup:
```csharp
using Aspose.Slides;

// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

## Implementation Guide

Let's break down the process of creating a doughnut chart using Aspose.Slides for .NET into manageable steps.

### Create a Doughnut Chart

#### Overview
We'll begin by adding a doughnut chart to your PowerPoint slide, setting its position and size.

**Adding the Chart:**
```csharp
using Aspose.Slides.Charts;

// Access the first slide in the presentation (by default, one is created)
ISlide slide = presentation.Slides[0];

// Add a doughnut chart to the slide at position (50, 50) with width and height of 400 units
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parameters:** `ChartType.Doughnut`, x-position: 50, y-position: 50, width: 400, height: 400.

### Set the Hole Size

#### Overview
Next, we'll configure the hole size of the doughnut chart to make it visually appealing.

**Configuring Hole Size:**
```csharp
// Set the hole size for the doughnut chart to 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Key Configuration:** `DoughnutHoleSize` determines how much of the center is "cut out." A value between 0 and 100 represents percentage.

### Save Your Presentation

Finally, save your changes to a new PowerPoint file:
```csharp
// Define the path where the presentation will be saved
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Save the modified presentation in PPTX format
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Note:** Replace `YOUR_OUTPUT_DIRECTORY` with your desired file location.

### Troubleshooting Tips

- Ensure Aspose.Slides is correctly installed and imported.
- Verify that your output directory path exists before saving the presentation.

## Practical Applications

Doughnut charts created with Aspose.Slides for .NET can be used in various scenarios:

1. **Business Reports:** Illustrate financial data like budget allocations or sales distributions.
2. **Marketing Analytics:** Display market share percentages among different brands.
3. **Educational Material:** Use to explain statistical concepts in a visually engaging way.

Integrate Aspose.Slides with other systems for automated report generation and distribution within corporate environments.

## Performance Considerations

When working with large presentations or numerous charts, consider the following tips:

- Optimize data processing before adding it to slides.
- Reuse presentation objects where possible to conserve memory.
- Regularly update your Aspose.Slides library to benefit from performance improvements.

## Conclusion

You've learned how to create and customize a doughnut chart using Aspose.Slides for .NET. This versatile tool enhances the visual appeal of your presentations, making data easier to understand at a glance.

**Next Steps:**
Explore other chart types available in Aspose.Slides or delve into advanced features like animations.

Ready to try it out? Head over to the resources section below and start experimenting!

## FAQ Section

1. **What is Aspose.Slides for .NET used for?**  
   It's a library for creating, modifying, and converting PowerPoint presentations programmatically.

2. **How can I change the color of the doughnut segments?**  
   Use `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` to adjust fill properties.

3. **Can I create multiple charts in one presentation?**  
   Yes, add as many charts as needed by repeating the chart creation steps on different slides or positions.

4. **How do I license Aspose.Slides for .NET for commercial use?**  
   Purchase a license through the official Aspose website to use it commercially.

5. **What should I do if my presentation doesn't save correctly?**  
   Check file path permissions and ensure your project references are up-to-date.

## Resources

- [Aspose.Slides Documentation](https://reference.aspose.com/slides/net/)
- [Download Aspose.Slides for .NET](https://releases.aspose.com/slides/net/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/net/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}