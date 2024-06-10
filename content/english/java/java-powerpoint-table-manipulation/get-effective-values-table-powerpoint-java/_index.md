---
title: Get Effective Values of Table in PowerPoint with Java
linktitle: Get Effective Values of Table in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-table-manipulation/get-effective-values-table-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class GetEffectiveValuesOfTable
{
    public static void main(String[] args)
    {

        //ExStart:GetEffectiveValuesOfTable

        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation pres = new Presentation(dataDir + "pres.pptx");
        try
        {
            ITable tbl = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ITableFormatEffectiveData tableFormatEffective = tbl.getTableFormat().getEffective();
            IRowFormatEffectiveData rowFormatEffective = tbl.getRows().get_Item(0).getRowFormat().getEffective();
            IColumnFormatEffectiveData columnFormatEffective = tbl.getColumns().get_Item(0).getColumnFormat().getEffective();
            ICellFormatEffectiveData cellFormatEffective = tbl.get_Item(0, 0).getCellFormat().getEffective();

            IFillFormatEffectiveData tableFillFormatEffective = tableFormatEffective.getFillFormat();
            IFillFormatEffectiveData rowFillFormatEffective = rowFormatEffective.getFillFormat();
            IFillFormatEffectiveData columnFillFormatEffective = columnFormatEffective.getFillFormat();
            IFillFormatEffectiveData cellFillFormatEffective = cellFormatEffective.getFillFormat();

        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:GetEffectiveValuesOfTable

    }
}


```
