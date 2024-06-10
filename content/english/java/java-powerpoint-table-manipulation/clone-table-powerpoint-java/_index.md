---
title: Clone Table in PowerPoint with Java
linktitle: Clone Table in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-table-manipulation/clone-table-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.ISlide;
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;



public class CloningInTable
{
    public static void main(String[] args)
    {
        //ExStart:CloningInTable
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate presentationentation class that representationents PPTX file
        Presentation presentation = new Presentation(dataDir + "presentation.pptx");
        try
        {
            // Access first slide
            ISlide sld = presentation.getSlides().get_Item(0);

            // Define columns with widths and rows with heights
            double[] dblCols = {50, 50, 50};
            double[] dblRows = {50, 30, 30, 30, 30};

            // Add table shape to slide
            ITable table = sld.getShapes().addTable(100, 50, dblCols, dblRows);


            // Add text to the row 1 cell 1
            table.get_Item(0, 0).getTextFrame().setText("Row 1 Cell 1");

            // Add text to the row 1 cell 2
            table.get_Item(1, 0).getTextFrame().setText("Row 1 Cell 2");

            // Clone Row 1 at end of table
            table.getRows().addClone(table.getRows().get_Item(0), false);

            // Add text to the row 2 cell 1
            table.get_Item(0, 1).getTextFrame().setText("Row 2 Cell 1");

            // Add text to the row 2 cell 2
            table.get_Item(1, 1).getTextFrame().setText("Row 2 Cell 2");


            // Clone Row 2 as 4th row of table
            table.getRows().insertClone(3, table.getRows().get_Item(1), false);

            //Cloning first column at end
            table.getColumns().addClone(table.getColumns().get_Item(0), false);

            //Cloning 2nd column at 4th column index
            table.getColumns().insertClone(3, table.getColumns().get_Item(1), false);


            // Write PPTX to Disk
            presentation.save(dataDir + "table_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
}
//ExEnd:CloningInTable
    
   
```
