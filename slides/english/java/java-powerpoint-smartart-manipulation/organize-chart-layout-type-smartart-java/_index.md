---
title: Organize Chart Layout Type in SmartArt using Java
linktitle: Organize Chart Layout Type in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Master organizing chart layout types in SmartArt using Java with Aspose.Slides, enhancing presentation visuals effortlessly.
weight: 13
url: /java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Organize Chart Layout Type in SmartArt using Java

## Introduction
In this tutorial, we'll walk through the process of organizing chart layout type in SmartArt using Java, specifically leveraging the Aspose.Slides library. SmartArt in presentations can greatly enhance the visual appeal and clarity of your data, making it essential to master its manipulation.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Slides library downloaded and set up. If you haven't already, download it from [here](https://releases.aspose.com/slides/java/).
3. Basic understanding of Java programming.

## Import Packages
Firstly, import the necessary packages:
```java
import com.aspose.slides.*;
```
Let's break down the example provided into multiple steps:
## Step 1: Initialize Presentation Object
```java
Presentation presentation = new Presentation();
```
Create a new presentation object.
## Step 2: Add SmartArt to Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Add SmartArt to the desired slide with specified dimensions and layout type.
## Step 3: Set Organization Chart Layout
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Set the organization chart layout type. In this example, we're using the Left Hanging layout.
## Step 4: Save Presentation
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Save the presentation with the organized chart layout.

## Conclusion
Mastering the organization of chart layout types in SmartArt using Java empowers you to create visually engaging presentations with ease. With Aspose.Slides, the process becomes streamlined and efficient, allowing you to focus on crafting impactful content.
## FAQ's
### Is Aspose.Slides compatible with different Java development environments?
Yes, Aspose.Slides is compatible with various Java development environments, ensuring flexibility for developers.
### Can I customize the appearance of SmartArt elements using Aspose.Slides?
Absolutely, Aspose.Slides provides extensive customization options for SmartArt elements, enabling you to tailor them to your specific requirements.
### Does Aspose.Slides offer comprehensive documentation for developers?
Yes, developers can refer to the detailed documentation provided by Aspose.Slides for Java, offering insights into its functionalities and usage.
### Is there a trial version available for Aspose.Slides?
Yes, you can access a free trial version of Aspose.Slides to explore its features before making a purchase decision.
### Where can I seek support for Aspose.Slides-related queries?
For any assistance or queries regarding Aspose.Slides, you can visit the support forum [here](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
