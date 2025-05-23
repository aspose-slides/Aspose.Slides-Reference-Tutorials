---
"description": "Tìm hiểu cách tạo Biểu đồ Histogram trong bài thuyết trình PowerPoint bằng Aspose.Slides for Java. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu."
"linktitle": "Biểu đồ Histogram trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ Histogram trong Java Slides"
"url": "/vi/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ Histogram trong Java Slides


## Giới thiệu về Biểu đồ Histogram trong Java Slides sử dụng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ Histogram trong bản trình bày PowerPoint bằng API Aspose.Slides for Java. Biểu đồ Histogram được sử dụng để biểu diễn sự phân bố dữ liệu trong một khoảng thời gian liên tục.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides for Java. Bạn có thể tải xuống từ [Trang web Aspose](https://releases.aspose.com/slides/java/).

## Bước 1: Khởi tạo dự án của bạn

Tạo một dự án Java và đưa thư viện Aspose.Slides vào phần phụ thuộc của dự án.

## Bước 2: Nhập các thư viện cần thiết

```java
import com.aspose.slides.*;
```

## Bước 3: Tải một bài thuyết trình hiện có

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Hãy chắc chắn thay thế `"Your Document Directory"` với đường dẫn thực tế đến tài liệu PowerPoint của bạn.

## Bước 4: Tạo biểu đồ Histogram

Bây giờ, chúng ta hãy tạo Biểu đồ Histogram trên một slide trong bài thuyết trình.

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

Trong mã này, trước tiên chúng ta xóa mọi danh mục và chuỗi hiện có khỏi biểu đồ. Sau đó, chúng ta thêm các điểm dữ liệu vào chuỗi bằng cách sử dụng `getDataPoints().addDataPointForHistogramSeries` phương pháp. Cuối cùng, chúng ta đặt loại tổng hợp trục ngang thành Tự động và lưu bản trình bày.

## Mã nguồn đầy đủ cho biểu đồ Histogram trong Java Slides

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

Trong hướng dẫn này, chúng tôi đã khám phá cách tạo Biểu đồ Histogram trong bản trình bày PowerPoint bằng API Aspose.Slides for Java. Biểu đồ Histogram là công cụ hữu ích để trực quan hóa sự phân bổ dữ liệu trong một khoảng thời gian liên tục và chúng có thể là một bổ sung mạnh mẽ cho bản trình bày của bạn, đặc biệt là khi xử lý nội dung thống kê hoặc phân tích.

## Câu hỏi thường gặp

### Làm thế nào để cài đặt Aspose.Slides cho Java?

Bạn có thể tải xuống thư viện Aspose.Slides cho Java từ [đây](https://releases.aspose.com/slides/java/). Thực hiện theo hướng dẫn cài đặt được cung cấp trên trang web của họ.

### Biểu đồ Histogram được sử dụng để làm gì?

Biểu đồ Histogram được sử dụng để trực quan hóa sự phân bố dữ liệu trong một khoảng thời gian liên tục. Biểu đồ này thường được sử dụng trong thống kê để biểu diễn sự phân bố tần suất.

### Tôi có thể tùy chỉnh giao diện của Biểu đồ Histogram không?

Có, bạn có thể tùy chỉnh giao diện của biểu đồ, bao gồm màu sắc, nhãn và trục, bằng cách sử dụng API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}