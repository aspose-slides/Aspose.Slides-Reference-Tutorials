---
title: Set Fill Format for SmartArt Shape Node in Java
linktitle: Set Fill Format for SmartArt Shape Node in Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-smartart-manipulation/set-fill-format-smartart-shape-node-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;


public class FillFormatSmartArtShapeNode
{
    public static void main(String[] args)
    {
        //ExStart.getFillFormat().martArtShapeNode
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Accessing the slide
            ISlide slide = presentation.getSlides().get_Item(0);

            // Adding SmartArt shape and nodes
            ISmartArt chevron = slide.getShapes().addSmartArt(10, 10, 800, 60, SmartArtLayoutType.ClosedChevronProcess);
            ISmartArtNode node = chevron.getAllNodes().addNode();
            node.getTextFrame().setText("Some text");

            // Setting node fill color
            for (ISmartArtShape item : node.getShapes())
            {
                item.getFillFormat().setFillType(FillType.Solid);
                item.getFillFormat().getSolidFillColor().setColor(Color.RED);
            }

            // Saving Presentation
            presentation.save(dataDir + "FillFormat_SmartArt_ShapeNode_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd.getFillFormat().martArtShapeNode
    }
}


```
