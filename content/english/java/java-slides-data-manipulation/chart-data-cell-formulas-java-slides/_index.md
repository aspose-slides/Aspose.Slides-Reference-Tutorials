---
title: Chart Data Cell Formulas in Java Slides
linktitle: Chart Data Cell Formulas in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-data-manipulation/chart-data-cell-formulas-java-slides/
---

## Complete Source Code
```java
        String outpptxFile = RunExamples.getOutPath() + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
        Presentation presentation = new Presentation();
        try
        {
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
            IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
            IChartDataCell cell1 = workbook.getCell(0, "B2");
            cell1.setFormula("1 + SUM(F2:H5)");
            IChartDataCell cell2 = workbook.getCell(0, "C2");
            cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
            workbook.calculateFormulas();
            presentation.save(outpptxFile, SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
