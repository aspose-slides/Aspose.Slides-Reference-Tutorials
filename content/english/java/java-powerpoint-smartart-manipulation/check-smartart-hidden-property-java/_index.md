---
title: Check SmartArt Hidden Property using Java
linktitle: Check SmartArt Hidden Property using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 24
url: /java/java-powerpoint-smartart-manipulation/check-smartart-hidden-property-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class CheckSmartArtHiddenProperty
{
    public static void main(String[] args)
    {
        //ExStart:CheckSmartArtHiddenProperty
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Add SmartArt BasicProcess 
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.RadialCycle);

            // Add node on SmartArt 
            ISmartArtNode node = smart.getAllNodes().addNode();

            // Check isHidden property
            boolean hidden = node.isHidden(); // Returns true

            if (hidden)
            {
                // Do some actions or notifications
            }
            // Saving Presentation
            presentation.save(dataDir + "CheckSmartArtHiddenProperty_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:CheckSmartArtHiddenProperty
    }
}


```
