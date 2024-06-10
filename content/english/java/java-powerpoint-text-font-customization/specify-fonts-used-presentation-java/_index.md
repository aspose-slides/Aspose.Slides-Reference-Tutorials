---
title: Specify Fonts Used in Presentation with Java
linktitle: Specify Fonts Used in Presentation with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 22
url: /java/java-powerpoint-text-font-customization/specify-fonts-used-presentation-java/
---

## Complete Source Code
```java


import com.aspose.slides.IPresentation;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;


import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;


public class SpecifyFontsUsedWithPresentation
{
    public static void main(String[] args) throws IOException
    {
        // ExStart:SpecifyFontsUsedWithPresentation
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        byte[] memoryFont1 = Files.readAllBytes(Paths.get(dataDir + "customfonts\\CustomFont1.ttf"));
        byte[] memoryFont2 = Files.readAllBytes(Paths.get(dataDir + "customfonts\\CustomFont2.ttf"));

        LoadOptions loadOptions = new LoadOptions();
        loadOptions.getDocumentLevelFontSources().setFontFolders(new String[]{"assets\\fonts", "global\\fonts"});
        loadOptions.getDocumentLevelFontSources().setMemoryFonts(new byte[][]{memoryFont1, memoryFont2});

        IPresentation presentation = new Presentation("MyPresentation.pptx", loadOptions);
        try
        {
            //work with the presentation
            //CustomFont1, CustomFont2 as well as fonts from assets\fonts & global\fonts folders and their subfolders are available to the presentation
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        // ExEnd:SpecifyFontsUsedWithPresentation
    }
}


```
