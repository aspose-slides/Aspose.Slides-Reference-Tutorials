---
title: Biểu đồ rải rác trong Java Slides
linktitle: Biểu đồ rải rác trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Biểu đồ phân tán trong Java bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn Java để trực quan hóa dữ liệu trong bản trình bày.
type: docs
weight: 11
url: /vi/java/chart-creation/scattered-chart-java-slides/
---

## Giới thiệu về Biểu đồ phân tán trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ phân tán bằng Aspose.Slides cho Java. Biểu đồ phân tán rất hữu ích để hiển thị các điểm dữ liệu trên mặt phẳng hai chiều. Chúng tôi sẽ cung cấp hướng dẫn từng bước và bao gồm mã nguồn Java để thuận tiện cho bạn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. [Aspose.Slides cho Java](https://products.aspose.com/slides/java) Cài đặt.
2. Một môi trường phát triển Java được thiết lập.

## Bước 1: Khởi tạo bản trình bày

Đầu tiên, nhập các thư viện cần thiết và tạo bản trình bày mới.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Tạo bản trình bày mới
Presentation pres = new Presentation();
```

## Bước 2: Thêm trang trình bày và tạo biểu đồ phân tán

 Tiếp theo, thêm một slide và tạo biểu đồ phân tán trên đó. Chúng tôi sẽ sử dụng`ScatterWithSmoothLines` loại biểu đồ trong ví dụ này.

```java
// Nhận slide đầu tiên
ISlide slide = pres.getSlides().get_Item(0);

// Tạo biểu đồ phân tán
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Bước 3: Chuẩn bị dữ liệu biểu đồ

Bây giờ, hãy chuẩn bị dữ liệu cho biểu đồ phân tán của chúng ta. Chúng tôi sẽ thêm hai chuỗi, mỗi chuỗi có nhiều điểm dữ liệu.

```java
// Lấy chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;

// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Xóa loạt bản demo
chart.getChartData().getSeries().clear();

// Thêm loạt phim đầu tiên
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Thêm điểm dữ liệu vào chuỗi đầu tiên
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Chỉnh sửa loại chuỗi
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Thay đổi kích thước điểm đánh dấu
series.getMarker().setSymbol(MarkerStyleType.Star); // Thay đổi biểu tượng đánh dấu

// Lấy loạt biểu đồ thứ hai
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

Đó là nó! Bạn đã tạo thành công Biểu đồ phân tán bằng Aspose.Slides cho Java. Bây giờ bạn có thể tùy chỉnh thêm ví dụ này cho phù hợp với yêu cầu thiết kế và dữ liệu cụ thể của mình.

## Mã nguồn hoàn chỉnh cho biểu đồ phân tán trong các trang trình bày Java
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Tạo biểu đồ mặc định
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Lấy chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa loạt bản demo
chart.getChartData().getSeries().clear();
// Thêm loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Thêm điểm mới (1:3) vào đó.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Thêm điểm mới (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Chỉnh sửa loại chuỗi
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Thay đổi điểm đánh dấu chuỗi biểu đồ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Thêm điểm mới (5:2) vào đó.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Thêm điểm mới (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Thêm điểm mới (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Thêm điểm mới (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Thay đổi điểm đánh dấu chuỗi biểu đồ
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã hướng dẫn bạn quy trình tạo Biểu đồ phân tán bằng Aspose.Slides cho Java. Biểu đồ phân tán là công cụ mạnh mẽ để trực quan hóa các điểm dữ liệu trong không gian hai chiều, giúp phân tích và hiểu các mối quan hệ dữ liệu phức tạp dễ dàng hơn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại biểu đồ?

 Để thay đổi loại biểu đồ, hãy sử dụng`setType`phương pháp trên chuỗi biểu đồ và cung cấp loại biểu đồ mong muốn. Ví dụ,`series.setType(ChartType.Line)` sẽ thay đổi chuỗi thành biểu đồ đường.

### Làm cách nào để tùy chỉnh kích thước và kiểu điểm đánh dấu?

 Bạn có thể thay đổi kích thước và kiểu điểm đánh dấu bằng cách sử dụng`getMarker` phương pháp trên chuỗi và sau đó thiết lập các thuộc tính kích thước và ký hiệu. Ví dụ:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Vui lòng khám phá thêm các tùy chọn tùy chỉnh trong tài liệu Aspose.Slides for Java.

 Nhớ thay thế`"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.