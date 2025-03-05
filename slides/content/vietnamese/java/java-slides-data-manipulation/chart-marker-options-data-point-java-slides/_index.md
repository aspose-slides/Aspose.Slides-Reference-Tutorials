---
title: Tùy chọn điểm đánh dấu biểu đồ trên điểm dữ liệu trong trang trình bày Java
linktitle: Tùy chọn điểm đánh dấu biểu đồ trên điểm dữ liệu trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tối ưu hóa các trang trình bày Java của bạn với các tùy chọn đánh dấu biểu đồ tùy chỉnh. Tìm hiểu cách nâng cao điểm dữ liệu một cách trực quan bằng Aspose.Slides cho Java. Khám phá hướng dẫn từng bước và câu hỏi thường gặp.
type: docs
weight: 14
url: /vi/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Giới thiệu về Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Java Slides

Khi nói đến việc tạo ra các bản trình bày có tác động mạnh mẽ, khả năng tùy chỉnh và thao tác với các điểm đánh dấu biểu đồ trên các điểm dữ liệu có thể tạo ra sự khác biệt. Với Aspose.Slides cho Java, bạn có khả năng chuyển đổi biểu đồ của mình thành các phần tử động và hấp dẫn trực quan.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào phần mã hóa, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Aspose.Slides cho Thư viện Java
- Môi trường phát triển tích hợp Java (IDE)
- Tài liệu trình bày mẫu (ví dụ: "Test.pptx")

## Bước 1: Thiết lập môi trường

Trước tiên, hãy đảm bảo bạn đã cài đặt và sẵn sàng các công cụ cần thiết. Tạo một dự án Java trong IDE của bạn và nhập thư viện Aspose.Slides cho Java.

## Bước 2: Tải bài thuyết trình

Để bắt đầu, hãy tải tài liệu trình bày mẫu của bạn. Trong mã được cung cấp, chúng tôi giả sử tài liệu có tên là "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Bước 3: Tạo biểu đồ

Bây giờ, hãy tạo một biểu đồ trong bài thuyết trình. Chúng tôi sẽ sử dụng Biểu đồ đường có điểm đánh dấu trong ví dụ này.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Bước 4: Làm việc với dữ liệu biểu đồ

Để thao tác với dữ liệu biểu đồ, chúng ta cần truy cập vào bảng tính dữ liệu biểu đồ và chuẩn bị chuỗi dữ liệu. Chúng tôi sẽ xóa chuỗi mặc định và thêm dữ liệu tùy chỉnh của mình.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Bước 5: Thêm điểm đánh dấu tùy chỉnh

Đây là phần thú vị - tùy chỉnh điểm đánh dấu trên các điểm dữ liệu. Chúng tôi sẽ sử dụng hình ảnh làm điểm đánh dấu trong ví dụ này.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Thêm điểm đánh dấu tùy chỉnh vào điểm dữ liệu
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Lặp lại cho các điểm dữ liệu khác
// ...

// Thay đổi kích thước điểm đánh dấu chuỗi biểu đồ
series.getMarker().setSize(15);
```

## Bước 6: Lưu bài thuyết trình

Sau khi bạn đã tùy chỉnh các điểm đánh dấu biểu đồ của mình, hãy lưu bản trình bày để xem các thay đổi đang diễn ra.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh cho các tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong các trang trình bày Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Tạo biểu đồ mặc định
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Lấy chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
//Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Xóa loạt bản demo
chart.getChartData().getSeries().clear();
//Thêm loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Đặt hình ảnh
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Đặt hình ảnh
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Thêm điểm mới (1:3) vào đó.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Thay đổi điểm đánh dấu chuỗi biểu đồ
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Với Aspose.Slides cho Java, bạn có thể nâng cao bản trình bày của mình bằng cách tùy chỉnh các điểm đánh dấu biểu đồ trên các điểm dữ liệu. Điều này cho phép bạn tạo các slide trực quan ấn tượng và giàu thông tin để thu hút khán giả.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi kích thước điểm đánh dấu cho điểm dữ liệu?

 Để thay đổi kích thước điểm đánh dấu cho các điểm dữ liệu, hãy sử dụng`series.getMarker().setSize()` phương thức và cung cấp kích thước mong muốn làm đối số.

### Tôi có thể sử dụng hình ảnh làm điểm đánh dấu tùy chỉnh không?

 Có, bạn có thể sử dụng hình ảnh làm điểm đánh dấu tùy chỉnh cho điểm dữ liệu. Đặt loại điền thành`FillType.Picture` và cung cấp hình ảnh bạn muốn sử dụng.

### Aspose.Slides cho Java có phù hợp để tạo biểu đồ động không?

Tuyệt đối! Aspose.Slides cho Java cung cấp các khả năng mở rộng để tạo biểu đồ động và tương tác trong bản trình bày của bạn.

### Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ bằng Aspose.Slides không?

Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của biểu đồ, bao gồm tiêu đề, trục, nhãn dữ liệu, v.v. bằng cách sử dụng Aspose.Slides cho Java.

### Tôi có thể truy cập tài liệu và nội dung tải xuống Aspose.Slides dành cho Java ở đâu?

 Bạn có thể tìm thấy tài liệu tại[đây](https://reference.aspose.com/slides/java/) và tải xuống thư viện tại[đây](https://releases.aspose.com/slides/java/).