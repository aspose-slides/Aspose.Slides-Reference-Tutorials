---
title: Apply 3D Rotation Effect on Shapes in PowerPoint
linktitle: Apply 3D Rotation Effect on Shapes in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to apply 3D rotation effects on shapes in PowerPoint using Aspose.Slides for Java with this comprehensive, step-by-step tutorial.
weight: 12
url: /java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Are you ready to take your PowerPoint presentations to the next level? Adding 3D rotation effects can make your slides more dynamic and engaging. Whether you are a seasoned developer or just getting started, this step-by-step tutorial will show you how to apply 3D rotation effects to shapes in PowerPoint using Aspose.Slides for Java. Let's dive right in!
## Prerequisites
Before we start, ensure you have the following in place:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: Download the latest version of Aspose.Slides for Java from the [download link](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Use an IDE like IntelliJ IDEA or Eclipse for coding.
4. A valid license: If you don’t have a license, you can get a [temporary license](https://purchase.aspose.com/temporary-license/) to try out the features.
## Import Packages
First, let's import the necessary packages in your Java project. These imports will help you handle presentations and shapes with Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Step 1: Set Up Your Project
Before diving into the code, set up your project environment. Ensure you have added Aspose.Slides for Java to your project's dependencies.
Add Aspose.Slides to Your Project:
1. Download the Aspose.Slides JAR files from the [download page](https://releases.aspose.com/slides/java/).
2. Add these JAR files to your project's build path.
## Step 2: Create a New PowerPoint Presentation
In this step, we will create a new PowerPoint presentation.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an instance of Presentation class
Presentation pres = new Presentation();
```
This code snippet initializes a new presentation object where we will add our shapes.
## Step 3: Add a Rectangle Shape
Next, let's add a rectangle shape to the first slide.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
This code adds a rectangle shape at the specified position and size on the first slide.
## Step 4: Apply 3D Rotation to the Rectangle
Now, let's apply a 3D rotation effect to the rectangle shape.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Here, we set the depth, camera rotation angles, camera type, and lighting type to give our rectangle a 3D look.
## Step 5: Add a Line Shape
Let's add another shape, this time a line, to the slide.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
This code places a line shape on the slide.
## Step 6: Apply 3D Rotation to the Line
Finally, we will apply a 3D rotation effect to the line shape.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Similar to the rectangle, we set the 3D properties for the line shape.
## Step 7: Save the Presentation
After adding and configuring your shapes, save the presentation.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
This code saves your presentation with the specified filename in the desired format.
## Conclusion
Congratulations! You've successfully applied 3D rotation effects to shapes in a PowerPoint presentation using Aspose.Slides for Java. By following these steps, you can create visually appealing and dynamic presentations. For further customization and more advanced features, refer to the [Aspose.Slides documentation](https://reference.aspose.com/slides/java/).
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a powerful API to create, modify, and manipulate PowerPoint presentations programmatically.
### Can I try Aspose.Slides for Java for free?
Yes, you can get a [free trial](https://releases.aspose.com/) or a [temporary license](https://purchase.aspose.com/temporary-license/) to test the features.
### What types of shapes can I add 3D effects to in Aspose.Slides?
You can add 3D effects to various shapes like rectangles, lines, ellipses, and custom shapes.
### How do I get support for Aspose.Slides for Java?
You can visit the [support forum](https://forum.aspose.com/c/slides/11) for assistance and to discuss any issues.
### Can I use Aspose.Slides for Java in commercial projects?
Yes, but you need to purchase a license. You can buy one from the [purchase page](https://purchase.aspose.com/buy).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
