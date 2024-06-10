---
title: Export HTML Text in PowerPoint using Java
linktitle: Export HTML Text in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-text-alignment-formatting/export-html-text-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.IAutoShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;


import java.io.*;
import java.nio.charset.StandardCharsets;


public class ExportingHTMLText
{
    public static void main(String[] args) throws IOException
    {
        //ExStart:ExportingHTMLText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Load the presentation file
        Presentation pres = new Presentation(dataDir + "ExportingHTMLText.pptx");
        try
        {

            // Acesss the default first slide of presentation
            ISlide slide = pres.getSlides().get_Item(0);

            // Desired index
            int index = 0;

            // Accessing the added shape
            IAutoShape ashape = (IAutoShape) slide.getShapes().get_Item(index);

            //Writing Paragraphs data to HTML by providing paragraph starting index, total paragraphs to be copied
            Writer out = new BufferedWriter(new OutputStreamWriter(new FileOutputStream(dataDir + "output_out.html"), StandardCharsets.UTF_8));
            try
            {
                out.write(ashape.getTextFrame().getParagraphs().exportToHtml(0, ashape.getTextFrame().getParagraphs().getCount(), null));
            }
            finally
            {
                out.close();
            }
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:ExportingHTMLText
    }
}

```
