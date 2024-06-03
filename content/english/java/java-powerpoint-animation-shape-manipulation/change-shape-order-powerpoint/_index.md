---
title: Change Shape Order in PowerPoint
linktitle: Change Shape Order in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.shapes;

import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;


public class ChangeShapeOrder
{
    public static void main(String[] args)
    {
        //ExStart:ChangeShapeOrder
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Shapes();

        Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
        try
        {
            ISlide slide = presentation1.getSlides().get_Item(0);
            IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
            shp3.getFillFormat().setFillType(FillType.NoFill);
            shp3.addTextFrame(" ");

            ITextFrame txtFrame = shp3.getTextFrame();
            IParagraph para = txtFrame.getParagraphs().get_Item(0);
            IPortion portion = para.getPortions().get_Item(0);
            portion.setText("Watermark Text Watermark Text Watermark Text");
            shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
            slide.getShapes().reorder(2, shp3);
            presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation1 != null) presentation1.dispose();
        }
        //ExEnd:ChangeShapeOrder
    }
}




```
