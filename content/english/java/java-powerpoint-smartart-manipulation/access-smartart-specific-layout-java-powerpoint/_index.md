---
title: Access SmartArt with Specific Layout in Java PowerPoint
linktitle: Access SmartArt with Specific Layout in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-smartart-manipulation/access-smartart-specific-layout-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.IShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArt;
import com.aspose.slides.SmartArtLayoutType;



public class AccessSmartArtParticularLayout
{
    public static void main(String[] args)
    {
        //ExStart:AccessSmartArtParticularLayout
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
        try
        {
            // Traverse through every shape inside first slide
            for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
            {
                // Check if shape is of SmartArt type
                if (shape instanceof SmartArt)
                {
                    // Typecast shape to SmartArtEx
                    SmartArt smart = (SmartArt) shape;

                    // Checking SmartArt Layout
                    if (smart.getLayout() == SmartArtLayoutType.BasicBlockList)
                    {
                        System.out.println("Do some thing here....");
                    }
                }
            }
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:AccessSmartArtParticularLayout
    }
}


```
