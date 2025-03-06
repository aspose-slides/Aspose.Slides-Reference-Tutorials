---
title: Đặt Độ rộng Khoảng cách trong Trang trình bày Java
linktitle: Đặt Độ rộng Khoảng cách trong Trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt Độ rộng khoảng cách trong Java Slides với Aspose.Slides cho Java. Nâng cao hình ảnh biểu đồ cho bài thuyết trình PowerPoint của bạn.
weight: 21
url: /vi/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Độ rộng Khoảng cách trong Trang trình bày Java


## Giới thiệu về Đặt độ rộng khoảng cách trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập Độ rộng khoảng cách cho biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Độ rộng Khoảng cách xác định khoảng cách giữa các cột hoặc thanh trong biểu đồ, cho phép bạn kiểm soát hình thức trực quan của biểu đồ.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho Java. Bạn có thể tải xuống từ trang web Aspose[đây](https://releases.aspose.com/slides/java/).

## Hướng dẫn từng bước một

Thực hiện theo các bước sau để đặt Độ rộng khoảng cách trong biểu đồ bằng Aspose.Slides cho Java:

### 1. Tạo một bài thuyết trình trống

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tạo một bản trình bày trống
Presentation presentation = new Presentation();
```

### 2. Truy cập vào slide đầu tiên

```java
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Thêm biểu đồ với dữ liệu mặc định

```java
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Đặt chỉ mục bảng dữ liệu biểu đồ

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
```

### 5. Lấy sổ làm việc dữ liệu biểu đồ

```java
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Thêm chuỗi vào biểu đồ

```java
// Thêm chuỗi vào biểu đồ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Thêm danh mục vào biểu đồ

```java
// Thêm danh mục vào biểu đồ
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Điền dữ liệu chuỗi

```java
// Điền dữ liệu chuỗi
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Điền điểm dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Đặt độ rộng khoảng cách

```java
// Đặt giá trị Độ rộng khoảng cách
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Lưu bài thuyết trình

```java
// Lưu bài thuyết trình với biểu đồ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để đặt độ rộng khoảng cách trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bản trình bày trống
Presentation presentation = new Presentation();
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Thêm loạt bài
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Thêm danh mục
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Lấy loạt biểu đồ thứ hai
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Đặt giá trị GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Lưu bài thuyết trình bằng biểu đồ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt Độ rộng khoảng cách cho biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Điều chỉnh Độ rộng khoảng cách cho phép bạn kiểm soát khoảng cách giữa các cột hoặc thanh trong biểu đồ, nâng cao khả năng trình bày trực quan dữ liệu của bạn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi giá trị Độ rộng Khoảng cách?

 Để thay đổi Độ rộng Khoảng cách, hãy sử dụng`setGapWidth` phương pháp trên`ParentSeriesGroup`của chuỗi biểu đồ. Trong ví dụ được cung cấp, chúng tôi đặt Độ rộng khoảng cách thành 50, nhưng bạn có thể điều chỉnh giá trị này theo khoảng cách mong muốn của mình.

### Tôi có thể tùy chỉnh các thuộc tính biểu đồ khác không?

Có, Aspose.Slides for Java cung cấp các khả năng mở rộng để tùy chỉnh biểu đồ. Bạn có thể sửa đổi các thuộc tính biểu đồ khác nhau, chẳng hạn như màu sắc, nhãn, tiêu đề, v.v. Kiểm tra Tài liệu tham khảo API để biết thông tin chi tiết về các tùy chọn tùy chỉnh biểu đồ.

### Tôi có thể tìm thêm tài nguyên và tài liệu ở đâu?

 Bạn có thể tìm thấy tài liệu toàn diện và các tài nguyên bổ sung trên Aspose.Slides for Java trên[trang web giả định](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
