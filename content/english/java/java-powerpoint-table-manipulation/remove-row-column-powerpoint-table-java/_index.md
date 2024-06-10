---
title: Remove Row or Column in PowerPoint Table using Java
linktitle: Remove Row or Column in PowerPoint Table using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-powerpoint-table-manipulation/remove-row-column-powerpoint-table-java/
---

## Complete Source Code
```java


import com.aspose.slides.ISlide;
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;


import java.io.File;


public class RemovingRowColumn
{
    public static void main(String[] args)
    {
        //ExStart:RemovingRowColumn
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            double[] colWidth = new double[]{100, 50, 30};
            double[] rowHeight = new double[]{30, 50, 30};

            ITable table = slide.getShapes().addTable(100, 100, colWidth, rowHeight);
            table.getRows().removeAt(1, false);
            table.getColumns().removeAt(1, false);
            pres.save(dataDir + "TestTable_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:RemovingRowColumn
    }
}

```
