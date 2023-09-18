---
title: Set Chart Data From Workbook in Java Slides
linktitle: Set Chart Data From Workbook in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-slides-data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Complete Source Code
```java
        String outPath = RunExamples.getOutPath() + "response2.pptx";
        Presentation pres = new Presentation();
        try {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
            chart.getChartData().getChartDataWorkbook().clear(0);
            Workbook workbook = null;
            try {
                workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
            } catch (Exception ex) {
                System.out.println(ex);
            }
            ByteArrayOutputStream mem = new ByteArrayOutputStream();
            workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
            mem.flush();
            chart.getChartData().writeWorkbookStream(mem.toByteArray());
            chart.getChartData().setRange("Sheet2!$A$1:$B$3");
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            series.getParentSeriesGroup().setColorVaried(true);
            pres.save(outPath, SaveFormat.Pptx);
        } catch(Exception e) {
        } finally {
            if (pres != null) pres.dispose();
        }
```
