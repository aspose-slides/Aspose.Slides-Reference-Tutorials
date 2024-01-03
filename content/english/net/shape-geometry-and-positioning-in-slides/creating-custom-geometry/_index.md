---
title: Creating Custom Geometry in C# with Aspose.Slides for .NET
linktitle: Creating Custom Geometry in Geometry Shape using Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn to create custom geometry in Aspose.Slides for .NET. Elevate your presentations with unique shapes. Step-by-step guide for C# developers.
type: docs
weight: 15
url: /net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---
## Introduction
In the dynamic world of presentations, adding unique shapes and geometries can elevate your content, making it more engaging and visually appealing. Aspose.Slides for .NET provides a powerful solution for creating custom geometries within shapes, allowing you to break free from conventional designs. This tutorial will guide you through the process of creating custom geometry in a GeometryShape using Aspose.Slides for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- A basic understanding of C# programming language.
- Aspose.Slides for .NET library installed in your development environment.
- Visual Studio or any preferred C# development environment set up.
## Import Namespaces
To get started, import the necessary namespaces into your C# project:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Step 1: Set Up Your Project
Create a new C# project in your preferred development environment. Ensure that Aspose.Slides for .NET is properly installed.
## Step 2: Define Your Document Directory
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Step 3: Set Outer and Inner Star Radius
```csharp
float R = 100, r = 50; // Outer and inner star radius
```
## Step 4: Create Star Geometry Path
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Step 5: Create a Presentation
```csharp
using (Presentation pres = new Presentation())
{
    // Create new shape
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Set new geometry path to the shape
    shape.SetGeometryPath(starPath);
    // Save the presentation
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Step 6: Define CreateStarGeometry Method
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Conclusion
Congratulations! You've successfully learned how to create custom geometry in a GeometryShape using Aspose.Slides for .NET. This opens up a world of possibilities for creating unique and visually stunning presentations.
## FAQs
### 1. Can I use Aspose.Slides for .NET with other programming languages?
Yes, Aspose.Slides supports various programming languages, but this tutorial focuses on C#.
### 2. Where can I find the documentation for Aspose.Slides for .NET?
Visit the [documentation](https://reference.aspose.com/slides/net/) for detailed information.
### 3. Is there a free trial available for Aspose.Slides for .NET?
Yes, you can explore a [free trial](https://releases.aspose.com/) to experience the features.
### 4. How can I get support for Aspose.Slides for .NET?
Seek assistance and engage with the community at the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 5. Where can I purchase Aspose.Slides for .NET?
You can buy Aspose.Slides for .NET [here](https://purchase.aspose.com/buy).
