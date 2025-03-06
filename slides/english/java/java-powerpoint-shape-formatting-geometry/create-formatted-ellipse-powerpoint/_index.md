---
title: Create Formatted Ellipse in PowerPoint
linktitle: Create Formatted Ellipse in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to create a formatted ellipse in PowerPoint using Aspose.Slides for Java with our detailed step-by-step guide.
weight: 17
url: /java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Welcome to this comprehensive tutorial on creating a formatted ellipse in PowerPoint using Aspose.Slides for Java. Aspose.Slides is a powerful library that allows developers to manipulate PowerPoint files programmatically. Whether you're automating slide generation or enhancing presentations with custom shapes, this guide will walk you through every step, ensuring you can add a perfectly formatted ellipse to your slides with ease. Let's dive in and see how we can achieve this!
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK): Make sure you have JDK 1.6 or higher installed.
2. Aspose.Slides for Java: Download the latest version from [Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Use an IDE like IntelliJ IDEA or Eclipse.
4. Basic Knowledge of Java: Familiarity with Java programming is required.
## Import Packages
To start using Aspose.Slides, you need to import the necessary packages. Here’s how you can do it:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Step 1: Set Up Your Project Directory
First, you need a directory to store your PowerPoint files.
### Create Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create directory if it is not already present.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Ensure you replace `"Your Document Directory"` with the actual path where you want to store your files.
## Step 2: Initialize the Presentation
Now, instantiate the Presentation class, which represents the PowerPoint file.
```java
// Instantiate Presentation class that represents the PPTX
Presentation pres = new Presentation();
```
## Step 3: Get the First Slide
Next, get the first slide from the presentation where you will add the ellipse.
```java
// Get the first slide
ISlide sld = pres.getSlides().get_Item(0);
```
## Step 4: Add an Ellipse Shape
Add an auto shape of the ellipse type to the slide.
```java
// Add autoshape of ellipse type
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Here, `50, 150, 150, 50` are the coordinates and size of the ellipse (x position, y position, width, height).
## Step 5: Apply Formatting to the Ellipse
Now, apply some formatting to the ellipse. We'll set a solid fill color and a line color.
### Set Fill Color
```java
// Apply some formatting to ellipse shape
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Set Line Color and Width
```java
// Apply some formatting to the line of Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Step 6: Save the Presentation
Finally, save the presentation to your specified directory.
```java
// Write the PPTX file to disk
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Step 7: Dispose of the Presentation Object
Dispose of the presentation object to free up resources.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusion
Congratulations! You've successfully created a formatted ellipse in a PowerPoint presentation using Aspose.Slides for Java. This tutorial walked you through setting up your project, adding an ellipse, applying formatting, and saving your presentation. With these skills, you can now enhance your PowerPoint slides programmatically, making your presentations more dynamic and visually appealing.
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a powerful library that allows developers to create, modify, and manage PowerPoint presentations programmatically.
### Can I use Aspose.Slides for Java with any IDE?
Yes, you can use Aspose.Slides for Java with any Java IDE like IntelliJ IDEA, Eclipse, or NetBeans.
### Do I need a license for Aspose.Slides?
Yes, Aspose.Slides is a commercial product, and you need a license for full functionality. You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Where can I find more documentation on Aspose.Slides for Java?
You can find detailed documentation on the Aspose.Slides for Java [documentation page](https://reference.aspose.com/slides/java/).
### Is there support available for Aspose.Slides?
Yes, Aspose offers support through their [forum](https://forum.aspose.com/c/slides/11).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
