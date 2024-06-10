---
title: Replace Text in PowerPoint using Java
linktitle: Replace Text in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-font-management-text-replacement/replace-text-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ReplacingText
{
    public static void main(String[] args)
    {
        //ExStart:ReplacingText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate Presentation class that represents PPTX// Instantiate Presentation class that represents PPTX
        Presentation pres = new Presentation(dataDir + "ReplacingText.pptx");
        try
        {

            // Access first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Iterate through shapes to find the placeholder
            for (IShape shp : sld.getShapes())
                if (shp.getPlaceholder() != null)
                {
                    // Change the text of each placeholder
                    ((IAutoShape) shp).getTextFrame().setText("This is Placeholder");
                }

            // Save the PPTX to Disk
            pres.save(dataDir + "output_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:ReplacingText
    }
}

```
