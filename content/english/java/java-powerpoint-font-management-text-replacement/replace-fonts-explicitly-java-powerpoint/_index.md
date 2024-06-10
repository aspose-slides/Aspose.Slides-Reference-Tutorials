---
title: Replace Fonts Explicitly in Java PowerPoint
linktitle: Replace Fonts Explicitly in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-font-management-text-replacement/replace-fonts-explicitly-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.FontData;
import com.aspose.slides.IFontData;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;



public class ReplaceFontsExplicitly
{
    public static void main(String[] args)
    {
        //ExStart:ReplaceFontsExplicitly
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Load presentation
        Presentation presentation = new Presentation(dataDir + "Fonts.pptx");

        // Load source font to be replaced
        IFontData sourceFont = new FontData("Arial");

        // Load the replacing font
        IFontData destFont = new FontData("Times New Roman");

        // Replace the fonts
        presentation.getFontsManager().replaceFont(sourceFont, destFont);

        // Save the presentation
        presentation.save(dataDir + "UpdatedFont_out.pptx", SaveFormat.Pptx);
        //ExEnd:ReplaceFontsExplicitly
    }
}

```
