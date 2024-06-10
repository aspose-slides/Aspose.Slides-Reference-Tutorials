---
title: Load External Font in PowerPoint with Java
linktitle: Load External Font in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-font-management-text-replacement/load-external-font-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.FontsLoader;
import com.aspose.slides.Presentation;


import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;


public class LoadExternalFont

{
    public static void main(String[] args) throws IOException
    {
        // ExStart:LoadExternalFont

        // The path to the documents directory.

        String dataDir = "Your Document Directory";


        // loading presentation uses SomeFont which is not installed on the system
        Presentation pres = new Presentation();
        try
        {
            // load SomeFont from file into the byte array
            Path path = Paths.get(dataDir + "CustomFonts.ttf");
            byte[] fontData = Files.readAllBytes(path);

            // load font represented as byte array
            FontsLoader.loadExternalFont(fontData);

            // font SomeFont will be available during the rendering or other operations
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
    }

    // ExEnd:LoadExternalFont

}



```
