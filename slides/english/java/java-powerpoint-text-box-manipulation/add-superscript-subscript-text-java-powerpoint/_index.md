---
title: Add Superscript and Subscript Text in Java PowerPoint
linktitle: Add Superscript and Subscript Text in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add superscript and subscript text in Java PowerPoint presentations using Aspose.Slides for Java. Perfect for enhancing your slides.
weight: 13
url: /java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Superscript and Subscript Text in Java PowerPoint

## Introduction
Creating engaging and informative PowerPoint presentations often requires the use of formatting features like superscript and subscript text. This tutorial will guide you through the process of incorporating superscript and subscript text into your Java PowerPoint presentations using Aspose.Slides for Java.
## Prerequisites
Before you begin, ensure you have the following:
- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library. You can download it from [here](https://releases.aspose.com/slides/java/).
- An Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse set up for Java development.
- Basic familiarity with Java programming and PowerPoint presentations.

## Import Packages
First, import the necessary packages from Aspose.Slides for Java:
```java
import com.aspose.slides.*;
```
## Step 1: Set up the Presentation
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Step 2: Access the Slide
```java
// Get the first slide
ISlide slide = presentation.getSlides().get_Item(0);
```
## Step 3: Create a Text Box
```java
// Create an AutoShape to serve as a text box
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Step 4: Add Superscript Text
```java
// Create a paragraph for the main text
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Create a portion for the superscript text
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Set escapement for superscript
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Add the main paragraph with superscript to the text box
textFrame.getParagraphs().add(mainParagraph);
```
## Step 5: Add Subscript Text
```java
// Create another paragraph for subscript text
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Create a portion for the subscript text
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Set escapement for subscript
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Add the subscript paragraph to the text box
textFrame.getParagraphs().add(subscriptParagraph);
```
## Step 6: Save the Presentation
```java
// Save the presentation
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusion
In this tutorial, we explored how to enhance your Java PowerPoint presentations with superscript and subscript text using Aspose.Slides for Java. By following these steps, you can create more visually appealing and informative slides that effectively communicate your content.

## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a robust library that allows developers to create, manipulate, and convert PowerPoint presentations programmatically.
### Where can I find more documentation on Aspose.Slides for Java?
Detailed documentation can be found [here](https://reference.aspose.com/slides/java/).
### How can I obtain a temporary license for Aspose.Slides for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Can I try Aspose.Slides for Java for free?
Yes, you can download a free trial version from [here](https://releases.aspose.com/).
### Where can I get support for Aspose.Slides for Java?
For support and discussions, visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
