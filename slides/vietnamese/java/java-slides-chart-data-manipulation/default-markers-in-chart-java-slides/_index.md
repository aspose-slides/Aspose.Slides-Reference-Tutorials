---
title: Điểm đánh dấu mặc định trong biểu đồ trong Java Slides
linktitle: Điểm đánh dấu mặc định trong biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Trang trình bày Java với các điểm đánh dấu mặc định trong biểu đồ bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn.
weight: 16
url: /vi/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Điểm đánh dấu mặc định trong biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo biểu đồ với các điểm đánh dấu mặc định bằng Aspose.Slides cho Java. Điểm đánh dấu mặc định là các ký hiệu hoặc hình dạng được thêm vào các điểm dữ liệu trong biểu đồ để làm nổi bật chúng. Chúng ta sẽ tạo một biểu đồ đường có các điểm đánh dấu để trực quan hóa dữ liệu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình.

## Bước 1: Tạo bản trình bày

Đầu tiên, hãy tạo một bài thuyết trình và thêm một slide vào đó. Sau đó chúng ta sẽ thêm biểu đồ vào slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Bước 2: Thêm biểu đồ đường bằng điểm đánh dấu

Bây giờ, hãy thêm biểu đồ đường có điểm đánh dấu vào trang chiếu. Chúng tôi cũng sẽ xóa mọi dữ liệu mặc định khỏi biểu đồ.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Bước 3: Điền dữ liệu biểu đồ

Chúng tôi sẽ điền vào biểu đồ dữ liệu mẫu. Trong ví dụ này, chúng tôi sẽ tạo hai chuỗi có điểm dữ liệu và danh mục.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Loạt 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Loạt 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Đang điền dữ liệu chuỗi
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Bước 4: Tùy chỉnh biểu đồ

Bạn có thể tùy chỉnh thêm biểu đồ, chẳng hạn như thêm chú giải và điều chỉnh hình thức của nó.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình cùng biểu đồ vào vị trí mà bạn mong muốn.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo biểu đồ dạng đường với các điểm đánh dấu mặc định bằng Aspose.Slides cho Java.

## Mã nguồn hoàn chỉnh cho các điểm đánh dấu mặc định trong biểu đồ trong Java Slides

```java
        // Đường dẫn đến thư mục tài liệu.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Lấy loạt biểu đồ thứ hai
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Hiện đang điền dữ liệu chuỗi
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Phần kết luận

Trong hướng dẫn toàn diện này, bạn đã học cách tạo Java Slides với các điểm đánh dấu mặc định trong biểu đồ bằng Aspose.Slides cho Java. Chúng tôi đã thực hiện toàn bộ quá trình, từ thiết lập bản trình bày đến tùy chỉnh giao diện của biểu đồ và lưu kết quả.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi các ký hiệu đánh dấu?

Bạn có thể tùy chỉnh các ký hiệu điểm đánh dấu bằng cách đặt kiểu điểm đánh dấu cho từng điểm dữ liệu. Sử dụng`IDataPoint.setMarkerStyle()` để thay đổi biểu tượng đánh dấu.

### Làm cách nào để điều chỉnh màu sắc của biểu đồ?

 Để sửa đổi màu sắc của biểu đồ, bạn có thể sử dụng`IChartSeriesFormat` Và`IShapeFillFormat` giao diện để thiết lập thuộc tính điền và dòng.

### Tôi có thể thêm nhãn vào điểm dữ liệu không?

 Có, bạn có thể thêm nhãn vào điểm dữ liệu bằng cách sử dụng`IDataPoint.getLabel()` phương pháp và tùy chỉnh chúng khi cần thiết.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
