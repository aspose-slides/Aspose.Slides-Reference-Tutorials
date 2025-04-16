---
title: "How to Create and Save Custom Star Shapes in .NET Presentations Using Aspose.Slides"
description: "Learn how to enhance your presentations with custom star shapes using Aspose.Slides for .NET. Follow this step-by-step guide to create engaging visuals."
date: "2025-04-16"
weight: 1
url: "/net/shapes-text-frames/create-star-shape-dotnet-presentation-aspose-slides/"
keywords:
- Aspose.Aspose.Slides
- Net
- Document Processing

---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}
# How to Create and Save Custom Star Shapes in .NET Presentations Using Aspose.Slides

Incorporating unique shapes like stars can transform your presentation slides from ordinary to extraordinary. This tutorial guides you through creating and saving custom star-shaped geometries using Aspose.Slides for .NET, making your presentations more engaging and visually appealing.

## What You'll Learn:
- Creating a custom star shape with specific radii in C#.
- Integrating this feature into a .NET application.
- Saving the presentation with the new custom shape using Aspose.Slides.

Let's dive in!

### Prerequisites

Before starting, ensure you have:
- **Aspose.Slides for .NET**: Version 23.x or later is required. This library allows creating and manipulating PowerPoint presentations programmatically.
- **Development Environment**: Visual Studio with a .NET project setup.
- **Basic C# Knowledge**: Familiarity with C# programming concepts will help you understand the implementation better.

### Setting Up Aspose.Slides for .NET

Add Aspose.Slides to your project using one of these methods:

**Using .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Using Package Manager:**
```powershell
Install-Package Aspose.Slides
```

**Using NuGet Package Manager UI:**
1. Open the "Manage NuGet Packages" dialog in Visual Studio.
2. Search for "Aspose.Slides".
3. Install the latest version.

#### Acquiring a License
To fully utilize Aspose.Slides, consider acquiring a license:
- **Free Trial**: Start with a temporary license to explore full features without limitations.
- **Purchase**: Visit [Aspose Purchase](https://purchase.aspose.com/buy) for various licensing options tailored to your needs.

### Implementation Guide
We will create the star shape and save it in a presentation, divided into two main features.

#### Feature 1: Create Custom Geometry Path
This feature involves generating a geometric path that forms a star shape using specified outer and inner radii.

**Overview**: We calculate points for both the outer and inner edges of the star and connect them to form a closed star shape.

##### Implementation Steps:

**Step 1**: Define the Star Points Calculation
```csharp
using System.Collections.Generic;
using Aspose.Slides.Export;
using System.Drawing;

public static class StarGeometryCreator
{
    public static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
    {
        GeometryPath starPath = new GeometryPath();
        List<PointF> points = new List<PointF>();
        int step = 72; // Step angle in degrees

        for (int angle = -90; angle < 270; angle += step)
        {
            double radians = angle * (Math.PI / 180f);
            double xOuter = outerRadius * Math.Cos(radians) + outerRadius;
            double yOuter = outerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xOuter, (float)yOuter));

            radians = Math.PI * (angle + step / 2) / 180.0;
            double xInner = innerRadius * Math.Cos(radians) + outerRadius;
            double yInner = innerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xInner, (float)yInner));
        }

        starPath.MoveTo(points[0]);
        for (int i = 1; i < points.Count; i++)
        {
            starPath.LineTo(points[i]);
        }
        starPath.CloseFigure();

        return starPath;
    }
}
```
**Explanation**: The method `CreateStarGeometry` calculates the coordinates of outer and inner vertices based on input radii. It uses trigonometry to place each point, creating a continuous path that forms a star.

#### Feature 2: Create and Save a Presentation with Custom Shape
Here we integrate the custom geometry into a presentation and save it as a .pptx file.

**Overview**: Add a shape to a slide using the custom geometry path created in the previous step.

##### Implementation Steps:

**Step 1**: Initialize the Presentation
```csharp
using Aspose.Slides;
using System.IO;

public static class PresentationCreator
{
    public static void CreateAndSavePresentation()
    {
        string resultPath = Path.Combine("YOUR_OUTPUT_DIRECTORY\
{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}