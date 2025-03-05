---
title: Change SmartArt Layout in PowerPoint with Java
linktitle: Change SmartArt Layout in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to manipulate SmartArt layouts in PowerPoint presentations using Java with Aspose.Slides for Java.
type: docs
weight: 19
url: /java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---
## Introduction
In this tutorial, we'll explore how to manipulate SmartArt layouts in PowerPoint presentations using Java. SmartArt is a powerful feature in PowerPoint that allows users to create visually appealing graphics for various purposes, such as illustrating processes, hierarchies, relationships, and more.
## Prerequisites
Before we dive into the tutorial, make sure you have the following:
1. Java Development Environment: Ensure you have Java Development Kit (JDK) installed on your system.
2. Aspose.Slides Library: Download and install the Aspose.Slides for Java library from [here](https://releases.aspose.com/slides/java/).
3. Basic Understanding of Java: Familiarity with Java programming language fundamentals will be helpful.
4. Integrated Development Environment (IDE): Choose an IDE of your preference, such as Eclipse or IntelliJ IDEA.

## Import Packages
To begin, import the necessary packages into your Java project:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Step 1: Set Up Your Java Project Environment
Ensure your Java project is properly set up in your chosen IDE. Create a new Java project and include the Aspose.Slides library in your project's dependencies.
## Step 2: Create a New Presentation
Instantiate a new Presentation object to create a new PowerPoint presentation.
```java
Presentation presentation = new Presentation();
```
## Step 3: Add SmartArt Graphic
Add a SmartArt graphic to your presentation. Specify the position and dimensions of the SmartArt graphic on the slide.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Step 4: Change SmartArt Layout
Change the layout of the SmartArt graphic to your desired layout type.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Step 5: Save Presentation
Save the modified presentation to a specified directory on your system.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Manipulating SmartArt layouts in PowerPoint presentations using Java is a straightforward process with Aspose.Slides for Java. By following this tutorial, you can easily modify SmartArt graphics to suit your presentation needs.
## FAQ's
### Can I customize the appearance of SmartArt graphics using Aspose.Slides for Java?
Yes, you can customize various aspects of SmartArt graphics, such as colors, styles, and effects.
### Is Aspose.Slides compatible with different versions of PowerPoint?
Aspose.Slides supports PowerPoint presentations created in various versions of PowerPoint, ensuring compatibility across different platforms.
### Does Aspose.Slides offer support for other programming languages?
Yes, Aspose.Slides is available for multiple programming languages, including .NET, Python, and JavaScript.
### Can I create SmartArt graphics from scratch using Aspose.Slides?
Absolutely, you can create SmartArt graphics programmatically or modify existing ones to meet your requirements.
### Is there a community forum where I can seek help regarding Aspose.Slides?
Yes, you can visit the Aspose.Slides forum [here](https://forum.aspose.com/c/slides/11) to ask questions and engage with the community.
