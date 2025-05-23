---
"description": "Tìm hiểu cách đặt nhãn dữ liệu có dấu phần trăm trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Tạo biểu đồ hấp dẫn với hướng dẫn từng bước và mã nguồn."
"linktitle": "Đặt nhãn dữ liệu Phần trăm Đăng nhập Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Đặt nhãn dữ liệu Phần trăm Đăng nhập Java Slides"
"url": "/vi/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Đặt nhãn dữ liệu Phần trăm Đăng nhập Java Slides


## Giới thiệu về Đặt nhãn dữ liệu Phần trăm Đăng nhập Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập nhãn dữ liệu có dấu phần trăm bằng Aspose.Slides for Java. Chúng tôi sẽ tạo bản trình bày PowerPoint có biểu đồ cột xếp chồng và cấu hình nhãn dữ liệu để hiển thị phần trăm.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thêm thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo một bài thuyết trình mới

Đầu tiên, chúng ta tạo một bản trình bày PowerPoint mới bằng Aspose.Slides.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
```

## Bước 2: Thêm Slide và Biểu đồ

Tiếp theo, chúng ta thêm một slide và biểu đồ cột xếp chồng vào bài thuyết trình.

```java
// Lấy tham chiếu của slide
ISlide slide = presentation.getSlides().get_Item(0);

// Thêm biểu đồ PercentsStackedColumn vào trang chiếu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Bước 3: Cấu hình Định dạng Số Trục

Để hiển thị phần trăm, chúng ta cần cấu hình định dạng số cho trục dọc của biểu đồ.

```java
// Đặt NumberFormatLinkedToSource thành false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Bước 4: Thêm dữ liệu biểu đồ

Chúng tôi thêm dữ liệu vào biểu đồ bằng cách tạo chuỗi và điểm dữ liệu. Trong ví dụ này, chúng tôi thêm hai chuỗi với các điểm dữ liệu tương ứng của chúng.

```java
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Thêm series mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Thêm series mới
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Bước 5: Tùy chỉnh nhãn dữ liệu

Bây giờ, chúng ta hãy tùy chỉnh giao diện của nhãn dữ liệu.

```java
// Thiết lập thuộc tính LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Bước 6: Lưu bài thuyết trình

Cuối cùng, chúng ta lưu bài thuyết trình vào tệp PowerPoint.

```java
// Ghi bản trình bày vào đĩa
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công bản trình bày PowerPoint có biểu đồ cột xếp chồng và định cấu hình nhãn dữ liệu để hiển thị phần trăm bằng Aspose.Slides for Java.

## Mã nguồn hoàn chỉnh cho nhãn dữ liệu tập hợp phần trăm đăng nhập Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
// Lấy tham chiếu của slide
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ PercentsStackedColumn vào trang chiếu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Đặt NumberFormatLinkedToSource thành false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Thêm series mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Thiết lập màu tô của chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Thiết lập thuộc tính LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Thêm series mới
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Thiết lập kiểu và màu tô
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Ghi bản trình bày vào đĩa
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo các bài thuyết trình hấp dẫn với nhãn dữ liệu dựa trên phần trăm, có thể đặc biệt hữu ích để truyền tải thông tin hiệu quả trong các báo cáo kinh doanh, tài liệu giáo dục, v.v.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi màu sắc của biểu đồ?

Bạn có thể thay đổi màu tô của chuỗi biểu đồ bằng cách sử dụng `setFill` phương pháp như thể hiện trong ví dụ.

### Tôi có thể tùy chỉnh kích thước phông chữ của nhãn dữ liệu không?

Có, bạn có thể tùy chỉnh kích thước phông chữ của nhãn dữ liệu bằng cách thiết lập `setFontHeight` tài sản như được thể hiện trong mã.

### Làm thế nào tôi có thể thêm nhiều chuỗi vào biểu đồ?

Bạn có thể thêm các chuỗi bổ sung vào biểu đồ bằng cách sử dụng `add` phương pháp trên `IChartSeriesCollection` sự vật.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}