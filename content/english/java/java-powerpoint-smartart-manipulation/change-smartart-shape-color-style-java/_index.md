---
title: Change SmartArt Shape Color Style using Java
linktitle: Change SmartArt Shape Color Style using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-powerpoint-smartart-manipulation/change-smartart-shape-color-style-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ChangeSmartArtShapeColorStyle
{
    public static void main(String[] args)
    {
        //ExStart:ChangeSmartArtShapeColorStyle
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

                    // Checking SmartArt color type
                    if (smart.getColorStyle() == SmartArtColorType.ColoredFillAccent1)
                    {
                        // Changing SmartArt color type
                        smart.setColorStyle(SmartArtColorType.ColorfulAccentColors);
                    }
                }
            }

            // Saving Presentation
            presentation.save(dataDir + "ChangeSmartArtColorStyle_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ChangeSmartArtShapeColorStyle
    }
}


```
