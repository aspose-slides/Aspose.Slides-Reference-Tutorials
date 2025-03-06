---
title: Aspose.Slides - Connect Shapes Seamlessly in .NET
linktitle: Connecting Shapes using Connectors in Presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Explore the power of Aspose.Slides for .NET, connecting shapes effortlessly in your presentations. Elevate your slides with dynamic connectors.
type: docs
weight: 29
url: /net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Introduction
In the dynamic world of presentations, the ability to connect shapes using connectors adds a layer of sophistication to your slides. Aspose.Slides for .NET empowers developers to achieve this seamlessly. This tutorial will guide you through the process, breaking down each step to ensure a clear understanding.
## Prerequisites
Before we dive into the tutorial, make sure you have the following:
- Basic knowledge of C# and .NET framework.
- Aspose.Slides for .NET installed. If not, download it [here](https://releases.aspose.com/slides/net/).
- A development environment set up.
## Import Namespaces
In your C# code, start by importing the necessary namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Set Up the Document Directory
Begin by defining the directory for your document:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instantiate Presentation Class
Create an instance of the Presentation class to represent your PPTX file:
```csharp
using (Presentation input = new Presentation())
{
    // Accessing shapes collection for the selected slide
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Add Shapes to the Slide
Add the necessary shapes to your slide, such as Ellipse and Rectangle:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Add Connector Shape
Include a connector shape in the slide's shape collection:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Connect Shapes with Connector
Specify the shapes to be connected by the connector:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Reroute Connector
Call the reroute method to set the automatic shortest path between shapes:
```csharp
connector.Reroute();
```
## 7. Save Presentation
Save your presentation to view the connected shapes:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Congratulations! You have successfully connected shapes using connectors in presentation slides using Aspose.Slides for .NET. Enhance your presentations with this advanced feature and captivate your audience.
## FAQs
### Is Aspose.Slides for .NET compatible with the latest .NET framework?
Yes, Aspose.Slides for .NET is regularly updated to ensure compatibility with the latest .NET framework versions.
### Can I connect more than two shapes using a single connector?
Absolutely, you can connect multiple shapes by extending the connector logic in your code.
### Are there any limitations on the shapes I can connect?
Aspose.Slides for .NET supports connecting various shapes, including basic shapes, smart art, and custom shapes.
### How can I customize the appearance of the connector?
Explore the Aspose.Slides documentation for methods to customize connector appearance, such as line style and color.
### Is there a community forum for Aspose.Slides support?
Yes, you can find assistance and share your experiences in the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
