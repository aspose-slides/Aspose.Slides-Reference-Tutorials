---
"description": "Tìm hiểu cách thiết lập màu tô đảo ngược cho biểu đồ Java Slides bằng Aspose.Slides. Nâng cao khả năng trực quan hóa biểu đồ của bạn bằng hướng dẫn từng bước và mã nguồn này."
"linktitle": "Đặt Biểu đồ màu tô đảo ngược trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Đặt Biểu đồ màu tô đảo ngược trong Java Slides"
"url": "/vi/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Biểu đồ màu tô đảo ngược trong Java Slides


## Giới thiệu về Set Invert Fill Color Chart trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thiết lập màu tô đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides for Java. Màu tô đảo ngược là một tính năng hữu ích khi bạn muốn làm nổi bật các giá trị âm trong biểu đồ bằng một màu cụ thể. Chúng tôi sẽ cung cấp hướng dẫn từng bước và mã nguồn để thực hiện việc này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Đã cài đặt thư viện Aspose.Slides cho Java.
2. Thiết lập môi trường phát triển Java.

## Bước 1: Tạo bài thuyết trình

Đầu tiên, chúng ta cần tạo một bài thuyết trình để thêm biểu đồ vào. Bạn có thể sử dụng mã sau để tạo bài thuyết trình:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Tiếp theo, chúng ta sẽ thêm biểu đồ cột nhóm vào bài thuyết trình. Sau đây là cách bạn có thể thực hiện:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Bước 3: Thiết lập dữ liệu biểu đồ

Bây giờ, chúng ta hãy thiết lập dữ liệu biểu đồ, bao gồm chuỗi và danh mục:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm loạt bài và danh mục mới
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Bước 4: Điền dữ liệu chuỗi

Bây giờ, chúng ta hãy điền dữ liệu chuỗi vào biểu đồ:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Bước 5: Đặt Đảo ngược màu tô

Để thiết lập màu đảo ngược cho chuỗi biểu đồ, bạn có thể sử dụng mã sau:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Trong đoạn mã trên, chúng ta thiết lập chuỗi để đảo ngược màu tô cho các giá trị âm và chỉ định màu cho phần tô đảo ngược.

## Bước 6: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày có biểu đồ:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho biểu đồ màu tô đảo ngược trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Thêm loạt bài và danh mục mới
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Lấy chuỗi biểu đồ đầu tiên và điền dữ liệu chuỗi.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã chỉ cho bạn cách thiết lập màu tô đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides for Java. Tính năng này cho phép bạn làm nổi bật các giá trị âm trong biểu đồ của mình bằng một màu cụ thể, giúp dữ liệu của bạn có nhiều thông tin trực quan hơn.

## Câu hỏi thường gặp

Trong phần này, chúng tôi sẽ giải quyết một số câu hỏi thường gặp liên quan đến việc thiết lập màu đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides cho Java.

### Làm thế nào để cài đặt Aspose.Slides cho Java?

Bạn có thể cài đặt Aspose.Slides cho Java bằng cách bao gồm các tệp JAR Aspose.Slides trong dự án Java của bạn. Bạn có thể tải xuống thư viện từ [Trang tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/). Thực hiện theo hướng dẫn cài đặt được cung cấp trong tài liệu dành cho môi trường phát triển cụ thể của bạn.

### Tôi có thể tùy chỉnh màu cho phần tô ngược trong chuỗi biểu đồ không?

Có, bạn có thể tùy chỉnh màu cho phần tô ngược trong chuỗi biểu đồ. Trong ví dụ mã được cung cấp, `series.getInvertedSolidFillColor().setColor(Color.RED)` dòng đặt màu thành màu đỏ cho phần tô ngược. Bạn có thể thay thế `Color.RED` với bất kỳ màu nào khác mà bạn lựa chọn.

### Làm thế nào tôi có thể sửa đổi loại biểu đồ trong Aspose.Slides cho Java?

Bạn có thể sửa đổi loại biểu đồ bằng cách thay đổi `ChartType` tham số khi thêm biểu đồ vào bản trình bày. Trong ví dụ mã, chúng tôi đã sử dụng `ChartType.ClusteredColumn`. Bạn có thể khám phá các loại biểu đồ khác như biểu đồ đường, biểu đồ thanh, biểu đồ hình tròn, v.v., bằng cách chỉ định biểu đồ thích hợp `ChartType` giá trị enum.

### Làm thế nào để thêm nhiều chuỗi dữ liệu vào biểu đồ?

Để thêm nhiều chuỗi dữ liệu vào biểu đồ, bạn có thể sử dụng `chart.getChartData().getSeries().add(...)` phương pháp cho mỗi chuỗi bạn muốn thêm. Đảm bảo cung cấp các điểm dữ liệu và nhãn thích hợp cho mỗi chuỗi để điền vào biểu đồ của bạn với nhiều chuỗi.

### Có cách nào để tùy chỉnh các khía cạnh khác của giao diện biểu đồ không?

Có, bạn có thể tùy chỉnh nhiều khía cạnh khác nhau của giao diện biểu đồ, bao gồm nhãn trục, tiêu đề, chú giải và nhiều hơn nữa bằng Aspose.Slides for Java. Tham khảo tài liệu để biết hướng dẫn chi tiết về cách tùy chỉnh các thành phần và giao diện biểu đồ.

### Tôi có thể lưu biểu đồ ở nhiều định dạng khác nhau không?

Có, bạn có thể lưu biểu đồ ở nhiều định dạng khác nhau bằng Aspose.Slides for Java. Trong ví dụ mã được cung cấp, chúng tôi đã lưu bản trình bày dưới dạng tệp PPTX. Bạn có thể sử dụng các định dạng khác nhau `SaveFormat` tùy chọn lưu ở các định dạng khác như PDF, PNG hoặc SVG, tùy theo yêu cầu của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}