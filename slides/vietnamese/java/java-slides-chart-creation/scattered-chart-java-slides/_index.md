---
"description": "Tìm hiểu cách tạo Biểu đồ phân tán trong Java bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn Java để trực quan hóa dữ liệu trong bài thuyết trình."
"linktitle": "Biểu đồ phân tán trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ phân tán trong Java Slides"
"url": "/vi/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ phân tán trong Java Slides


## Giới thiệu về Biểu đồ phân tán trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ phân tán bằng Aspose.Slides for Java. Biểu đồ phân tán hữu ích để trực quan hóa các điểm dữ liệu trên mặt phẳng hai chiều. Chúng tôi sẽ cung cấp hướng dẫn từng bước và bao gồm mã nguồn Java để bạn tiện theo dõi.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. [Aspose.Slides cho Java](https://products.aspose.com/slides/java) đã cài đặt.
2. Thiết lập môi trường phát triển Java.

## Bước 1: Khởi tạo bài thuyết trình

Đầu tiên, hãy nhập các thư viện cần thiết và tạo một bản trình bày mới.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Tạo một bài thuyết trình mới
Presentation pres = new Presentation();
```

## Bước 2: Thêm một Slide và Tạo Biểu đồ Phân tán

Tiếp theo, thêm một slide và tạo biểu đồ phân tán trên đó. Chúng ta sẽ sử dụng `ScatterWithSmoothLines` loại biểu đồ trong ví dụ này.

```java
// Nhận slide đầu tiên
ISlide slide = pres.getSlides().get_Item(0);

// Tạo biểu đồ phân tán
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Bước 3: Chuẩn bị dữ liệu biểu đồ

Bây giờ, hãy chuẩn bị dữ liệu cho biểu đồ phân tán của chúng ta. Chúng ta sẽ thêm hai chuỗi, mỗi chuỗi có nhiều điểm dữ liệu.

```java
// Nhận chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;

// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Xóa loạt bản demo
chart.getChartData().getSeries().clear();

// Thêm chuỗi đầu tiên
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Thêm điểm dữ liệu vào chuỗi đầu tiên
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Chỉnh sửa loại sê-ri
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Thay đổi kích thước điểm đánh dấu
series.getMarker().setSymbol(MarkerStyleType.Star); // Thay đổi biểu tượng đánh dấu

// Lấy chuỗi biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);

// Thêm điểm dữ liệu vào chuỗi thứ hai
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Thay đổi kiểu đánh dấu cho chuỗi thứ hai
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày có biểu đồ phân tán vào tệp PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công Biểu đồ phân tán bằng Aspose.Slides for Java. Bây giờ bạn có thể tùy chỉnh ví dụ này thêm nữa để phù hợp với dữ liệu cụ thể và yêu cầu thiết kế của bạn.

## Mã nguồn đầy đủ cho biểu đồ phân tán trong Java Slides
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Tạo biểu đồ mặc định
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Nhận chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa loạt bản demo
chart.getChartData().getSeries().clear();
// Thêm series mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Thêm điểm mới (1:3) vào đó.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Thêm điểm mới (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Chỉnh sửa loại sê-ri
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Thay đổi dấu hiệu chuỗi biểu đồ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Lấy chuỗi biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Thêm điểm mới (5:2) vào đó.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Thêm điểm mới (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Thêm điểm mới (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Thêm điểm mới (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Thay đổi dấu hiệu chuỗi biểu đồ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã hướng dẫn bạn quy trình tạo Biểu đồ phân tán bằng Aspose.Slides for Java. Biểu đồ phân tán là công cụ mạnh mẽ để trực quan hóa các điểm dữ liệu trong không gian hai chiều, giúp phân tích và hiểu các mối quan hệ dữ liệu phức tạp dễ dàng hơn.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi loại biểu đồ?

Để thay đổi loại biểu đồ, hãy sử dụng `setType` phương pháp trên chuỗi biểu đồ và cung cấp loại biểu đồ mong muốn. Ví dụ, `series.setType(ChartType.Line)` sẽ thay đổi chuỗi thành biểu đồ đường.

### Làm thế nào để tùy chỉnh kích thước và kiểu dáng của điểm đánh dấu?

Bạn có thể thay đổi kích thước và kiểu đánh dấu bằng cách sử dụng `getMarker` phương pháp trên chuỗi và sau đó thiết lập các thuộc tính kích thước và ký hiệu. Ví dụ:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Bạn có thể thoải mái khám phá thêm nhiều tùy chọn tùy chỉnh khác trong tài liệu Aspose.Slides for Java.

Nhớ thay thế `"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}