---
title: Set Custom Bullets Number in Java PowerPoint
linktitle: Set Custom Bullets Number in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set custom bullet numbers in Java PowerPoint with Aspose.Slides, enhancing presentation clarity and structure programmatically.
weight: 15
url: /java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
In today's digital age, creating dynamic presentations is crucial for effectively communicating ideas and data. Aspose.Slides for Java provides a powerful toolkit to manipulate PowerPoint presentations programmatically, offering extensive features to enhance your presentation-building process. This article delves into setting custom bullet numbers in Java PowerPoint presentations using Aspose.Slides. Whether you're a seasoned developer or a newcomer, this tutorial will guide you step-by-step through the process, ensuring you can leverage this capability efficiently.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites set up on your development environment:
- Java Development Kit (JDK) installed
- Integrated Development Environment (IDE) such as IntelliJ IDEA or Eclipse
- Aspose.Slides for Java library. You can download it from [here](https://releases.aspose.com/slides/java/)
- Basic understanding of Java programming language and object-oriented concepts

## Import Packages
Firstly, import the necessary Aspose.Slides classes and other Java standard libraries:
```java
import com.aspose.slides.*;
```
## Step 1: Create a Presentation Object
Begin by creating a new PowerPoint presentation using Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Step 2: Add an AutoShape with Text
Insert an AutoShape (Rectangle) on the slide and access its text frame.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Step 3: Remove Default Paragraph
Remove the default existing paragraph from the text frame.
```java
textFrame.getParagraphs().removeAt(0);
```
## Step 4: Add Numbered Bullets
Add paragraphs with custom numbered bullets starting from specific numbers.
```java
// Example paragraph with bullet starting from 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Example paragraph with bullet starting from 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Example paragraph with bullet starting from 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Step 5: Save the Presentation
Finally, save the modified presentation to your desired location.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Conclusion
In conclusion, Aspose.Slides for Java simplifies the process of setting custom bullet numbers in PowerPoint presentations programmatically. By following the steps outlined in this tutorial, you can enhance the visual clarity and structure of your presentations efficiently.
## FAQ's
### Can I customize the appearance of bullets further?
Yes, Aspose.Slides offers extensive options to customize bullet type, size, color, and more.
### Is Aspose.Slides compatible with all versions of PowerPoint?
Aspose.Slides supports PowerPoint formats from 97-2003 to the latest versions.
### How can I get technical support for Aspose.Slides?
Visit [Aspose.Slides Forum](https://forum.aspose.com/c/slides/11) for technical assistance.
### Can I try Aspose.Slides before purchasing?
Yes, you can download a free trial from [here](https://releases.aspose.com/).
### Where can I purchase Aspose.Slides?
You can purchase Aspose.Slides from [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
