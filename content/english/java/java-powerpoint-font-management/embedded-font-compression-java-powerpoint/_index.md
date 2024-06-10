---
title: Embedded Font Compression in Java PowerPoint
linktitle: Embedded Font Compression in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-font-management/embedded-font-compression-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.nio.file.Files;
import java.nio.file.Paths;

public class EmbeddedFontCompression
{
    public static void main(String[] args) throws Exception
    {
        String presentationName = "Your Document Directory";
        String outPath = "Your Output Directory" + "presWithEmbeddedFonts-out.pptx";

        //ExStart:EmbeddedFontCompression
        Presentation pres = new Presentation(presentationName);
        try {
            // Compress embedded fonts
            Compress.compressEmbeddedFonts(pres);
            // Save result
            pres.save(outPath, SaveFormat.Pptx);
        } finally {
            if(pres != null) pres.dispose();
        }

        // Get source file info
        byte[] sourceFile = Files.readAllBytes(Paths.get(presentationName));
        System.out.println(String.format("Source file size = %d bytes", sourceFile.length));
        // Get result file info
        byte[] outputFile = Files.readAllBytes(Paths.get(outPath));
        System.out.println(String.format("Result file size = %d bytes", outputFile.length));
        //ExEnd:EmbeddedFontCompression
    }

}

```
