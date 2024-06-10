---
title: Specify Default Text Language in Java PowerPoint
linktitle: Specify Default Text Language in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 21
url: /java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


public class SpecifyDefaultTextLanguage
{
    public static void main(String[] args)
    {
        //ExStart:SpecifyDefaultTextLanguage
        LoadOptions loadOptions = new LoadOptions();
        loadOptions.setDefaultTextLanguage("en-US");
        Presentation pres = new Presentation(loadOptions);
        try
        {
            // Add new rectangle shape with text
            IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
            shp.getTextFrame().setText("New Text");

            // Check the first portion language
            System.out.println(shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().getLanguageId());
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:SpecifyDefaultTextLanguage
    }
}

```
