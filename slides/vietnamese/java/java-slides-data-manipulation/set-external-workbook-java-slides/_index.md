---
title: Đặt sổ làm việc bên ngoài trong Java Slides
linktitle: Đặt sổ làm việc bên ngoài trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides for Java. Tạo bản trình bày động với tích hợp dữ liệu Excel.
type: docs
weight: 19
url: /vi/java/data-manipulation/set-external-workbook-java-slides/
---

## Giới thiệu về Đặt sổ làm việc bên ngoài trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách thiết lập sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides. Bạn sẽ tìm hiểu cách tạo bản trình bày PowerPoint với biểu đồ tham chiếu dữ liệu từ sổ làm việc Excel bên ngoài. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ về cách tích hợp dữ liệu bên ngoài vào bản trình bày Java Slides của mình.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào triển khai, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides dành cho Java đã được thêm vào dự án của bạn.
- Sổ làm việc Excel có dữ liệu bạn muốn tham chiếu trong bản trình bày của mình.

## Bước 1: Tạo bản trình bày mới

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Chúng tôi bắt đầu bằng cách tạo bản trình bày PowerPoint mới bằng Aspose.Slides.

## Bước 2: Thêm biểu đồ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Tiếp theo, chúng ta chèn biểu đồ hình tròn vào bản trình bày. Bạn có thể tùy chỉnh loại biểu đồ và vị trí nếu cần.

## Bước 3: Truy cập Sổ làm việc bên ngoài

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Để truy cập sổ làm việc bên ngoài, chúng tôi sử dụng`setExternalWorkbook` phương thức và cung cấp đường dẫn đến sổ làm việc Excel chứa dữ liệu.

## Bước 4: Liên kết dữ liệu biểu đồ

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Chúng tôi liên kết biểu đồ với dữ liệu từ sổ làm việc bên ngoài bằng cách chỉ định tham chiếu ô cho chuỗi và danh mục.

## Bước 5: Lưu bài thuyết trình

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Cuối cùng, chúng tôi lưu bản trình bày có tham chiếu sổ làm việc bên ngoài dưới dạng tệp PowerPoint.

## Mã nguồn hoàn chỉnh để đặt sổ làm việc bên ngoài trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thiết lập sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides. Giờ đây, bạn có thể tạo bản trình bày tham chiếu động dữ liệu từ sổ làm việc Excel, nâng cao tính linh hoạt và tính tương tác của các trang chiếu của bạn.

## Câu hỏi thường gặp

### Làm cách nào để cài đặt Aspose.Slides cho Java?

Aspose.Slides cho Java có thể được cài đặt bằng cách thêm thư viện vào dự án Java của bạn. Bạn có thể tải xuống thư viện từ trang web Aspose và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

### Tôi có thể sử dụng các loại biểu đồ khác nhau với sổ làm việc bên ngoài không?

Có, bạn có thể sử dụng nhiều loại biểu đồ khác nhau được Aspose.Slides hỗ trợ và liên kết chúng với dữ liệu từ sổ làm việc bên ngoài. Quá trình này có thể thay đổi một chút tùy thuộc vào loại biểu đồ bạn chọn.

### Điều gì sẽ xảy ra nếu cấu trúc dữ liệu của sổ làm việc bên ngoài của tôi thay đổi?

Nếu cấu trúc dữ liệu của sổ làm việc bên ngoài của bạn thay đổi, bạn có thể cần phải cập nhật các tham chiếu ô trong mã Java của mình để đảm bảo rằng dữ liệu biểu đồ vẫn chính xác.

### Aspose.Slides có tương thích với các phiên bản Java mới nhất không?

Aspose.Slides cho Java được cập nhật thường xuyên để đảm bảo khả năng tương thích với các phiên bản Java mới nhất. Hãy nhớ kiểm tra các bản cập nhật và sử dụng phiên bản mới nhất của thư viện để có hiệu suất và khả năng tương thích tối ưu.

### Tôi có thể thêm nhiều biểu đồ tham chiếu cùng một sổ làm việc bên ngoài không?

Có, bạn có thể thêm nhiều biểu đồ vào bản trình bày của mình, tất cả đều tham chiếu đến cùng một sổ làm việc bên ngoài. Chỉ cần lặp lại các bước được nêu trong hướng dẫn này cho từng biểu đồ bạn muốn tạo.