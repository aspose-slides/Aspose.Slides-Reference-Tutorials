---
title: Add Assistant Node to SmartArt in Java PowerPoint
linktitle: Add Assistant Node to SmartArt in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


public class AssistantNode
{
    public static void main(String[] args)
    {
        //ExStart:AssistantNode
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Creating a presentation instance
        Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
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
                    // Traversing through all nodes of SmartArt shape

                    for (ISmartArtNode node : smart.getAllNodes())
                    {
                        String tc = node.getTextFrame().getText();
                        // Check if node is Assitant node
                        if (node.isAssistant())
                        {
                            // Setting Assitant node to false and making it normal node
                            node.setAssistant(false);
                        }
                    }
                }
            }
            // Save Presentation
            pres.save(dataDir + "ChangeAssitantNode_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:AssistantNode
    }
}

```
