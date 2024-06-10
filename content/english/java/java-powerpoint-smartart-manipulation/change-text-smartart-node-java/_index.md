---
title: Change Text on SmartArt Node using Java
linktitle: Change Text on SmartArt Node using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 22
url: /java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ChangeTextOnSmartArtNode
{
    public static void main(String[] args)
    {
        //ExStart:ChangeTextOnSmartArtNode
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Add SmartArt BasicProcess 
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);

            // Obtain the reference of a node by using its Index  
            ISmartArtNode node = smart.getNodes().get_Item(1); // select second root node

            // Setting the text of the TextFrame 
            node.getTextFrame().setText("Second root node");

            // Saving Presentation
            presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ChangeTextOnSmartArtNode
    }
}


```
