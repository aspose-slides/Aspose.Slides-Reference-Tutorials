---
"description": "Tìm hiểu cách tạo Biểu đồ hộp trong bài thuyết trình Java với Aspose.Slides. Hướng dẫn từng bước và mã nguồn kèm theo để trực quan hóa dữ liệu hiệu quả."
"linktitle": "Biểu đồ hộp trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ hộp trong Java Slides"
"url": "/vi/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ hộp trong Java Slides


## Giới thiệu về Biểu đồ hộp trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ hộp bằng Aspose.Slides for Java. Biểu đồ hộp hữu ích để trực quan hóa dữ liệu thống kê với nhiều tứ phân vị và giá trị ngoại lai. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn bắt đầu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Thư viện Aspose.Slides cho Java đã được cài đặt và cấu hình.
- Thiết lập môi trường phát triển Java.

## Bước 1: Khởi tạo bài thuyết trình

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Ở bước này, chúng ta khởi tạo một đối tượng trình bày bằng cách sử dụng đường dẫn đến tệp PowerPoint hiện có ("test.pptx" trong ví dụ này).

## Bước 2: Tạo biểu đồ hộp

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Trong bước này, chúng ta tạo một hình dạng Biểu đồ hộp trên trang chiếu đầu tiên của bài thuyết trình. Chúng ta cũng xóa mọi danh mục và chuỗi hiện có khỏi biểu đồ.

## Bước 3: Xác định danh mục

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

Trong bước này, chúng tôi xác định các danh mục cho Biểu đồ hộp. Chúng tôi sử dụng `IChartDataWorkbook` để thêm danh mục và dán nhãn cho phù hợp.

## Bước 4: Tạo Series

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Tại đây, chúng ta tạo một chuỗi BoxAndWhisker cho biểu đồ và cấu hình nhiều tùy chọn khác nhau như phương pháp tứ phân vị, đường trung bình, điểm đánh dấu trung bình, điểm bên trong và điểm ngoại lai.

## Bước 5: Thêm Điểm Dữ Liệu

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Trong bước này, chúng tôi thêm các điểm dữ liệu vào chuỗi BoxAndWhisker. Các điểm dữ liệu này biểu diễn dữ liệu thống kê cho biểu đồ.

## Bước 6: Lưu bài thuyết trình

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Cuối cùng, chúng ta lưu bản trình bày có Biểu đồ hộp vào một tệp PowerPoint mới có tên "BoxAndWhisker.pptx".

Xin chúc mừng! Bạn đã tạo thành công Biểu đồ hộp bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh biểu đồ thêm bằng cách điều chỉnh các thuộc tính khác nhau và thêm nhiều điểm dữ liệu hơn khi cần.

## Mã nguồn đầy đủ cho biểu đồ hộp trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo Biểu đồ hộp bằng Aspose.Slides for Java. Biểu đồ hộp là công cụ hữu ích để trực quan hóa dữ liệu thống kê, bao gồm tứ phân vị và giá trị ngoại lai. Chúng tôi cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn bắt đầu tạo Biểu đồ hộp trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi giao diện của Biểu đồ hộp?

Bạn có thể tùy chỉnh giao diện của Biểu đồ hộp bằng cách sửa đổi các thuộc tính như kiểu đường, màu sắc và phông chữ. Tham khảo tài liệu Aspose.Slides for Java để biết chi tiết về tùy chỉnh biểu đồ.

### Tôi có thể thêm chuỗi dữ liệu bổ sung vào Biểu đồ hộp không?

Có, bạn có thể thêm nhiều chuỗi dữ liệu vào Biểu đồ hộp bằng cách tạo thêm `IChartSeries` các đối tượng và thêm điểm dữ liệu vào chúng.

### QuartileMethodType.Exclusive có nghĩa là gì?

Các `QuartileMethodType.Exclusive` thiết lập chỉ định rằng các phép tính tứ phân vị phải được thực hiện bằng phương pháp loại trừ. Bạn có thể chọn các phương pháp tính tứ phân vị khác nhau tùy thuộc vào dữ liệu và yêu cầu của mình.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}