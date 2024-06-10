---
title: Rotate Text in PowerPoint using Java
linktitle: Rotate Text in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;


public class RotatingText
{
    public static void main(String[] args)
    {
        //ExStart:RotatingText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation presentation = new Presentation();

        // Get the first slide 
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add an AutoShape of Rectangle type
        IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);

        // Add TextFrame to the Rectangle
        ashp.addTextFrame(" ");
        ashp.getFillFormat().setFillType(FillType.NoFill);

        // Accessing the text frame
        ITextFrame txtFrame = ashp.getTextFrame();
        txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);

        // Create the Paragraph object for text frame
        IParagraph para = txtFrame.getParagraphs().get_Item(0);

        // Create Portion object for paragraph
        IPortion portion = para.getPortions().get_Item(0);
        portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
        portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
        portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);

        // Save Presentation
        presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
        //ExEnd:RotatingText
    }
}

```
