---
title: Setting Date Format For Category Axis in Java Slides
linktitle: Setting Date Format For Category Axis in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 26
url: /java/java-slides-data-manipulation/setting-date-format-category-axis-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
            pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
    }
    public static String convertToOADate(GregorianCalendar date) throws ParseException
    {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899");
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
```
