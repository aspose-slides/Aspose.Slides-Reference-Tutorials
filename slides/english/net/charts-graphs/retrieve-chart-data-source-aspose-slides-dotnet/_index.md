---
title: "How to Retrieve Chart Data Source Type Using Aspose.Slides for .NET - Charts & Graphs"
description: "Learn how to efficiently retrieve chart data source types in PowerPoint presentations using Aspose.Slides for .NET. Automate and integrate presentations with ease."
date: "2025-04-15"
weight: 1
url: "/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/"
keywords:
- Aspose.Aspose.Slides
- Net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# How to Retrieve Chart Data Source Type Using Aspose.Slides for .NET

## Introduction

Are you struggling to manage data sources within charts of PowerPoint presentations programmatically? Many developers face challenges when trying to extract and manipulate chart data in Microsoft Office files using C#. In this tutorial, we’ll guide you through retrieving the data source type of a chart in a PowerPoint presentation with Aspose.Slides for .NET. This solution is ideal if you need to automate presentations or integrate them into your applications.

**What You'll Learn:**
- Setting up and using Aspose.Slides for .NET
- Retrieving the data source type of charts in PowerPoint slides
- Handling external workbook paths when applicable
- Saving changes back to a presentation

Before we dive in, let's cover some prerequisites.

## Prerequisites

To follow this tutorial effectively, you'll need:
1. **Aspose.Slides for .NET Library:** Ensure you have the latest version installed.
2. **Development Environment:** A working setup of Visual Studio or any preferred IDE that supports C# development.
3. **Basic Knowledge:** Familiarity with C#, object-oriented programming concepts, and handling file paths in .NET.

## Setting Up Aspose.Slides for .NET

Firstly, you need to install the Aspose.Slides library. Here’s how:

**Using .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Using Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**Via NuGet Package Manager UI:**
Search for "Aspose.Slides" in the NuGet Package Manager and install it.

### License Acquisition
- **Free Trial:** Start with a free trial to explore functionalities.
- **Temporary License:** Obtain a temporary license for extended access without limitations.
- **Purchase:** Consider purchasing if you find Aspose.Slides meets your needs.

Once installed, initialize your project by including the necessary namespaces:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Implementation Guide

We'll break down this feature into steps for clarity. Let's explore how to retrieve a chart’s data source type.

### Step 1: Load Your Presentation

First, load the PowerPoint presentation containing your charts:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Set to your directory path

using (Presentation pres = new Presentation(dataDir + "/pres.pptx"))
{
    // Continue with further steps...
}
```

### Step 2: Access a Slide and Its Chart

Access the first slide and the chart within:
```csharp
// Get the first slide from the presentation
ISlide slide = pres.Slides[0];

// Ensure the shape is indeed a chart
IChart chart = (IChart)slide.Shapes[0];
```

### Step 3: Retrieve Data Source Type

Now, let’s retrieve the data source type:
```csharp
// Get the data source type of the chart
ChartDataSourceType sourceType = chart.ChartData.DataSourceType;
```

### Step 4: Handle External Workbook Paths

If your chart uses an external workbook, you can fetch its path like this:
```csharp
if (sourceType == ChartDataSourceType.ExternalWorkbook)
{
    string path = chart.ChartData.ExternalWorkbookPath;
}
```

### Step 5: Save Your Presentation

Finally, save the presentation after making any modifications:
```csharp
pres.Save(dataDir + "/Result.pptx\
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}