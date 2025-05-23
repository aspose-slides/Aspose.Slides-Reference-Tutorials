---
"description": "Cải thiện bài thuyết trình PowerPoint của bạn với Aspose.Slides for Java. Học cách sửa đổi biểu đồ hiện có theo chương trình. Hướng dẫn từng bước với mã nguồn để tùy chỉnh biểu đồ."
"linktitle": "Biểu đồ hiện có trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ hiện có trong Java Slides"
"url": "/vi/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ hiện có trong Java Slides


## Giới thiệu về Biểu đồ hiện có trong Java Slides sử dụng Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ trình bày cách sửa đổi biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Chúng tôi sẽ hướng dẫn các bước để thay đổi dữ liệu biểu đồ, tên danh mục, tên chuỗi và thêm chuỗi mới vào biểu đồ. Đảm bảo bạn đã thiết lập Aspose.Slides for Java trong dự án của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Thư viện Aspose.Slides cho Java được bao gồm trong dự án của bạn.
2. Một bản trình bày PowerPoint hiện có có biểu đồ mà bạn muốn sửa đổi.
3. Thiết lập môi trường phát triển Java.

## Bước 1: Tải bài thuyết trình

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Khởi tạo lớp Presentation biểu diễn tệp PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Bước 2: Truy cập vào Slide và Biểu đồ

```java
// Truy cập trang chiếu đầu tiên
ISlide sld = pres.getSlides().get_Item(0);

// Truy cập biểu đồ trên trang chiếu
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Bước 3: Thay đổi Dữ liệu Biểu đồ và Tên Danh mục

```java
// Thiết lập chỉ mục của biểu đồ dữ liệu bảng
int defaultWorksheetIndex = 0;

// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Thay đổi tên danh mục biểu đồ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Bước 4: Cập nhật Biểu đồ Chuỗi đầu tiên

```java
// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Cập nhật tên series
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Cập nhật dữ liệu chuỗi
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Bước 5: Cập nhật Biểu đồ Chuỗi Thứ hai

```java
// Lấy chuỗi biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);

// Cập nhật tên series
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Cập nhật dữ liệu chuỗi
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Bước 6: Thêm một chuỗi mới vào biểu đồ

```java
// Thêm một loạt mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Lấy chuỗi biểu đồ thứ ba
series = chart.getChartData().getSeries().get_Item(2);

// Điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Bước 7: Thay đổi loại biểu đồ

```java
// Thay đổi loại biểu đồ thành Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Bước 8: Lưu bản trình bày đã sửa đổi

```java
// Lưu bản trình bày với biểu đồ đã sửa đổi
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Xin chúc mừng! Bạn đã sửa đổi thành công biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bây giờ bạn có thể sử dụng mã này để tùy chỉnh biểu đồ trong bản trình bày PowerPoint của mình theo chương trình.

## Mã nguồn đầy đủ cho biểu đồ hiện có trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Presentation biểu diễn tệp PPTX// Khởi tạo lớp Presentation biểu diễn tệp PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Truy cập slide đầu tiênMarker
ISlide sld = pres.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Thay đổi tên danh mục biểu đồ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Hiện đang cập nhật dữ liệu chuỗi
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Sửa đổi tên series
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Lấy chuỗi biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Hiện đang cập nhật dữ liệu chuỗi
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Sửa đổi tên series
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Bây giờ, thêm một loạt mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Lấy chuỗi biểu đồ thứ 3
series = chart.getChartData().getSeries().get_Item(2);
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Lưu bài thuyết trình có biểu đồ
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Phần kết luận

Trong hướng dẫn toàn diện này, chúng ta đã học cách sửa đổi biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bằng cách làm theo hướng dẫn từng bước và sử dụng các ví dụ về mã nguồn, bạn có thể dễ dàng tùy chỉnh và cập nhật biểu đồ để đáp ứng các yêu cầu cụ thể của mình. Sau đây là tóm tắt những gì chúng tôi đã đề cập:

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi loại biểu đồ?

Bạn có thể thay đổi loại biểu đồ bằng cách sử dụng `chart.setType(ChartType.ChartTypeHere)` phương pháp. Thay thế `ChartTypeHere` với loại biểu đồ mong muốn, chẳng hạn như `ChartType.ClusteredCylinder` trong ví dụ của chúng tôi.

### Tôi có thể thêm nhiều điểm dữ liệu vào một chuỗi không?

Có, bạn có thể thêm nhiều điểm dữ liệu hơn vào một chuỗi bằng cách sử dụng `series.getDataPoints().addDataPointForBarSeries(cell)` phương pháp. Đảm bảo cung cấp dữ liệu ô phù hợp.

### Làm thế nào để cập nhật tên danh mục?

Bạn có thể cập nhật tên danh mục bằng cách sử dụng `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` để đặt tên danh mục mới.

### Làm thế nào để tôi sửa đổi tên series?

Để sửa đổi tên sê-ri, hãy sử dụng `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` để đặt tên cho series mới.

### Có cách nào để xóa một chuỗi khỏi biểu đồ không?

Có, bạn có thể xóa một chuỗi khỏi biểu đồ bằng cách sử dụng `chart.getChartData().getSeries().removeAt(index)` phương pháp, nơi `index` là chỉ số của chuỗi bạn muốn xóa.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}