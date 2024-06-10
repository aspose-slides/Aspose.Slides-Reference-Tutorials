---
title: Merge Cells in PowerPoint Table with Java
linktitle: Merge Cells in PowerPoint Table with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;


public class MergeCell
{
    public static void main(String[] args)
    {
        //ExStart:MergeCell
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate Presentation class that represents PPTX file
        Presentation presentation = new Presentation();
        try
        {

            // Access first slide
            ISlide slide = presentation.getSlides().get_Item(0);

            // Define columns with widths and rows with heights
            double[] dblCols = {70, 70, 70, 70};
            double[] dblRows = {70, 70, 70, 70};

            // Add table shape to slide
            ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);

            // Set border format for each cell
            for (IRow row : table.getRows())
            {
                for (ICell cell : (Iterable<ICell>) row)
                {
                    cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
                    cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
                    cell.getCellFormat().getBorderTop().setWidth(5);

                    cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
                    cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
                    cell.getCellFormat().getBorderBottom().setWidth(5);

                    cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
                    cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
                    cell.getCellFormat().getBorderLeft().setWidth(5);

                    cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
                    cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
                    cell.getCellFormat().getBorderRight().setWidth(5);

                }
            }

            // Merging cells (1, 1) x (2, 1)
            table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);

            // Merging cells (1, 2) x (2, 2)
            table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);

            // Merging cells (1, 2) x (2, 2)
            table.mergeCells(table.get_Item(1, 1), table.get_Item(1, 2), true);

            //Write PPTX to Disk
            presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:MergeCell
    }
}





```
