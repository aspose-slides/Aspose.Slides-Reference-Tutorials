---
title: Apply Outer Shadow in PowerPoint with Java
linktitle: Apply Outer Shadow in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to apply outer shadow effect in PowerPoint using Java with Aspose.Slides. Enhance your presentations with depth and visual appeal.
type: docs
weight: 13
url: /java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---
## Introduction
Creating visually appealing PowerPoint presentations often involves adding various effects to shapes and text. One such effect is the outer shadow, which can make elements stand out and add depth to your slides. In this tutorial, you will learn how to apply an outer shadow effect to a shape in PowerPoint using Java with Aspose.Slides.
## Prerequisites

Before you begin this tutorial, make sure you have the following prerequisites:

1. Java Development Kit (JDK): Ensure you have Java installed on your system. You can download and install the latest version of JDK from the Oracle website.

2. Aspose.Slides for Java: Download and install Aspose.Slides for Java from the [download page](https://releases.aspose.com/slides/java/).

3. Integrated Development Environment (IDE): Choose your preferred Java IDE such as Eclipse, IntelliJ IDEA, or NetBeans for coding and running Java applications.

4. Basic Java Knowledge: Familiarity with Java programming language fundamentals and object-oriented concepts will be beneficial for understanding the code examples.

## Import Packages

First, import the necessary packages for working with Aspose.Slides and related functionalities in your Java project:

```java
import com.aspose.slides.*;
```

Now let's break down the example code into multiple steps to apply the outer shadow effect to a shape in PowerPoint using Java with Aspose.Slides:

## Step 1: Set up your project environment

Create a new Java project in your preferred IDE and add Aspose.Slides for Java library to your project's build path.

## Step 2: Initialize Presentation object

Create an instance of the `Presentation` class, which represents a PowerPoint presentation file.

```java
Presentation presentation = new Presentation();
```

## Step 3: Add a slide and shape

Get a reference to the slide where you want to add the shape, and then add an AutoShape (e.g., rectangle) to the slide.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Step 4: Customize the shape

Set the fill type of the shape to 'NoFill' and add text to the shape.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Step 5: Customize the text

Access the text properties of the shape and customize the font size.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Step 6: Enable Outer Shadow effect

Enable the outer shadow effect for the text portion.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Step 7: Set shadow parameters

Define the parameters for the outer shadow effect, such as blur radius, direction, distance, and shadow color.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Step 8: Save the presentation

Save the modified presentation with the outer shadow effect applied to the shape.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

Congratulations! You have successfully applied an outer shadow effect to a shape in PowerPoint using Java with Aspose.Slides. Experiment with different parameters to achieve the desired visual effects in your presentations.

## FAQ's

### Can I apply the outer shadow effect to other shapes besides rectangles?
Yes, you can apply the outer shadow effect to various shapes supported by Aspose.Slides, such as circles, triangles, and custom shapes.

### Is it possible to customize the shadow color and intensity?
Absolutely! You have full control over the shadow parameters, including color, blur radius, direction, and distance.

### Can I apply multiple effects to the same shape?
Yes, you can combine multiple effects like outer shadow, inner shadow, glow, and reflection to enhance the visual appeal of shapes and text in your presentations.

### Does Aspose.Slides support applying effects to text elements?
Yes, you can apply effects not only to shapes but also to individual text portions within shapes, giving you extensive flexibility in designing your slides.

### Where can I find more resources and support for Aspose.Slides?
You can refer to the [documentation](https://reference.aspose.com/slides/java/) for detailed API references and explore the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) for community support and discussions.
