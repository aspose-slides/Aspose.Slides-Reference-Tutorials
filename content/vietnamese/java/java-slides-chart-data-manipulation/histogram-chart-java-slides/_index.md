---
title: Biểu đồ biểu đồ trong Java Slides
linktitle: Biểu đồ biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Biểu đồ biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu.
type: docs
weight: 19
url: /vi/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Giới thiệu về Biểu đồ biểu đồ trong Java Slides bằng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ biểu đồ trong bản trình bày PowerPoint bằng API Aspose.Slides cho Java. Biểu đồ biểu đồ được sử dụng để thể hiện sự phân bổ dữ liệu trong một khoảng thời gian liên tục.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho Java. Bạn có thể tải nó xuống từ[trang web giả định](https://releases.aspose.com/slides/java/).

## Bước 1: Khởi tạo dự án của bạn

Tạo một dự án Java và đưa thư viện Aspose.Slides vào phần phụ thuộc của dự án của bạn.

## Bước 2: Nhập các thư viện cần thiết

```java
import com.aspose.slides.*;
```

## Bước 3: Tải bản trình bày hiện có

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế tới tài liệu PowerPoint của bạn.

## Bước 4: Tạo biểu đồ biểu đồ

Bây giờ, hãy tạo Biểu đồ biểu đồ trên một slide trong bản trình bày.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Thêm điểm dữ liệu vào chuỗi
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Đặt loại tổng hợp trục ngang thành Tự động
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Lưu bài thuyết trình
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Trong mã này, trước tiên chúng tôi xóa mọi danh mục và chuỗi hiện có khỏi biểu đồ. Sau đó, chúng tôi thêm các điểm dữ liệu vào chuỗi bằng cách sử dụng`getDataPoints().addDataPointForHistogramSeries` phương pháp. Cuối cùng, chúng tôi đặt loại tổng hợp trục ngang thành Tự động và lưu bản trình bày.

## Mã nguồn hoàn chỉnh cho biểu đồ biểu đồ trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách tạo Biểu đồ biểu đồ trong bản trình bày PowerPoint bằng API Aspose.Slides cho Java. Biểu đồ biểu đồ là công cụ có giá trị để trực quan hóa việc phân phối dữ liệu trong một khoảng thời gian liên tục và chúng có thể là sự bổ sung mạnh mẽ cho bản trình bày của bạn, đặc biệt là khi xử lý nội dung thống kê hoặc phân tích.

## Câu hỏi thường gặp

### Làm cách nào để cài đặt Aspose.Slides cho Java?

 Bạn có thể tải xuống thư viện Aspose.Slides cho Java từ[đây](https://releases.aspose.com/slides/java/). Thực hiện theo các hướng dẫn cài đặt được cung cấp trên trang web của họ.

### Biểu đồ Histogram dùng để làm gì?

Biểu đồ biểu đồ được sử dụng để trực quan hóa việc phân phối dữ liệu trong một khoảng thời gian liên tục. Nó thường được sử dụng trong thống kê để thể hiện sự phân bố tần số.

### Tôi có thể tùy chỉnh giao diện của Biểu đồ biểu đồ không?

Có, bạn có thể tùy chỉnh giao diện của biểu đồ, bao gồm màu sắc, nhãn và trục bằng cách sử dụng API Aspose.Slides.