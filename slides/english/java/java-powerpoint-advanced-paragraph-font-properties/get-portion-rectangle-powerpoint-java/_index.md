---
title: Get Portion Rectangle in PowerPoint with Java
linktitle: Get Portion Rectangle in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to get the portion rectangle in PowerPoint using Aspose.Slides for Java with this detailed, step-by-step tutorial. Perfect for Java developers.
weight: 12
url: /java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Get Portion Rectangle in PowerPoint with Java

## Introduction
Creating dynamic presentations in Java is a breeze with Aspose.Slides for Java. In this tutorial, we'll dive into the nitty-gritty of getting the portion rectangle in PowerPoint using Aspose.Slides. We'll cover everything from setting up your environment to breaking down the code step-by-step. So, let's get started!
## Prerequisites
Before we jump into the code, let's ensure you have everything you need to follow along smoothly:
1. Java Development Kit (JDK): Make sure you have JDK 8 or above installed on your machine.
2. Aspose.Slides for Java: Download the latest version from [here](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Eclipse, IntelliJ IDEA, or any other Java IDE of your choice.
4. Basic Knowledge of Java: Understanding of Java programming is essential.
## Import Packages
First things first, let's import the necessary packages. This will include Aspose.Slides and a few others for handling our task efficiently.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Step 1: Setting Up the Presentation
The first step is to create a new presentation. This will be our canvas to work on.
```java
Presentation pres = new Presentation();
```
## Step 2: Creating a Table
Now, let's add a table to the first slide of our presentation. This table will contain the cells where we'll add our text.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Step 3: Adding Paragraphs to Cells
Next, we'll create paragraphs and add them to a specific cell in the table. This involves clearing any existing text and then adding new paragraphs.
```java
// Create paragraphs
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Add text into the table cell
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Step 4: Adding a Text Frame to an AutoShape
To make our presentation more dynamic, we'll add a text frame to an AutoShape and set its alignment.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Step 5: Calculating Coordinates
We need to get the coordinates of the top-left corner of the table cell. This will help us place the shapes accurately.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Step 6: Adding Frames to Paragraphs and Portions
Using the `IParagraph.getRect()` and `IPortion.getRect()` methods, we can add frames to our paragraphs and portions. This involves iterating through the paragraphs and portions, creating shapes around them, and customizing their appearance.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Step 7: Adding Frames to AutoShape Paragraphs
Similarly, we'll add frames to the paragraphs in our AutoShape, enhancing the presentation's visual appeal.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Step 8: Saving the Presentation
Finally, we'll save our presentation to a specified path.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Step 9: Cleaning Up
It's good practice to dispose of the presentation object to free up resources.
```java
if (pres != null) pres.dispose();
```
## Conclusion
Congratulations! You've successfully learned how to get the portion rectangle in PowerPoint using Aspose.Slides for Java. This powerful library opens up a world of possibilities for creating dynamic and visually appealing presentations programmatically. Dive deeper into Aspose.Slides and explore more features to enhance your presentations further.
## FAQ's
### What is Aspose.Slides for Java?
Aspose.Slides for Java is a powerful library that allows developers to create, modify, and manipulate PowerPoint presentations programmatically.
### Can I use Aspose.Slides for Java in commercial projects?
Yes, Aspose.Slides for Java can be used in commercial projects. You can purchase a license from [here](https://purchase.aspose.com/buy).
### Is there a free trial available for Aspose.Slides for Java?
Yes, you can download a free trial from [here](https://releases.aspose.com/).
### Where can I find the documentation for Aspose.Slides for Java?
The documentation is available [here](https://reference.aspose.com/slides/java/).
### How can I get support for Aspose.Slides for Java?
You can get support from the Aspose forum [here](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
