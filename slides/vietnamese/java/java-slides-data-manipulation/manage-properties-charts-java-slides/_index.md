---
"description": "Học cách tạo biểu đồ ấn tượng và quản lý thuộc tính trong slide Java bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn cho các bài thuyết trình mạnh mẽ."
"linktitle": "Quản lý biểu đồ thuộc tính trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Quản lý biểu đồ thuộc tính trong Java Slides"
"url": "/vi/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý biểu đồ thuộc tính trong Java Slides


## Giới thiệu về Quản lý Thuộc tính và Biểu đồ trong Java Slides sử dụng Aspose.Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý thuộc tính và tạo biểu đồ trong Java slide bằng Aspose.Slides. Aspose.Slides là một Java API mạnh mẽ để làm việc với các bài thuyết trình PowerPoint. Chúng ta sẽ hướng dẫn từng bước, bao gồm các ví dụ về mã nguồn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides cho Java trong dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Thêm biểu đồ vào trang chiếu

Để thêm biểu đồ vào trang chiếu, hãy làm theo các bước sau:

1. Nhập các lớp cần thiết và tạo một phiên bản của lớp Presentation.

```java
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
```

2. Truy cập vào slide mà bạn muốn thêm biểu đồ. Trong ví dụ này, chúng ta truy cập vào slide đầu tiên.

```java
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Thêm biểu đồ có dữ liệu mặc định. Trong trường hợp này, chúng tôi đang thêm biểu đồ StackedColumn3D.

```java
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Thiết lập dữ liệu biểu đồ

Để thiết lập dữ liệu biểu đồ, chúng ta cần tạo một bảng tính dữ liệu biểu đồ và thêm chuỗi và danh mục. Thực hiện theo các bước sau:

4. Thiết lập chỉ mục của bảng dữ liệu biểu đồ.

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
```

5. Nhận sổ làm việc dữ liệu biểu đồ.

```java
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Thêm chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi thêm hai chuỗi có tên là "Chuỗi 1" và "Chuỗi 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Thêm danh mục vào biểu đồ. Ở đây, chúng tôi thêm ba danh mục.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Thiết lập Thuộc tính Xoay 3D

Bây giờ, hãy thiết lập thuộc tính xoay 3D cho biểu đồ:

8. Đặt trục góc vuông.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Đặt góc quay cho trục X và Y. Trong ví dụ này, chúng ta xoay X 40 độ và Y 270 độ.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Đặt tỷ lệ độ sâu thành 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Điền dữ liệu chuỗi

11. Lấy chuỗi biểu đồ thứ hai và điền các điểm dữ liệu vào đó.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Điều chỉnh chồng chéo

12. Đặt giá trị chồng chéo cho chuỗi. Ví dụ, bạn có thể đặt thành 100 để không chồng chéo.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình vào đĩa.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công biểu đồ cột xếp chồng 3D với các thuộc tính tùy chỉnh bằng Aspose.Slides trong Java.

## Mã nguồn đầy đủ để quản lý biểu đồ thuộc tính trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Đặt thuộc tính Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Lấy chuỗi biểu đồ thứ hai
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Đặt giá trị OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Ghi bản trình bày vào đĩa
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đi sâu vào thế giới quản lý thuộc tính và tạo biểu đồ trong các slide Java bằng Aspose.Slides. Aspose.Slides là một API Java mạnh mẽ giúp các nhà phát triển làm việc hiệu quả với các bài thuyết trình PowerPoint. Chúng tôi đã đề cập đến các bước thiết yếu và cung cấp các ví dụ về mã nguồn để hướng dẫn bạn trong suốt quá trình.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi loại biểu đồ?

Bạn có thể thay đổi loại biểu đồ bằng cách sửa đổi `ChartType` tham số khi thêm biểu đồ. Tham khảo tài liệu Aspose.Slides để biết các loại biểu đồ có sẵn.

### Tôi có thể tùy chỉnh màu biểu đồ không?

Có, bạn có thể tùy chỉnh màu biểu đồ bằng cách thiết lập thuộc tính tô của các điểm dữ liệu chuỗi hoặc danh mục.

### Làm thế nào để thêm nhiều điểm dữ liệu vào một chuỗi?

Bạn có thể thêm nhiều điểm dữ liệu hơn vào một chuỗi bằng cách sử dụng `series.getDataPoints().addDataPointForBarSeries()` phương pháp và chỉ định ô chứa giá trị dữ liệu.

### Làm thế nào tôi có thể thiết lập góc quay khác nhau?

Để thiết lập góc quay khác nhau cho trục X và Y, hãy sử dụng `chart.getRotation3D().setRotationX()` Và `chart.getRotation3D().setRotationY()` với giá trị góc mong muốn.

### Tôi có thể tùy chỉnh những thuộc tính 3D nào khác?

Bạn có thể khám phá các thuộc tính 3D khác của biểu đồ, chẳng hạn như độ sâu, phối cảnh và ánh sáng, bằng cách tham khảo tài liệu Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}