---
title: Đặt tỷ lệ phần trăm nhãn dữ liệu Đăng nhập Java Slides
linktitle: Đặt tỷ lệ phần trăm nhãn dữ liệu Đăng nhập Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt nhãn dữ liệu bằng dấu phần trăm trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Tạo biểu đồ hấp dẫn với hướng dẫn từng bước và mã nguồn.
type: docs
weight: 17
url: /vi/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Giới thiệu về Đặt tỷ lệ phần trăm nhãn dữ liệu Đăng nhập trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đặt nhãn dữ liệu bằng ký hiệu phần trăm bằng Aspose.Slides cho Java. Chúng tôi sẽ tạo bản trình bày PowerPoint với biểu đồ cột xếp chồng và định cấu hình nhãn dữ liệu để hiển thị tỷ lệ phần trăm.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thêm thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày mới

Đầu tiên, chúng ta tạo một bản trình bày PowerPoint mới bằng Aspose.Slides.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
```

## Bước 2: Thêm trang trình bày và biểu đồ

Tiếp theo, chúng tôi thêm trang trình bày và biểu đồ cột xếp chồng vào bản trình bày.

```java
// Nhận tài liệu tham khảo của slide
ISlide slide = presentation.getSlides().get_Item(0);

// Thêm biểu đồ PercentsStackedColumn trên trang chiếu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Bước 3: Định cấu hình định dạng số trục

Để hiển thị tỷ lệ phần trăm, chúng ta cần cấu hình định dạng số cho trục tung của biểu đồ.

```java
//Đặt NumberFormatLinkedToSource thành sai
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Bước 4: Thêm dữ liệu biểu đồ

Chúng tôi thêm dữ liệu vào biểu đồ bằng cách tạo chuỗi và điểm dữ liệu. Trong ví dụ này, chúng tôi thêm hai chuỗi với các điểm dữ liệu tương ứng.

```java
//Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Thêm loạt phim mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Thêm loạt phim mới
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Bước 5: Tùy chỉnh nhãn dữ liệu

Bây giờ, hãy tùy chỉnh giao diện của nhãn dữ liệu.

```java
// Đặt thuộc tính LabelFormat
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

Cuối cùng, chúng ta lưu bài thuyết trình vào file PowerPoint.

```java
// Ghi bài thuyết trình vào đĩa
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo thành công bản trình bày PowerPoint với biểu đồ cột xếp chồng và nhãn dữ liệu được định cấu hình để hiển thị tỷ lệ phần trăm bằng Aspose.Slides for Java.

## Mã nguồn hoàn chỉnh để đặt tỷ lệ phần trăm nhãn dữ liệu Đăng nhập Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
// Nhận tài liệu tham khảo của slide
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ PercentsStackedColumn trên trang chiếu
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//Đặt NumberFormatLinkedToSource thành sai
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
//Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Thêm loạt phim mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Đặt màu tô của chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Đặt thuộc tính LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Thêm loạt phim mới
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Cài đặt kiểu và màu tô
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Ghi bài thuyết trình vào đĩa
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo các bản trình bày hấp dẫn với nhãn dữ liệu dựa trên tỷ lệ phần trăm, nhãn này có thể đặc biệt hữu ích để truyền tải thông tin một cách hiệu quả trong các báo cáo kinh doanh, tài liệu giáo dục, v.v.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu sắc của chuỗi biểu đồ?

 Bạn có thể thay đổi màu tô của chuỗi biểu đồ bằng cách sử dụng`setFill` phương pháp như trong ví dụ.

### Tôi có thể tùy chỉnh kích thước phông chữ của nhãn dữ liệu không?

 Có, bạn có thể tùy chỉnh kích thước phông chữ của nhãn dữ liệu bằng cách đặt`setFontHeight` thuộc tính như được thể hiện trong mã.

### Làm cách nào tôi có thể thêm nhiều chuỗi vào biểu đồ?

 Bạn có thể thêm chuỗi bổ sung vào biểu đồ bằng cách sử dụng`add` phương pháp trên`IChartSeriesCollection` sự vật.
