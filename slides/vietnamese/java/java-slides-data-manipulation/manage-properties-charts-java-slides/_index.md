---
title: Quản lý biểu đồ thuộc tính trong Java Slides
linktitle: Quản lý biểu đồ thuộc tính trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo các biểu đồ tuyệt đẹp và quản lý các thuộc tính trong các trang trình bày Java bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn để có bài thuyết trình hiệu quả.
weight: 13
url: /vi/java/data-manipulation/manage-properties-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Quản lý thuộc tính và biểu đồ trong Java Slide bằng Aspose.Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý các thuộc tính và tạo biểu đồ trong các trang chiếu Java bằng Aspose.Slides. Aspose.Slides là một API Java mạnh mẽ để làm việc với các bản trình bày PowerPoint. Chúng tôi sẽ hướng dẫn quy trình từng bước, bao gồm các ví dụ về mã nguồn.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn đã cài đặt và thiết lập thư viện Aspose.Slides cho Java trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Thêm biểu đồ vào slide

Để thêm biểu đồ vào slide, hãy làm theo các bước sau:

1. Nhập các lớp cần thiết và tạo một thể hiện của lớp Trình bày.

```java
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
```

2. Truy cập vào slide nơi bạn muốn thêm biểu đồ. Trong ví dụ này, chúng ta truy cập vào slide đầu tiên.

```java
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Thêm biểu đồ với dữ liệu mặc định. Trong trường hợp này, chúng tôi đang thêm biểu đồ StackedColumn3D.

```java
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Cài đặt dữ liệu biểu đồ

Để đặt dữ liệu biểu đồ, chúng ta cần tạo sổ làm việc dữ liệu biểu đồ, đồng thời thêm chuỗi và danh mục. Thực hiện theo các bước sau:

4. Đặt chỉ mục của bảng dữ liệu biểu đồ.

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
```

5. Lấy sổ làm việc dữ liệu biểu đồ.

```java
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Thêm chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi thêm hai chuỗi có tên "Series 1" và "Series 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Thêm danh mục vào biểu đồ. Ở đây, chúng tôi thêm ba loại.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Đặt thuộc tính xoay 3D

Bây giờ, hãy đặt thuộc tính xoay 3D cho biểu đồ:

8. Đặt các trục góc vuông.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Đặt góc quay cho trục X và Y. Trong ví dụ này, chúng ta xoay X 40 độ và Y 270 độ.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Đặt phần trăm độ sâu thành 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Điền dữ liệu chuỗi

11. Lấy chuỗi biểu đồ thứ hai và điền vào đó các điểm dữ liệu.

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

12. Đặt giá trị chồng chéo cho chuỗi. Ví dụ: bạn có thể đặt thành 100 để không bị trùng lặp.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Lưu bản trình bày

Cuối cùng, lưu bản trình bày vào đĩa.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo thành công biểu đồ cột xếp chồng 3D với các thuộc tính tùy chỉnh bằng Aspose.Slides trong Java.

## Mã nguồn hoàn chỉnh để quản lý biểu đồ thuộc tính trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Đặt thuộc tính Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Lấy loạt biểu đồ thứ hai
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Đặt giá trị OverLap
series.getParentSeriesGroup().setOverlap((byte) 100);
// Ghi bài thuyết trình vào đĩa
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã đi sâu vào thế giới quản lý thuộc tính và tạo biểu đồ trong các trang chiếu Java bằng Aspose.Slides. Aspose.Slides là một API Java mạnh mẽ hỗ trợ các nhà phát triển làm việc với các bản trình bày PowerPoint một cách hiệu quả. Chúng tôi đã trình bày các bước thiết yếu và cung cấp các ví dụ về mã nguồn để hướng dẫn bạn thực hiện quy trình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại biểu đồ?

 Bạn có thể thay đổi loại biểu đồ bằng cách sửa đổi`ChartType` tham số khi thêm biểu đồ. Tham khảo tài liệu Aspose.Slides để biết các loại biểu đồ có sẵn.

### Tôi có thể tùy chỉnh màu biểu đồ không?

Có, bạn có thể tùy chỉnh màu biểu đồ bằng cách đặt thuộc tính tô màu của các điểm hoặc danh mục dữ liệu chuỗi.

### Làm cách nào để thêm nhiều điểm dữ liệu hơn vào một chuỗi?

 Bạn có thể thêm nhiều điểm dữ liệu hơn vào một chuỗi bằng cách sử dụng`series.getDataPoints().addDataPointForBarSeries()` phương thức và chỉ định ô chứa giá trị dữ liệu.

### Làm cách nào để đặt góc quay khác?

 Để đặt góc quay khác cho trục X và Y, hãy sử dụng`chart.getRotation3D().setRotationX()` Và`chart.getRotation3D().setRotationY()` với các giá trị góc mong muốn.

### Tôi có thể tùy chỉnh những thuộc tính 3D nào khác?

Bạn có thể khám phá các thuộc tính 3D khác của biểu đồ, chẳng hạn như độ sâu, phối cảnh và ánh sáng, bằng cách tham khảo tài liệu Aspose.Slides.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
