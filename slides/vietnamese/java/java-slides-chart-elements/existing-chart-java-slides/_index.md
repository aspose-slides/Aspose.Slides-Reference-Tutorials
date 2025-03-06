---
title: Biểu đồ hiện có trong Java Slides
linktitle: Biểu đồ hiện có trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Cải thiện bản trình bày PowerPoint của bạn với Aspose.Slides cho Java. Tìm hiểu cách sửa đổi các biểu đồ hiện có theo chương trình. Hướng dẫn từng bước với mã nguồn để tùy chỉnh biểu đồ.
type: docs
weight: 12
url: /vi/java/chart-elements/existing-chart-java-slides/
---

## Giới thiệu về Biểu đồ hiện có trong Java Slides bằng Aspose.Slides for Java

Trong hướng dẫn này, chúng tôi sẽ trình bày cách sửa đổi biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Chúng ta sẽ thực hiện các bước để thay đổi dữ liệu biểu đồ, tên danh mục, tên chuỗi và thêm chuỗi mới vào biểu đồ. Đảm bảo bạn đã thiết lập Aspose.Slides cho Java trong dự án của mình.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Thư viện Aspose.Slides dành cho Java có trong dự án của bạn.
2. Bản trình bày PowerPoint hiện có có biểu đồ mà bạn muốn sửa đổi.
3. Môi trường phát triển Java được thiết lập.

## Bước 1: Tải bài thuyết trình

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Bước 2: Truy cập Slide và Biểu đồ

```java
// Truy cập slide đầu tiên
ISlide sld = pres.getSlides().get_Item(0);

// Truy cập biểu đồ trên slide
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Bước 3: Thay đổi dữ liệu biểu đồ và tên danh mục

```java
// Đặt chỉ mục cho bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;

// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Thay đổi tên danh mục biểu đồ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Bước 4: Cập nhật chuỗi biểu đồ đầu tiên

```java
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Cập nhật tên bộ truyện
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Cập nhật dữ liệu chuỗi
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Bước 5: Cập nhật chuỗi biểu đồ thứ hai

```java
// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);

// Cập nhật tên bộ truyện
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Cập nhật dữ liệu chuỗi
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Bước 6: Thêm chuỗi mới vào biểu đồ

```java
// Thêm một loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Lấy loạt biểu đồ thứ ba
series = chart.getChartData().getSeries().get_Item(2);

// Điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Bước 7: Thay đổi loại biểu đồ

```java
//Thay đổi loại biểu đồ thành Clustered Xi lanh
chart.setType(ChartType.ClusteredCylinder);
```

## Bước 8: Lưu bản trình bày đã sửa đổi

```java
// Lưu bản trình bày với biểu đồ đã sửa đổi
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Chúc mừng! Bạn đã sửa đổi thành công biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bây giờ bạn có thể sử dụng mã này để tùy chỉnh biểu đồ trong bản trình bày PowerPoint của mình theo chương trình.

## Mã nguồn hoàn chỉnh cho biểu đồ hiện có trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Truy cập slideMarker đầu tiên
ISlide sld = pres.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Thay đổi tên danh mục biểu đồ
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Đang cập nhật dữ liệu chuỗi
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Sửa đổi tên bộ truyện
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Đang cập nhật dữ liệu chuỗi
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Sửa đổi tên bộ truyện
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Bây giờ, Thêm một loạt mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Lấy loạt biểu đồ thứ 3
series = chart.getChartData().getSeries().get_Item(2);
// Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Lưu bài thuyết trình bằng biểu đồ
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Phần kết luận

Trong hướng dẫn toàn diện này, chúng ta đã học cách sửa đổi biểu đồ hiện có trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bằng cách làm theo hướng dẫn từng bước và sử dụng các ví dụ về mã nguồn, bạn có thể dễ dàng tùy chỉnh và cập nhật biểu đồ để đáp ứng các yêu cầu cụ thể của mình. Dưới đây là bản tóm tắt về những gì chúng tôi đã đề cập:

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại biểu đồ?

 Bạn có thể thay đổi loại biểu đồ bằng cách sử dụng`chart.setType(ChartType.ChartTypeHere)` phương pháp. Thay thế`ChartTypeHere` với loại biểu đồ mong muốn, chẳng hạn như`ChartType.ClusteredCylinder` trong ví dụ của chúng tôi.

### Tôi có thể thêm nhiều điểm dữ liệu hơn vào một chuỗi không?

 Có, bạn có thể thêm nhiều điểm dữ liệu hơn vào chuỗi bằng cách sử dụng`series.getDataPoints().addDataPointForBarSeries(cell)` phương pháp. Đảm bảo cung cấp dữ liệu ô thích hợp.

### Làm cách nào để cập nhật tên danh mục?

 Bạn có thể cập nhật tên danh mục bằng cách sử dụng`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` để đặt tên danh mục mới.

### Làm cách nào để sửa đổi tên bộ truyện?

 Để sửa đổi tên chuỗi, hãy sử dụng`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` để đặt tên loạt phim mới.

### Có cách nào để xóa một chuỗi khỏi biểu đồ không?

 Có, bạn có thể xóa một chuỗi khỏi biểu đồ bằng cách sử dụng`chart.getChartData().getSeries().removeAt(index)` phương pháp, ở đâu`index`là chỉ mục của chuỗi bạn muốn xóa.