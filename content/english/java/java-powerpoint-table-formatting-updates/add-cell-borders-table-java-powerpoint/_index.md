---
title: Add Cell Borders to Table in Java PowerPoint
linktitle: Add Cell Borders to Table in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-table-formatting-updates/add-cell-borders-table-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.io.File;


public class TableWithCellBorders
{
    public static void main(String[] args)
    {
        //ExStart:TableWithCellBorders
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        // Instantiate Presentation class that represents PPTX file
        Presentation pres = new Presentation();
        try
        {

            // Access first slide
            Slide sld = (Slide) pres.getSlides().get_Item(0);

            // Define columns with widths and rows with heights
            double[] dblCols = {50, 50, 50, 50};
            double[] dblRows = {50, 30, 30, 30, 30};

            // Add table shape to slide

            // Add table shape to slide
            ITable tbl = sld.getShapes().addTable(100, 50, dblCols, dblRows);

            // Set border format for each cell
            for (IRow row : tbl.getRows())
                for (ICell cell : (Iterable<ICell>) row)
                {
                    cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.NoFill);
                    cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.NoFill);
                    cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.NoFill);
                    cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.NoFill);
                }

            //Write PPTX to Disk
            pres.save(dataDir + "table_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:TableWithCellBorders
    }
}

```
