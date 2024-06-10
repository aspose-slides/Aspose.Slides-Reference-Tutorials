---
title: Remove Node from SmartArt in PowerPoint using Java
linktitle: Remove Node from SmartArt in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-smartart-manipulation/remove-node-smartart-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


public class RemoveNode
{
    public static void main(String[] args)
    {
        //ExStart:RemoveNode
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Load the desired the presentation
        Presentation pres = new Presentation(dataDir + "RemoveNode.pptx");
        try
        {

            // Traverse through every shape inside first slide
            for (IShape shape : pres.getSlides().get_Item(0).getShapes())
            {

                // Check if shape is of SmartArt type
                if (shape instanceof ISmartArt)
                {
                    // Typecast shape to SmartArtEx
                    ISmartArt smart = (ISmartArt) shape;

                    if (smart.getAllNodes().size() > 0)
                    {
                        // Accessing SmartArt node at index 0
                        ISmartArtNode node = smart.getAllNodes().get_Item(0);

                        // Removing the selected node
                        smart.getAllNodes().removeNode(node);

                    }
                }
            }

            // Save Presentation
            pres.save(dataDir + "RemoveSmartArtNode_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:RemoveNode
    }
}

```
