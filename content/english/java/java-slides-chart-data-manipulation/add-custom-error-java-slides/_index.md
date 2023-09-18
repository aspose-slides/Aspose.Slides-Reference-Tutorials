---
title: Add Custom Error in Java Slides
linktitle: Add Custom Error in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-slides-chart-data-manipulation/add-custom-error-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Creating empty presentation
        Presentation presentation = new Presentation();
        try
        {
            // Creating a bubble chart
            IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
            // Adding custom Error bars and setting its format
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
            IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
            errBarX.setVisible(true);
            errBarY.setVisible(true);
            errBarX.setValueType(ErrorBarValueType.Custom);
            errBarY.setValueType(ErrorBarValueType.Custom);
            // Accessing chart series data point and setting error bars values for individual point
            IChartDataPointCollection points = series.getDataPoints();
            points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
            points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
            points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
            points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
            // Setting error bars for chart series points
            for (int i = 0; i < points.size(); i++)
            {
                points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
                points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
                points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
                points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
            }
            // Saving presentation
            presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
