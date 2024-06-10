---
title: Set Font Fallback in Java PowerPoint
linktitle: Set Font Fallback in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

## Complete Source Code
```java



import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;

public class SetFontFallBack
{
    public static void main(String[] args)
    {

        //ExStart:SetFontFallBack


        long startUnicodeIndex = 0x0B80;

        long endUnicodeIndex = 0x0BFF;

        IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
        IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");

        //Also the fonts list can be added in several ways:
        String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};

        IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);

        //ExEnd:SetFontFallBack

    }
}


```
