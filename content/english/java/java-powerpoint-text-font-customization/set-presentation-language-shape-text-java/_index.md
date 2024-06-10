---
title: Set Presentation Language and Shape Text in Java
linktitle: Set Presentation Language and Shape Text in Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

## Complete Source Code
```java


import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;



public class SettingPresentationLanguageAndShapeText
{
    public static void main(String[] args)
    {
        // ExStart:SettingPresentationLanguageAndShapeText
        Presentation pres = new Presentation();
        try
        {
            IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
            shape.addTextFrame("Text to apply spellcheck language");
            shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");

            pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
    }
    // ExEnd:SettingPresentationLanguageAndShapeText
}


```
