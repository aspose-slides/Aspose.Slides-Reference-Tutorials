---
"description": "Tối ưu hóa Java Slides của bạn với Custom Chart Marker Options. Tìm hiểu cách tăng cường các điểm dữ liệu trực quan bằng Aspose.Slides for Java. Khám phá hướng dẫn từng bước và Câu hỏi thường gặp."
"linktitle": "Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Java Slides"
"url": "/vi/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Java Slides


## Giới thiệu về Tùy chọn đánh dấu biểu đồ trên Điểm dữ liệu trong Java Slides

Khi nói đến việc tạo các bài thuyết trình có tác động, khả năng tùy chỉnh và thao tác các điểm đánh dấu biểu đồ trên các điểm dữ liệu có thể tạo nên sự khác biệt. Với Aspose.Slides for Java, bạn có khả năng biến đổi biểu đồ của mình thành các thành phần năng động và hấp dẫn về mặt hình ảnh.

## Điều kiện tiên quyết

Trước khi đi sâu vào phần mã hóa, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Aspose.Slides cho Thư viện Java
- Môi trường phát triển tích hợp Java (IDE)
- Tài liệu trình bày mẫu (ví dụ: "Test.pptx")

## Bước 1: Thiết lập môi trường

Trước tiên, hãy đảm bảo bạn đã cài đặt và sẵn sàng các công cụ cần thiết. Tạo một dự án Java trong IDE của bạn và nhập thư viện Aspose.Slides cho Java.

## Bước 2: Tải bài thuyết trình

Để bắt đầu, hãy tải tài liệu trình bày mẫu của bạn. Trong mã được cung cấp, chúng tôi giả sử tài liệu có tên là "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Bước 3: Tạo biểu đồ

Bây giờ, chúng ta hãy tạo một biểu đồ trong bài thuyết trình. Chúng ta sẽ sử dụng Biểu đồ đường có đánh dấu trong ví dụ này.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Bước 4: Làm việc với dữ liệu biểu đồ

Để thao tác dữ liệu biểu đồ, chúng ta cần truy cập vào sổ làm việc dữ liệu biểu đồ và chuẩn bị chuỗi dữ liệu. Chúng ta sẽ xóa chuỗi mặc định và thêm dữ liệu tùy chỉnh của mình.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Bước 5: Thêm các điểm đánh dấu tùy chỉnh

Đây là phần thú vị - tùy chỉnh các điểm đánh dấu trên các điểm dữ liệu. Chúng ta sẽ sử dụng hình ảnh làm điểm đánh dấu trong ví dụ này.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Thêm các điểm đánh dấu tùy chỉnh vào các điểm dữ liệu
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Lặp lại cho các điểm dữ liệu khác
// ...

// Thay đổi kích thước đánh dấu chuỗi biểu đồ
series.getMarker().setSize(15);
```

## Bước 6: Lưu bài thuyết trình

Sau khi tùy chỉnh các điểm đánh dấu biểu đồ, hãy lưu bản trình bày để xem những thay đổi.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho các tùy chọn đánh dấu biểu đồ trên điểm dữ liệu trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Tạo biểu đồ mặc định
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Nhận chỉ mục bảng tính dữ liệu biểu đồ mặc định
int defaultWorksheetIndex = 0;
//Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Xóa loạt bản demo
chart.getChartData().getSeries().clear();
//Thêm series mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Đặt hình ảnh
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Đặt hình ảnh
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Lấy chuỗi biểu đồ đầu tiên
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
//Thay đổi dấu hiệu chuỗi biểu đồ
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Với Aspose.Slides for Java, bạn có thể nâng cao bài thuyết trình của mình bằng cách tùy chỉnh các điểm đánh dấu biểu đồ trên các điểm dữ liệu. Điều này cho phép bạn tạo các slide trực quan tuyệt đẹp và nhiều thông tin thu hút khán giả.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi kích thước điểm đánh dấu cho các điểm dữ liệu?

Để thay đổi kích thước điểm đánh dấu cho các điểm dữ liệu, hãy sử dụng `series.getMarker().setSize()` phương pháp và cung cấp kích thước mong muốn làm đối số.

### Tôi có thể sử dụng hình ảnh làm điểm đánh dấu tùy chỉnh không?

Có, bạn có thể sử dụng hình ảnh làm điểm đánh dấu tùy chỉnh cho các điểm dữ liệu. Đặt loại điền thành `FillType.Picture` và cung cấp hình ảnh bạn muốn sử dụng.

### Aspose.Slides for Java có phù hợp để tạo biểu đồ động không?

Chắc chắn rồi! Aspose.Slides for Java cung cấp nhiều khả năng mở rộng để tạo biểu đồ động và tương tác trong bài thuyết trình của bạn.

### Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ bằng Aspose.Slides không?

Có, bạn có thể tùy chỉnh nhiều khía cạnh khác nhau của biểu đồ, bao gồm tiêu đề, trục, nhãn dữ liệu, v.v. bằng Aspose.Slides for Java.

### Tôi có thể truy cập tài liệu và tải xuống Aspose.Slides for Java ở đâu?

Bạn có thể tìm thấy tài liệu tại [đây](https://reference.aspose.com/slides/java/) và tải xuống thư viện tại [đây](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}