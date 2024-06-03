---
title: Render Comments in PowerPoint
linktitle: Render Comments in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-rendering-techniques/render-comments-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.rendering.printing;

import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class RenderComments
{
    public static void main(String[] args) throws IOException
    {
        //ExStart:RenderComments
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Rendering();
        String resultPath = RunExamples.getOutPath() + "OutPresBitmap.png";

        Presentation pres = new Presentation(dataDir + "presentation.pptx");

        IRenderingOptions renderOptions = new RenderingOptions();
        renderOptions.getNotesCommentsLayouting().setCommentsAreaColor(Color.RED);
        renderOptions.getNotesCommentsLayouting().setCommentsAreaWidth(200);
        renderOptions.getNotesCommentsLayouting().setCommentsPosition(CommentsPositions.Right);
        renderOptions.getNotesCommentsLayouting().setNotesPosition(NotesPositions.BottomTruncated);

        try
        {
            BufferedImage image = new BufferedImage(740, 960, BufferedImage.TYPE_INT_ARGB);
            java.awt.Graphics graphics = image.createGraphics();
            try
            {
                pres.getSlides().get_Item(0).renderToGraphics(renderOptions, (Graphics2D) graphics);
            }
            finally
            {
                if (graphics != null) graphics.dispose();
            }
            ImageIO.write(image, "png", new File(resultPath));
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:RenderComments
    }
}
    



```
