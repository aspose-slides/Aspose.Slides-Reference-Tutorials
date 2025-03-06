---
title: Add Custom Child Nodes in SmartArt using Java
linktitle: Add Custom Child Nodes in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add custom child nodes to SmartArt in PowerPoint presentations using Java with Aspose.Slides. Enhance your slides with professional graphics effortlessly.
weight: 11
url: /java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
SmartArt is a powerful feature in PowerPoint that allows users to create professional-looking graphics quickly and easily. In this tutorial, we will learn how to add custom child nodes to SmartArt using Java with Aspose.Slides.
## Prerequisites
Before we begin, make sure you have the following:
1. Java Development Kit (JDK): Ensure you have Java installed on your system.
2. Aspose.Slides for Java: Download and install Aspose.Slides for Java from [here](https://releases.aspose.com/slides/java/).

## Import Packages
To start, import the necessary packages in your Java project:
```java
import com.aspose.slides.*;
```
## Step 1: Load the Presentation
Load the PowerPoint presentation where you want to add custom child nodes to the SmartArt:
```java
String dataDir = "Your Document Directory";
// Load the desired presentation
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Step 2: Add SmartArt to Slide
Now, let's add SmartArt to the slide:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Step 3: Move SmartArt Shape
Move the SmartArt shape to a new position:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Step 4: Change Shape Width
Change the width of the SmartArt shape:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Step 5: Change Shape Height
Change the height of the SmartArt shape:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Step 6: Rotate the Shape
Rotate the SmartArt shape:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Step 7: Save the Presentation
Finally, save the modified presentation:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion
In this tutorial, we learned how to add custom child nodes to SmartArt using Java with Aspose.Slides. By following these steps, you can enhance your presentations with customized graphics, making them more engaging and professional.
## FAQ's
### Can I add different types of SmartArt layouts using Aspose.Slides for Java?
Yes, Aspose.Slides for Java supports various SmartArt layouts, allowing you to choose the one that best fits your presentation needs.
### Is Aspose.Slides for Java compatible with different versions of PowerPoint?
Aspose.Slides for Java is designed to work seamlessly with different versions of PowerPoint, ensuring compatibility and consistency across platforms.
### Can I customize the appearance of SmartArt shapes programmatically?
Absolutely! With Aspose.Slides for Java, you can programmatically customize the appearance, size, color, and layout of SmartArt shapes to suit your design preferences.
### Does Aspose.Slides for Java provide documentation and support?
Yes, you can find comprehensive documentation and access to community support forums on the Aspose website.
### Is there a trial version available for Aspose.Slides for Java?
Yes, you can download a free trial version of Aspose.Slides for Java from the website to explore its features and capabilities before making a purchase [here](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
