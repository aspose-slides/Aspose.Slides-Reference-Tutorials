---
title: Connect Shapes using Connectors in PowerPoint
linktitle: Connect Shapes using Connectors in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to connect shapes using connectors in PowerPoint presentations with Aspose.Slides for Java. Step-by-step tutorial for beginners.
weight: 18
url: /java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In this tutorial, we'll explore how to connect shapes using connectors in PowerPoint presentations with the help of Aspose.Slides for Java. Follow these step-by-step instructions to efficiently connect shapes and create visually appealing slides.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
- Basic knowledge of Java programming language.
- Installed Java Development Kit (JDK) on your system.
- Downloaded and set up Aspose.Slides for Java. If you haven't installed it yet, you can download it from [here](https://releases.aspose.com/slides/java/).
- A code editor such as Eclipse or IntelliJ IDEA.

## Import Packages
First, import the necessary packages for working with Aspose.Slides in your Java project.
```java
import com.aspose.slides.*;

```
## Step 1: Instantiate Presentation Class
Instantiate the `Presentation` class, which represents the PPTX file you're working on.
```java
// The path to the documents directory.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Step 2: Access Shapes Collection
Access the shapes collection for the selected slide where you want to add shapes and connectors.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Step 3: Add Shapes
Add the required shapes to the slide. In this example, we'll add an ellipse and a rectangle.
```java
// Add autoshape Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Add autoshape Rectangle
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Step 4: Add Connector
Add a connector shape to the slide shape collection.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Step 5: Join Shapes to Connectors
Connect the shapes to the connector.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Step 6: Reroute Connector
Call reroute to set the automatic shortest path between shapes.
```java
connector.reroute();
```
## Step 7: Save Presentation
Save the presentation after connecting shapes using connectors.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Finally, don't forget to dispose of the Presentation object.
```java
if (input != null) input.dispose();
```
Now you've successfully connected shapes using connectors in PowerPoint using Aspose.Slides for Java.

## Conclusion
In this tutorial, we've learned how to connect shapes using connectors in PowerPoint presentations with Aspose.Slides for Java. By following these simple steps, you can enhance your presentations with visually appealing diagrams and flowcharts.
## FAQ's
### Can I customize the appearance of connectors in Aspose.Slides for Java?
Yes, you can customize various properties of connectors such as color, line style, and thickness to suit your presentation needs.
### Is Aspose.Slides for Java compatible with all versions of PowerPoint?
Aspose.Slides for Java supports various PowerPoint formats, including PPTX, PPT, and ODP.
### Can I connect more than two shapes with a single connector?
Yes, you can connect multiple shapes using complex connectors provided by Aspose.Slides for Java.
### Does Aspose.Slides for Java offer support for adding text to shapes?
Absolutely, you can easily add text to shapes and connectors programmatically using Aspose.Slides for Java.
### Is there a community forum or support channel available for Aspose.Slides for Java users?
Yes, you can find helpful resources, ask questions, and engage with other users on the Aspose.Slides forum [here](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
