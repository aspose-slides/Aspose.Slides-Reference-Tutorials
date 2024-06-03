---
title: Create Group Shape in PowerPoint
linktitle: Create Group Shape in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;


public class CreateGroupShape
{
    public static void main(String[] args)
    {
        //ExStart:CreateGroupShape
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate Prseetation class 
        Presentation pres = new Presentation();
        try
        {
            // Get the first slide 
            ISlide sld = pres.getSlides().get_Item(0);

            // Accessing the shape collection of slides 
            IShapeCollection slideShapes = sld.getShapes();

            // Adding a group shape to the slide 
            IGroupShape groupShape = slideShapes.addGroupShape();

            // Adding shapes inside added group shape 
            groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
            groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
            groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
            groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);

            // Adding group shape frame 
            groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));

            // Write the PPTX file to disk 
            pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:CreateGroupShape
    }
}





```
