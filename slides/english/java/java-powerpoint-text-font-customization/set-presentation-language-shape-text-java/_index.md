---
title: Set Presentation Language and Shape Text in Java
linktitle: Set Presentation Language and Shape Text in Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to automate PowerPoint presentations using Aspose.Slides for Java. Create, modify, and enhance slides programmatically with ease.
weight: 19
url: /java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Creating and manipulating PowerPoint presentations programmatically in Java can streamline workflow automation and enhance productivity. Aspose.Slides for Java provides a robust set of tools to achieve these tasks efficiently. This tutorial guides you through the essential steps to set presentation language and shape text using Aspose.Slides for Java.
## Prerequisites
Before diving into the tutorial, ensure you have the following:
- Java Development Kit (JDK) installed
- Aspose.Slides for Java library, which you can download from [here](https://releases.aspose.com/slides/java/)
- Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse set up on your system
- Basic knowledge of Java programming language
## Import Packages
To begin, import the necessary Aspose.Slides packages in your Java file:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Step 1: Create a Presentation Object
Start by initializing a `Presentation` object:
```java
Presentation pres = new Presentation();
```
This creates a new PowerPoint presentation.
## Step 2: Add and Configure an AutoShape
Next, add an AutoShape to the first slide and configure its properties:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Here, we add a rectangle AutoShape at coordinates (50, 50) with dimensions 200x50 pixels.
## Step 3: Set Text and Language
Set text content and specify the language for spellchecking:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
Replace `"Text to apply spellcheck language"` with your desired text. The language ID `"en-EN"` specifies English (United States).
## Step 4: Save the Presentation
Save the modified presentation to a specified output directory:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
Ensure to replace `"Your Output Directory"` with your actual directory path where you want to save the file.
## Step 5: Dispose of Resources
Properly dispose of the `Presentation` object to release resources:
```java
pres.dispose();
```
This step is crucial to avoid memory leaks.

## Conclusion
In conclusion, Aspose.Slides for Java simplifies the process of creating and manipulating PowerPoint presentations programmatically. By following these steps, you can efficiently set the presentation language and configure text properties according to your requirements.
## FAQ's
### Can I use Aspose.Slides for Java to create PowerPoint presentations from scratch?
Yes, Aspose.Slides provides comprehensive APIs to create presentations entirely programmatically.
### How can I apply different fonts to text in PowerPoint slides using Aspose.Slides for Java?
You can set font properties through `IPortionFormat` objects associated with text portions.
### Is there a trial version available for Aspose.Slides for Java?
Yes, you can get a free trial from [here](https://releases.aspose.com/).
### Where can I find documentation for Aspose.Slides for Java?
Detailed documentation is available [here](https://reference.aspose.com/slides/java/).
### What support options are available for Aspose.Slides for Java?
You can visit the Aspose.Slides forum [here](https://forum.aspose.com/c/slides/11) for community support.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
