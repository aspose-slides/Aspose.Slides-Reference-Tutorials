---
title: Calculate Formulas in Java Slides
linktitle: Calculate Formulas in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-data-manipulation/calculate-formulas-java-slides/
---

## Complete Source Code
```java
        String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
        Presentation presentation = new Presentation();
        try {
            IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
            IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
            IChartDataCell cell = workbook.getCell(0, "A1");
            cell.setFormula("ABS(A2) + MAX(B2:C2)");
            workbook.getCell(0, "A2").setValue(-1);
            workbook.calculateFormulas();
            workbook.getCell(0, "B2").setFormula("2");
            workbook.calculateFormulas();
            workbook.getCell(0, "C2").setFormula("A2 + 4");
            workbook.calculateFormulas();
            cell.setFormula("MAX(2:2)");
            workbook.calculateFormulas();
            presentation.save(resultPath, SaveFormat.Pptx);
        } finally {
            if (presentation != null) presentation.dispose();
        }
```
