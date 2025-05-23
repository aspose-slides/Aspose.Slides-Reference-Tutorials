---
"description": "Tìm hiểu cách tạo Java Slides với các điểm đánh dấu mặc định trong biểu đồ bằng Aspose.Slides for Java. Hướng dẫn từng bước có mã nguồn."
"linktitle": "Các điểm đánh dấu mặc định trong biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Các điểm đánh dấu mặc định trong biểu đồ trong Java Slides"
"url": "/vi/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Các điểm đánh dấu mặc định trong biểu đồ trong Java Slides


## Giới thiệu về các điểm đánh dấu mặc định trong biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo biểu đồ với các điểm đánh dấu mặc định bằng Aspose.Slides for Java. Các điểm đánh dấu mặc định là các ký hiệu hoặc hình dạng được thêm vào các điểm dữ liệu trong biểu đồ để làm nổi bật chúng. Chúng ta sẽ tạo biểu đồ đường với các điểm đánh dấu để trực quan hóa dữ liệu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình.

## Bước 1: Tạo bài thuyết trình

Trước tiên, hãy tạo một bài thuyết trình và thêm một slide vào đó. Sau đó, chúng ta sẽ thêm một biểu đồ vào slide.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Bước 2: Thêm biểu đồ đường có đánh dấu

Bây giờ, hãy thêm biểu đồ đường có đánh dấu vào slide. Chúng ta cũng sẽ xóa mọi dữ liệu mặc định khỏi biểu đồ.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Bước 3: Điền dữ liệu biểu đồ

Chúng tôi sẽ điền dữ liệu mẫu vào biểu đồ. Trong ví dụ này, chúng tôi sẽ tạo hai chuỗi với các điểm dữ liệu và danh mục.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Phần 1
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

// Phần 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Điền dữ liệu chuỗi
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Bước 4: Tùy chỉnh biểu đồ

Bạn có thể tùy chỉnh biểu đồ thêm nữa, chẳng hạn như thêm chú giải và điều chỉnh giao diện của biểu đồ.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày có biểu đồ vào vị trí bạn mong muốn.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo xong biểu đồ đường với các điểm đánh dấu mặc định bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ cho các điểm đánh dấu mặc định trong biểu đồ trong Java Slides

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
            //Lấy chuỗi biểu đồ thứ hai
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Đang điền dữ liệu chuỗi
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

Trong hướng dẫn toàn diện này, bạn đã học cách tạo Java Slides với các điểm đánh dấu mặc định trong biểu đồ bằng Aspose.Slides for Java. Chúng tôi đã đề cập đến toàn bộ quá trình, từ thiết lập bản trình bày đến tùy chỉnh giao diện của biểu đồ và lưu kết quả.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi ký hiệu đánh dấu?

Bạn có thể tùy chỉnh các ký hiệu đánh dấu bằng cách thiết lập kiểu đánh dấu cho từng điểm dữ liệu. Sử dụng `IDataPoint.setMarkerStyle()` để thay đổi ký hiệu đánh dấu.

### Làm thế nào để điều chỉnh màu sắc của biểu đồ?

Để sửa đổi màu sắc của biểu đồ, bạn có thể sử dụng `IChartSeriesFormat` Và `IShapeFillFormat` giao diện để thiết lập các thuộc tính tô và đường kẻ.

### Tôi có thể thêm nhãn vào điểm dữ liệu không?

Có, bạn có thể thêm nhãn vào các điểm dữ liệu bằng cách sử dụng `IDataPoint.getLabel()` phương pháp và tùy chỉnh chúng khi cần thiết.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}