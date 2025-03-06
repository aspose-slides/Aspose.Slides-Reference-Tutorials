---
title: Biểu đồ hộp trong Java Slides
linktitle: Biểu đồ hộp trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Biểu đồ hộp trong bản trình bày Java bằng Aspose.Slides. Hướng dẫn từng bước và mã nguồn được bao gồm để hiển thị dữ liệu hiệu quả.
weight: 10
url: /vi/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ hộp trong Java Slides


## Giới thiệu về Biểu đồ hộp trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ hộp bằng Aspose.Slides cho Java. Biểu đồ hộp rất hữu ích để hiển thị dữ liệu thống kê với nhiều phần tư và các giá trị ngoại lệ khác nhau. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn bắt đầu.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Thư viện Aspose.Slides cho Java đã được cài đặt và định cấu hình.
- Một môi trường phát triển Java được thiết lập.

## Bước 1: Khởi tạo bản trình bày

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Trong bước này, chúng tôi khởi tạo một đối tượng bản trình bày bằng cách sử dụng đường dẫn đến tệp PowerPoint hiện có ("test.pptx" trong ví dụ này).

## Bước 2: Tạo biểu đồ hộp

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Trong bước này, chúng ta tạo hình Biểu đồ Hộp trên slide đầu tiên của bản trình bày. Chúng tôi cũng xóa mọi danh mục và chuỗi hiện có khỏi biểu đồ.

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

 Trong bước này, chúng tôi xác định các danh mục cho Biểu đồ hộp. Chúng tôi sử dụng`IChartDataWorkbook` để thêm danh mục và gắn nhãn cho chúng cho phù hợp.

## Bước 4: Tạo chuỗi

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Tại đây, chúng tôi tạo một chuỗi BoxAndWhisker cho biểu đồ và định cấu hình các tùy chọn khác nhau như phương pháp tứ phân vị, đường trung bình, điểm đánh dấu trung bình, điểm bên trong và điểm ngoại lệ.

## Bước 5: Thêm điểm dữ liệu

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Trong bước này, chúng tôi thêm điểm dữ liệu vào chuỗi BoxAndWhisker. Những điểm dữ liệu này đại diện cho dữ liệu thống kê cho biểu đồ.

## Bước 6: Lưu bài thuyết trình

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Cuối cùng, chúng ta lưu bản trình bày có Biểu đồ Hộp vào một tệp PowerPoint mới có tên "BoxAndWhisker.pptx."

Chúc mừng! Bạn đã tạo thành công Biểu đồ hộp bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh biểu đồ hơn nữa bằng cách điều chỉnh các thuộc tính khác nhau và thêm nhiều điểm dữ liệu hơn nếu cần.

## Mã nguồn hoàn chỉnh cho biểu đồ hộp trong Java Slides

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

Trong hướng dẫn này, chúng ta đã học cách tạo Biểu đồ hộp bằng Aspose.Slides cho Java. Biểu đồ hộp là công cụ có giá trị để trực quan hóa dữ liệu thống kê, bao gồm các phần tư và các giá trị ngoại lệ. Chúng tôi đã cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn bắt đầu tạo Biểu đồ hộp trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi giao diện của Biểu đồ Hộp?

Bạn có thể tùy chỉnh giao diện của Biểu đồ hộp bằng cách sửa đổi các thuộc tính như kiểu đường, màu sắc và phông chữ. Tham khảo tài liệu Aspose.Slides for Java để biết chi tiết về cách tùy chỉnh biểu đồ.

### Tôi có thể thêm chuỗi dữ liệu bổ sung vào Biểu đồ hộp không?

 Có, bạn có thể thêm nhiều chuỗi dữ liệu vào Biểu đồ hộp bằng cách tạo thêm`IChartSeries` các đối tượng và thêm các điểm dữ liệu vào chúng.

### QuartileMethodType.Exclusive có nghĩa là gì?

 Các`QuartileMethodType.Exclusive` cài đặt chỉ định rằng việc tính toán tứ phân vị phải được thực hiện bằng phương pháp độc quyền. Bạn có thể chọn các phương pháp tính toán tứ phân vị khác nhau tùy thuộc vào dữ liệu và yêu cầu của bạn.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
