---
title: Biểu đồ thông thường trong Java Slides
linktitle: Biểu đồ thông thường trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tạo biểu đồ thông thường trong Java Slides với Aspose.Slides cho Java. Hướng dẫn từng bước và mã nguồn để tạo, tùy chỉnh và lưu biểu đồ trong bản trình bày PowerPoint.
weight: 21
url: /vi/java/chart-data-manipulation/normal-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Biểu đồ thông thường trong Java Slides

Trong hướng dẫn này, chúng ta sẽ hướng dẫn quy trình tạo biểu đồ thông thường trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Chúng tôi sẽ sử dụng hướng dẫn từng bước cùng với mã nguồn để trình bày cách tạo biểu đồ cột được nhóm trong bản trình bày PowerPoint.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Aspose.Slides cho API Java đã được cài đặt.
2. Một môi trường phát triển Java được thiết lập.
3. Kiến thức cơ bản về lập trình Java.

## Bước 1: Thiết lập dự án

Đảm bảo bạn có một thư mục cho dự án của bạn. Hãy gọi nó là "Thư mục tài liệu của bạn" như được đề cập trong mã. Bạn có thể thay thế đường dẫn này bằng đường dẫn thực tế tới thư mục dự án của bạn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Bước 2: Tạo bản trình bày

Bây giờ, hãy tạo bản trình bày PowerPoint và truy cập vào slide đầu tiên của nó.

```java
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation pres = new Presentation();
// Truy cập slide đầu tiên
ISlide sld = pres.getSlides().get_Item(0);
```

## Bước 3: Thêm biểu đồ

Chúng tôi sẽ thêm biểu đồ cột được nhóm vào trang chiếu và đặt tiêu đề cho nó.

```java
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Đặt tiêu đề biểu đồ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Bước 4: Thiết lập dữ liệu biểu đồ

Tiếp theo, chúng ta sẽ thiết lập dữ liệu biểu đồ bằng cách xác định chuỗi và danh mục.

```java
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;

// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Xóa chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Bước 5: Điền dữ liệu chuỗi

Bây giờ, hãy điền các điểm dữ liệu chuỗi cho biểu đồ.

```java
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Đặt màu tô cho chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);

// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Đặt màu tô cho chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Bước 6: Tùy chỉnh nhãn

Hãy tùy chỉnh nhãn dữ liệu cho chuỗi biểu đồ.

```java
// Nhãn đầu tiên sẽ hiển thị Tên danh mục
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Hiển thị giá trị cho nhãn thứ ba với tên chuỗi và dấu phân cách
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Bước 7: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày có biểu đồ vào thư mục dự án của bạn.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo thành công biểu đồ cột được nhóm trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh thêm biểu đồ này theo yêu cầu của bạn.

## Mã nguồn hoàn chỉnh cho các biểu đồ thông thường trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation pres = new Presentation();
// Truy cập slide đầu tiên
ISlide sld = pres.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Đặt tiêu đề biểu đồ
// Chart.getChartTitle().getTextFrameForOverriding().setText("Tiêu đề mẫu");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Thêm loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Đặt màu tô cho chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Đặt màu tô cho chuỗi
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Nhãn đầu tiên sẽ hiển thị Tên danh mục
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Hiển thị giá trị cho nhãn thứ ba
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Lưu bài thuyết trình bằng biểu đồ
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo biểu đồ thông thường trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Chúng tôi đã xem hướng dẫn từng bước với mã nguồn để tạo biểu đồ cột được nhóm trong bản trình bày PowerPoint.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại biểu đồ?

 Để thay đổi loại biểu đồ, hãy sửa đổi`ChartType`tham số khi thêm biểu đồ bằng cách sử dụng`sld.getShapes().addChart()`. Bạn có thể chọn từ nhiều loại biểu đồ khác nhau có sẵn trong Aspose.Slides.

### Tôi có thể thay đổi màu sắc của chuỗi biểu đồ không?

 Có, bạn có thể thay đổi màu của chuỗi biểu đồ bằng cách đặt màu tô cho từng chuỗi bằng cách sử dụng`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Làm cách nào để thêm nhiều danh mục hoặc chuỗi vào biểu đồ?

 Bạn có thể thêm nhiều danh mục hoặc chuỗi khác vào biểu đồ bằng cách thêm các điểm dữ liệu và nhãn mới bằng cách sử dụng`chart.getChartData().getCategories().add()` Và`chart.getChartData().getSeries().add()` phương pháp.

### Làm cách nào tôi có thể tùy chỉnh thêm tiêu đề biểu đồ?

 Bạn có thể tùy chỉnh thêm tiêu đề biểu đồ bằng cách sửa đổi các thuộc tính của`chart.getChartTitle()` chẳng hạn như căn chỉnh văn bản, cỡ chữ và màu sắc.

### Làm cách nào để lưu biểu đồ sang định dạng tệp khác?

 Để lưu biểu đồ sang một định dạng tệp khác, hãy thay đổi`SaveFormat` tham số trong`pres.save()` sang định dạng mong muốn (ví dụ: PDF, PNG, JPEG).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
