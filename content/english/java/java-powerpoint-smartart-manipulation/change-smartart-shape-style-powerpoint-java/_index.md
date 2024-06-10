---
title: Change SmartArt Shape Style in PowerPoint with Java
linktitle: Change SmartArt Shape Style in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 23
url: /java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ChangSmartArtShapeStyle
{
    public static void main(String[] args)
    {
        //ExStart:ChangSmartArtShapeStyle
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
        try
        {
            // Traverse through every shape inside first slide
            for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
            {
                // Check if shape is of SmartArt type
                if (shape instanceof ISmartArt)
                {
                    // Typecast shape to SmartArtEx
                    ISmartArt smart = (ISmartArt) shape;

                    // Checking SmartArt style
                    if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
                    {
                        // Changing SmartArt Style
                        smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
                    }
                }
            }

            // Saving Presentation
            presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ChangSmartArtShapeStyle
    }
}


```
