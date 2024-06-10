---
title: Get Text from SmartArt Node in Java PowerPoint
linktitle: Get Text from SmartArt Node in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class GetTextFromSmartArtNode
{
    public static void main(String[] args)
    {
        // ExStart:GetTextFromSmartArtNode
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation("Presentation.pptx");
        try
        {
            ISlide slide = presentation.getSlides().get_Item(0);
            ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);

            ISmartArtNodeCollection smartArtNodes = smartArt.getAllNodes();
            for (ISmartArtNode smartArtNode : (Iterable<ISmartArtNode>) smartArtNodes)
            {
                for (ISmartArtShape nodeShape : smartArtNode.getShapes())
                {
                    if (nodeShape.getTextFrame() != null)
                        System.out.println(nodeShape.getTextFrame().getText());
                }
            }
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
    // ExEnd:GetTextFromSmartArtNode
}


```
