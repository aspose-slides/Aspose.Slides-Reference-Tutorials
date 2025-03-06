---
title: Đặt biểu đồ màu tô đảo ngược trong trang trình bày Java
linktitle: Đặt biểu đồ màu tô đảo ngược trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt đảo ngược màu tô cho biểu đồ Java Slides bằng Aspose.Slides. Nâng cao khả năng trực quan hóa biểu đồ của bạn bằng mã nguồn và hướng dẫn từng bước này.
weight: 22
url: /vi/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt biểu đồ màu tô đảo ngược trong trang trình bày Java


## Giới thiệu về Đặt biểu đồ màu tô đảo ngược trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách đặt màu tô đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides cho Java. Đảo ngược màu tô là một tính năng hữu ích khi bạn muốn làm nổi bật các giá trị âm trong biểu đồ bằng một màu cụ thể. Chúng tôi sẽ cung cấp hướng dẫn từng bước và mã nguồn để đạt được điều này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Đã cài đặt thư viện Aspose.Slides cho Java.
2. Môi trường phát triển Java được thiết lập.

## Bước 1: Tạo bản trình bày

Đầu tiên, chúng ta cần tạo một bản trình bày để thêm biểu đồ của mình vào. Bạn có thể sử dụng đoạn mã sau để tạo bản trình bày:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Tiếp theo, chúng ta sẽ thêm biểu đồ cột nhóm vào bản trình bày. Đây là cách bạn có thể làm điều đó:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Bước 3: Thiết lập dữ liệu biểu đồ

Bây giờ, hãy thiết lập dữ liệu biểu đồ, bao gồm chuỗi và danh mục:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm loạt và danh mục mới
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Bước 4: Điền dữ liệu chuỗi

Bây giờ, hãy điền dữ liệu chuỗi cho biểu đồ:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Bước 5: Đặt màu tô đảo ngược

Để đặt màu tô đảo ngược cho chuỗi biểu đồ, bạn có thể sử dụng mã sau:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Trong đoạn mã trên, chúng ta đặt chuỗi đảo ngược màu tô cho các giá trị âm và chỉ định màu cho phần tô đảo ngược.

## Bước 6: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình với biểu đồ:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để đặt biểu đồ màu tô đảo ngược trong các trang trình bày Java

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
// Thêm loạt và danh mục mới
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

Trong hướng dẫn này, chúng tôi đã chỉ cho bạn cách đặt màu tô đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides for Java. Tính năng này cho phép bạn làm nổi bật các giá trị âm trong biểu đồ bằng một màu cụ thể, làm cho dữ liệu của bạn có nhiều thông tin trực quan hơn.

## Câu hỏi thường gặp

Trong phần này, chúng tôi sẽ giải quyết một số câu hỏi phổ biến liên quan đến việc đặt màu tô đảo ngược cho biểu đồ trong Java Slides bằng Aspose.Slides for Java.

### Làm cách nào để cài đặt Aspose.Slides cho Java?

 Bạn có thể cài đặt Aspose.Slides cho Java bằng cách đưa các tệp JAR Aspose.Slides vào dự án Java của bạn. Bạn có thể tải xuống thư viện từ[Trang tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/). Làm theo hướng dẫn cài đặt được cung cấp trong tài liệu dành cho môi trường phát triển cụ thể của bạn.

### Tôi có thể tùy chỉnh màu cho phần điền ngược trong chuỗi biểu đồ không?

Có, bạn có thể tùy chỉnh màu cho phần tô ngược trong chuỗi biểu đồ. Trong ví dụ mã được cung cấp,`series.getInvertedSolidFillColor().setColor(Color.RED)` dòng đặt màu thành màu đỏ cho phần tô ngược. Bạn có thể thay thế`Color.RED` với bất kỳ màu nào khác mà bạn chọn.

### Làm cách nào tôi có thể sửa đổi loại biểu đồ trong Aspose.Slides cho Java?

 Bạn có thể sửa đổi loại biểu đồ bằng cách thay đổi`ChartType` tham số khi thêm biểu đồ vào bản trình bày. Trong ví dụ về mã, chúng tôi đã sử dụng`ChartType.ClusteredColumn` . Bạn có thể khám phá các loại biểu đồ khác như biểu đồ đường, biểu đồ thanh, biểu đồ hình tròn, v.v. bằng cách chỉ định các loại biểu đồ thích hợp.`ChartType` giá trị enum.

### Làm cách nào để thêm nhiều chuỗi dữ liệu vào biểu đồ?

 Để thêm nhiều chuỗi dữ liệu vào biểu đồ, bạn có thể sử dụng`chart.getChartData().getSeries().add(...)` phương pháp cho mỗi chuỗi bạn muốn thêm. Đảm bảo cung cấp các điểm dữ liệu và nhãn thích hợp cho từng chuỗi để điền vào biểu đồ của bạn nhiều chuỗi.

### Có cách nào để tùy chỉnh các khía cạnh khác của giao diện biểu đồ không?

Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của giao diện biểu đồ, bao gồm nhãn trục, tiêu đề, chú giải, v.v. bằng cách sử dụng Aspose.Slides cho Java. Tham khảo tài liệu để biết hướng dẫn chi tiết về cách tùy chỉnh các thành phần và hình thức biểu đồ.

### Tôi có thể lưu biểu đồ ở các định dạng khác nhau không?

 Có, bạn có thể lưu biểu đồ ở các định dạng khác nhau bằng Aspose.Slides cho Java. Trong ví dụ về mã được cung cấp, chúng tôi đã lưu bản trình bày dưới dạng tệp PPTX. Bạn có thể sử dụng khác nhau`SaveFormat` các tùy chọn để lưu nó ở các định dạng khác như PDF, PNG hoặc SVG, tùy thuộc vào yêu cầu của bạn.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
