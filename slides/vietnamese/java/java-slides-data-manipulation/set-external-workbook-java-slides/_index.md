---
"description": "Tìm hiểu cách thiết lập sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides for Java. Tạo các bài thuyết trình động với tích hợp dữ liệu Excel."
"linktitle": "Thiết lập Workbook ngoài trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thiết lập Workbook ngoài trong Java Slides"
"url": "/vi/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập Workbook ngoài trong Java Slides


## Giới thiệu về Set External Workbook trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách thiết lập một sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides. Bạn sẽ học cách tạo bản trình bày PowerPoint với biểu đồ tham chiếu dữ liệu từ sổ làm việc Excel bên ngoài. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ cách tích hợp dữ liệu bên ngoài vào bản trình bày Java Slides của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu triển khai, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides cho Java đã được thêm vào dự án của bạn.
- Một bảng tính Excel có chứa dữ liệu bạn muốn tham chiếu trong bài thuyết trình của mình.

## Bước 1: Tạo một bài thuyết trình mới

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Chúng ta bắt đầu bằng cách tạo một bản trình bày PowerPoint mới bằng Aspose.Slides.

## Bước 2: Thêm biểu đồ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Tiếp theo, chúng ta chèn biểu đồ hình tròn vào bài thuyết trình. Bạn có thể tùy chỉnh loại biểu đồ và vị trí khi cần.

## Bước 3: Truy cập Workbook bên ngoài

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Để truy cập vào sổ làm việc bên ngoài, chúng ta sử dụng `setExternalWorkbook` phương pháp và cung cấp đường dẫn đến bảng tính Excel chứa dữ liệu.

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

Cuối cùng, chúng ta lưu bản trình bày có tham chiếu đến bảng tính bên ngoài dưới dạng tệp PowerPoint.

## Mã nguồn đầy đủ cho Set External Workbook trong Java Slides

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

Trong hướng dẫn này, chúng ta đã học cách thiết lập một sổ làm việc bên ngoài trong Java Slides bằng Aspose.Slides. Bây giờ bạn có thể tạo các bài thuyết trình tham chiếu dữ liệu động từ sổ làm việc Excel, tăng cường tính linh hoạt và tính tương tác của các slide của bạn.

## Câu hỏi thường gặp

### Làm thế nào để cài đặt Aspose.Slides cho Java?

Có thể cài đặt Aspose.Slides for Java bằng cách thêm thư viện vào dự án Java của bạn. Bạn có thể tải xuống thư viện từ trang web Aspose và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

### Tôi có thể sử dụng các loại biểu đồ khác nhau với sổ làm việc bên ngoài không?

Có, bạn có thể sử dụng nhiều loại biểu đồ được Aspose.Slides hỗ trợ và liên kết chúng với dữ liệu từ sổ làm việc bên ngoài. Quy trình có thể thay đổi đôi chút tùy thuộc vào loại biểu đồ bạn chọn.

### Nếu cấu trúc dữ liệu của sổ làm việc ngoài của tôi thay đổi thì sao?

Nếu cấu trúc dữ liệu của sổ làm việc ngoài thay đổi, bạn có thể cần cập nhật tham chiếu ô trong mã Java để đảm bảo dữ liệu biểu đồ vẫn chính xác.

### Aspose.Slides có tương thích với phiên bản Java mới nhất không?

Aspose.Slides for Java được cập nhật thường xuyên để đảm bảo khả năng tương thích với các phiên bản Java mới nhất. Hãy chắc chắn kiểm tra các bản cập nhật và sử dụng phiên bản mới nhất của thư viện để có hiệu suất và khả năng tương thích tối ưu.

### Tôi có thể thêm nhiều biểu đồ tham chiếu đến cùng một bảng tính ngoài không?

Có, bạn có thể thêm nhiều biểu đồ vào bài thuyết trình của mình, tất cả đều tham chiếu đến cùng một sổ làm việc bên ngoài. Chỉ cần lặp lại các bước được nêu trong hướng dẫn này cho mỗi biểu đồ bạn muốn tạo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}