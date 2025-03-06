---
title: Change SmartArt State in PowerPoint with Java
linktitle: Change SmartArt State in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to change SmartArt states in PowerPoint presentations using Java and Aspose.Slides. Enhance your presentation automation skills.
weight: 21
url: /java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Change SmartArt State in PowerPoint with Java

## Introduction
In this tutorial, you'll learn how to manipulate SmartArt objects in PowerPoint presentations using Java with the Aspose.Slides library. SmartArt is a powerful feature in PowerPoint that allows you to create visually appealing diagrams and graphics.
## Prerequisites
Before you begin, make sure you have the following:
1. Java Development Kit (JDK): Ensure that you have Java installed on your system. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java: Download and install the Aspose.Slides for Java library from the [website](https://releases.aspose.com/slides/java/).

## Import Packages
To start working with Aspose.Slides in your Java project, import the necessary packages:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
Now let's break down the example code provided into multiple steps:
## Step 1: Initialize Presentation Object
```java
Presentation presentation = new Presentation();
```
Here, we create a new `Presentation` object, which represents a PowerPoint presentation.
## Step 2: Add SmartArt Object
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
This step adds a SmartArt object to the first slide of the presentation. We specify the position and dimensions of the SmartArt object, as well as the layout type (in this case, `BasicProcess`).
## Step 3: Set SmartArt State
```java
smart.setReversed(true);
```
Here, we set the state of the SmartArt object. In this example, we're reversing the direction of the SmartArt.
## Step 4: Check SmartArt State
```java
boolean flag = smart.isReversed();
```
We can also check the current state of the SmartArt object. This line retrieves whether the SmartArt is reversed or not and stores it in the `flag` variable.
## Step 5: Save Presentation
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
Finally, we save the modified presentation to a specified location on the disk.

## Conclusion
In this tutorial, we've learned how to change the state of SmartArt objects in PowerPoint presentations using Java and the Aspose.Slides library. With this knowledge, you can create dynamic and engaging presentations programmatically.
## FAQ's
### Can I modify other properties of SmartArt using Aspose.Slides for Java?
Yes, you can modify various aspects of SmartArt objects, such as colors, styles, and layouts, using Aspose.Slides.
### Is Aspose.Slides compatible with different versions of PowerPoint?
Yes, Aspose.Slides supports PowerPoint presentations across different versions, ensuring compatibility and seamless integration.
### Can I create custom SmartArt layouts with Aspose.Slides?
Absolutely! Aspose.Slides provides APIs to create custom SmartArt layouts tailored to your specific needs.
### Does Aspose.Slides offer support for other file formats besides PowerPoint?
Yes, Aspose.Slides supports a wide range of file formats, including PPTX, PPT, PDF, and more.
### Is there a community forum where I can get help with Aspose.Slides-related questions?
Yes, you can visit the Aspose.Slides forum at [here](https://forum.aspose.com/c/slides/11) for assistance and discussions.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
