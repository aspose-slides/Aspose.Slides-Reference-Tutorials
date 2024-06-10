---
title: Update Existing Table in PowerPoint using Java
linktitle: Update Existing Table in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-table-formatting-updates/update-existing-table-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class UpdateExistingTable
{
    public static void main(String[] args)
    {
        //ExStart:UpdateExistingTable
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate Presentation class that represents PPTX// Instantiate Presentation class that represents PPTX
        Presentation pres = new Presentation(dataDir + "UpdateExistingTable.pptx");
        try
        {

            // Access the first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Initialize null TableEx
            ITable tbl = null;

            // Iterate through the shapes and set a reference to the table found
            for (IShape shp : sld.getShapes())
                if (shp instanceof ITable)
                    tbl = (ITable) shp;

            // Set the text of the first column of second row
            tbl.getRows().get_Item(0).get_Item(1).getTextFrame().setText("New");

            //Write the PPTX to Disk
            pres.save(dataDir + "table1_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:UpdateExistingTable
    }
}

```
