---
title: Set Connector Line Angle in PowerPoint
linktitle: Set Connector Line Angle in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set connector line angles in PowerPoint presentations using Aspose.Slides for Java. Customize your slides with precision.
weight: 17
url: /java/java-powerpoint-animation-shape-manipulation/set-connector-line-angle-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In this tutorial, we'll explore how to set the angle of connector lines in PowerPoint presentations using Aspose.Slides for Java. Connector lines are essential for illustrating relationships and flows between shapes in your slides. By adjusting their angles, you can ensure your presentations convey your message clearly and effectively.
## Prerequisites
Before we begin, ensure you have the following:
- Basic knowledge of Java programming.
- JDK (Java Development Kit) installed on your system.
- Aspose.Slides for Java library downloaded and added to your project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Import Packages
To get started, import the necessary packages into your Java project. Ensure you include the Aspose.Slides library for accessing PowerPoint functionalities.
```java
import com.aspose.slides.*;

```
## Step 1: Initialize Presentation Object
Begin by initializing a Presentation object to load your PowerPoint file.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
## Step 2: Access Slide and Shapes
Access the slide and its shapes to identify connector lines.
```java
Slide slide = (Slide) pres.getSlides().get_Item(0);
Shape shape;
```
## Step 3: Iterate Through Shapes
Iterate through each shape on the slide to identify connector lines and their properties.
```java
for (int i = 0; i < slide.getShapes().size(); i++) {
    double dir = 0.0;
    shape = (Shape) slide.getShapes().get_Item(i);
    if (shape instanceof AutoShape) {
        AutoShape ashp = (AutoShape) shape;
        if (ashp.getShapeType() == ShapeType.Line) {
            // Handle Line shape
            dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
        }
    } else if (shape instanceof Connector) {
        // Handle Connector shape
        Connector ashp = (Connector) shape;
        dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
    }
    System.out.println(dir);
}
```
## Step 4: Calculate Angle
Implement the getDirection method to calculate the angle of the connector line.
```java
public static double getDirection(float w, float h, boolean flipH, boolean flipV) {
    float endLineX = w * (flipH ? -1 : 1);
    float endLineY = h * (flipV ? -1 : 1);
    float endYAxisX = 0;
    float endYAxisY = h;
    double angle = (Math.atan2(endYAxisY, endYAxisX) - Math.atan2(endLineY, endLineX));
    if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```

## Conclusion
In this tutorial, we've learned how to manipulate connector lines' angles in PowerPoint presentations using Aspose.Slides for Java. By following these steps, you can effectively customize your slides to visually represent your data and concepts with precision.
## FAQ's
### Can I use Aspose.Slides for Java with other Java libraries?
Absolutely! Aspose.Slides for Java seamlessly integrates with other Java libraries to enhance your presentation creation and management experience.
### Is Aspose.Slides suitable for both simple and complex PowerPoint tasks?
Yes, Aspose.Slides offers a wide range of functionalities catering to various PowerPoint requirements, from basic slide manipulation to advanced formatting and animation tasks.
### Does Aspose.Slides support all PowerPoint features?
Aspose.Slides strives to support most PowerPoint features. However, for specific or advanced functionalities, it's recommended to consult the documentation or reach out to Aspose support.
### Can I customize connector line styles with Aspose.Slides?
Certainly! Aspose.Slides provides extensive options for customizing connector lines, including styles, thickness, and endpoints, allowing you to create visually appealing presentations.
### Where can I find support for Aspose.Slides-related queries?
You can visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for assistance with any queries or issues you encounter during your development process.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
