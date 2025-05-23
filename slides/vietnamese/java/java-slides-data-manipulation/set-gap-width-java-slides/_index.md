---
"description": "Tìm hiểu cách thiết lập Độ rộng khoảng cách trong Java Slides với Aspose.Slides for Java. Nâng cao hình ảnh biểu đồ cho bài thuyết trình PowerPoint của bạn."
"linktitle": "Thiết lập độ rộng khoảng cách trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thiết lập độ rộng khoảng cách trong Java Slides"
"url": "/vi/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập độ rộng khoảng cách trong Java Slides


## Giới thiệu về Thiết lập Độ rộng Khoảng cách trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập Độ rộng khoảng cách cho biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Độ rộng khoảng cách xác định khoảng cách giữa các cột hoặc thanh trong biểu đồ, cho phép bạn kiểm soát giao diện trực quan của biểu đồ.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides for Java. Bạn có thể tải xuống từ trang web Aspose [đây](https://releases.aspose.com/slides/java/).

## Hướng dẫn từng bước

Thực hiện theo các bước sau để thiết lập Độ rộng khoảng cách trong biểu đồ bằng Aspose.Slides cho Java:

### 1. Tạo một bài thuyết trình trống

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Tạo một bài thuyết trình trống 
Presentation presentation = new Presentation();
```

### 2. Truy cập vào Slide đầu tiên

```java
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Thêm biểu đồ với dữ liệu mặc định

```java
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Thiết lập mục lục của biểu đồ dữ liệu

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
```

### 5. Nhận Sổ làm việc dữ liệu biểu đồ

```java
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Thêm Chuỗi vào Biểu đồ

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

// Điền các điểm dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Thiết lập độ rộng khoảng cách

```java
// Đặt giá trị Độ rộng khoảng cách
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Lưu bài thuyết trình

```java
// Lưu bản trình bày có biểu đồ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho Set Gap Width trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bài thuyết trình trống 
Presentation presentation = new Presentation();
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Thêm loạt bài
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Thêm danh mục
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Lấy chuỗi biểu đồ thứ hai
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Đặt giá trị GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Lưu bài thuyết trình có biểu đồ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách thiết lập Độ rộng khoảng cách cho biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Điều chỉnh Độ rộng khoảng cách cho phép bạn kiểm soát khoảng cách giữa các cột hoặc thanh trong biểu đồ, nâng cao khả năng hiển thị trực quan dữ liệu của bạn.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi giá trị Độ rộng khoảng cách?

Để thay đổi độ rộng khoảng cách, hãy sử dụng `setGapWidth` phương pháp trên `ParentSeriesGroup` của chuỗi biểu đồ. Trong ví dụ được cung cấp, chúng tôi đặt Độ rộng khoảng cách là 50, nhưng bạn có thể điều chỉnh giá trị này theo khoảng cách mong muốn.

### Tôi có thể tùy chỉnh các thuộc tính khác của biểu đồ không?

Có, Aspose.Slides for Java cung cấp khả năng tùy chỉnh biểu đồ mở rộng. Bạn có thể sửa đổi nhiều thuộc tính biểu đồ, chẳng hạn như màu sắc, nhãn, tiêu đề, v.v. Kiểm tra Tài liệu tham khảo API để biết thông tin chi tiết về các tùy chọn tùy chỉnh biểu đồ.

### Tôi có thể tìm thêm tài liệu và nguồn lực ở đâu?

Bạn có thể tìm thấy tài liệu toàn diện và các tài nguyên bổ sung về Aspose.Slides cho Java trên [Trang web Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}