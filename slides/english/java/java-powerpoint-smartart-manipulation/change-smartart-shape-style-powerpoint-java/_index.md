---
title: Change SmartArt Shape Style in PowerPoint with Java
linktitle: Change SmartArt Shape Style in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to change SmartArt styles in PowerPoint presentations using Java with Aspose.Slides for Java. Boost your presentations.
weight: 23
url: /java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Change SmartArt Shape Style in PowerPoint with Java

## Introduction
In the world of Java development, creating powerful presentations is often a requirement. Whether it's for business pitches, educational purposes, or simply sharing information, PowerPoint presentations are a common medium. However, sometimes the default styles and formats provided by PowerPoint may not fully meet our needs. This is where Aspose.Slides for Java comes into play.
Aspose.Slides for Java is a robust library that allows Java developers to work with PowerPoint presentations programmatically. It provides a wide range of features, including the ability to manipulate shapes, styles, animations, and much more. In this tutorial, we will focus on one specific task: changing the SmartArt shape style in PowerPoint presentations using Java.
## Prerequisites
Before diving into the tutorial, there are a few prerequisites you need to have in place:
1. Java Development Kit (JDK): Ensure that you have JDK installed on your system. You can download and install the latest version from the Oracle website.
2. Aspose.Slides for Java Library: You'll need to download and include the Aspose.Slides for Java library in your project. You can find the download link [here](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Choose your preferred IDE for Java development. IntelliJ IDEA, Eclipse, or NetBeans are popular choices.

## Import Packages
Before we start coding, let's import the necessary packages to our Java project. These packages will enable us to work with Aspose.Slides functionalities seamlessly.
```java
import com.aspose.slides.*;
```
## Step 1: Load the Presentation
First, we need to load the PowerPoint presentation that we want to modify.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Step 2: Traverse Through Shapes
Next, we'll traverse through every shape inside the first slide of the presentation.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Step 3: Check SmartArt Type
For each shape, we'll check if it's a SmartArt shape.
```java
if (shape instanceof ISmartArt)
```
## Step 4: Cast to SmartArt
If the shape is a SmartArt, we'll cast it to the `ISmartArt` interface.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Step 5: Check and Change Style
We'll then check the current style of the SmartArt and change it if needed.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Step 6: Save Presentation
Finally, we'll save the modified presentation to a new file.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Conclusion
In this tutorial, we've learned how to change the SmartArt shape style in PowerPoint presentations using Java and Aspose.Slides for Java library. By following the step-by-step guide, you can easily customize the appearance of SmartArt shapes to better suit your presentation needs.
## FAQ's
### Can I use Aspose.Slides for Java with other Java libraries?
Yes, Aspose.Slides for Java can be integrated with other Java libraries seamlessly to enhance the functionality of your applications.
### Is there a free trial available for Aspose.Slides for Java?
Yes, you can avail of a free trial of Aspose.Slides for Java from [here](https://releases.aspose.com/).
### How can I get support for Aspose.Slides for Java?
You can get support for Aspose.Slides for Java by visiting the [forum](https://forum.aspose.com/c/slides/11).
### Can I purchase a temporary license for Aspose.Slides for Java?
Yes, you can purchase a temporary license for Aspose.Slides for Java from [here](https://purchase.aspose.com/temporary-license/).
### Where can I find detailed documentation for Aspose.Slides for Java?
You can find detailed documentation for Aspose.Slides for Java [here](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
