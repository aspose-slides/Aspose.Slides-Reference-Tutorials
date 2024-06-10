---
title: Use Custom Fonts in PowerPoint with Java
linktitle: Use Custom Fonts in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 25
url: /java/java-powerpoint-text-font-customization/use-custom-fonts-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.FontsLoader;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;



public class UseCustomFonts
{
    public static void main(String[] args)
    {
        //ExStart:UseCustomFonts
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        String[] loadFonts = new String[]{dataDir + "CustomFonts.ttf"};

        // Load the custom font directory fonts
        FontsLoader.loadExternalFonts(loadFonts);

        // Do Some work and perform presentation/slides rendering
        Presentation presentation = new Presentation(dataDir + "DefaultFonts.pptx");
        try
        {
            presentation.save(dataDir + "NewFonts_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }

        // Clear Font Cachce
        FontsLoader.clearCache();
        //ExEnd:UseCustomFonts
    }
}


```
