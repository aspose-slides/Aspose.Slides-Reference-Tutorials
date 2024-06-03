---
title: Fill Shapes with Solid Color in PowerPoint
linktitle: Fill Shapes with Solid Color in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

import java.awt.*;


public class FillShapeswithSolidColor
{
    public static void main(String[] args)
    {
        //ExStart:FillShapeswithSolidColor
        // The path to the documents directory.                    
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation presentation = new Presentation();

        // Get the first slide
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add autoshape of rectangle type
        IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);

        // Set the fill type to Solid
        shape.getFillFormat().setFillType(FillType.Solid);

        // Set the color of the rectangle
        shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);

        //Write the PPTX file to disk
        presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
        //ExEnd:FillShapeswithSolidColor
    }
}



```
