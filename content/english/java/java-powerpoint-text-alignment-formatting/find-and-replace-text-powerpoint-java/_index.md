---
title: Find and Replace Text in PowerPoint using Java
linktitle: Find and Replace Text in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-text-alignment-formatting/find-and-replace-text-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;

import java.awt.Color;

public class FindAndReplaceText
{
    public static void main(String[] args)
    {
        String presentationName = "Your Document Directory";
        String outPath = "Your Output Directory" + "TextReplaceExample-out.pptx";
          
        //ExStart:FindAndReplaceText
        Presentation pres = new Presentation(presentationName);
        try {
            PortionFormat format = new PortionFormat();
            format.setFontHeight(24f);
            format.setFontItalic(NullableBool.True);
            format.getFillFormat().setFillType(FillType.Solid);
            format.getFillFormat().getSolidFillColor().setColor(Color.RED);

            SlideUtil.findAndReplaceText(pres, true, "[this block] ", "my text", format);
            pres.save(outPath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
        //ExEnd:FontFamily
    }
}

```
