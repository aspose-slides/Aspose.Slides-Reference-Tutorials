---
title: Thêm thanh lỗi trong trang trình bày Java
linktitle: Thêm thanh lỗi trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm thanh lỗi vào biểu đồ PowerPoint trong Java bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn để tùy chỉnh các thanh lỗi.
type: docs
weight: 13
url: /vi/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Giới thiệu về Thêm thanh lỗi trong Java Slide bằng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thêm các thanh lỗi vào biểu đồ trong trang chiếu PowerPoint bằng Aspose.Slides cho Java. Thanh lỗi cung cấp thông tin có giá trị về tính biến đổi hoặc độ không chắc chắn của các điểm dữ liệu trong biểu đồ. Chúng tôi sẽ tạo biểu đồ bong bóng và thêm các thanh lỗi vào đó. Bắt đầu nào!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ[trang web giả định](https://downloads.aspose.com/slides/java).

## Bước 1: Tạo một bài thuyết trình trống

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bản trình bày trống
Presentation presentation = new Presentation();
```

Trong bước này, chúng tôi tạo một bản trình bày trống trong đó chúng tôi sẽ thêm biểu đồ của mình với các thanh lỗi.

## Bước 2: Tạo biểu đồ bong bóng

```java
// Tạo biểu đồ bong bóng
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Ở đây, chúng ta tạo biểu đồ bong bóng và chỉ định vị trí cũng như kích thước của nó trên slide.

## Bước 3: Thêm thanh lỗi và định dạng cài đặt

```java
// Thêm thanh Lỗi và đặt định dạng của nó
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Trong bước này, chúng ta thêm các thanh lỗi vào biểu đồ và đặt định dạng của chúng. Bạn có thể tùy chỉnh các thanh lỗi bằng cách thay đổi giá trị, loại và các thuộc tính khác.

- `errBarX` đại diện cho các thanh lỗi dọc theo trục X.
- `errBarY` đại diện cho các thanh lỗi dọc theo trục Y.
- Chúng tôi hiển thị cả hai thanh lỗi X và Y.
- `setValueType` chỉ định loại giá trị cho các thanh lỗi (ví dụ: Cố định hoặc Tỷ lệ phần trăm).
- `setValue` đặt giá trị cho các thanh lỗi.
- `setType` xác định loại thanh lỗi (ví dụ: Plus hoặc Minus).
-  Chúng tôi đặt độ rộng của các dòng thanh lỗi bằng cách sử dụng`getFormat().getLine().setWidth(2)`.
- `setEndCap`chỉ định có bao gồm chữ hoa kết thúc trên thanh lỗi hay không.

## Bước 4: Lưu bài thuyết trình

```java
// Đang lưu bản trình bày
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Cuối cùng, chúng tôi lưu bản trình bày có thêm các thanh lỗi vào một vị trí được chỉ định.

Đó là nó! Bạn đã thêm thành công các thanh lỗi vào biểu đồ trong slide PowerPoint bằng Aspose.Slides for Java.

## Mã nguồn hoàn chỉnh để thêm thanh lỗi trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bản trình bày trống
Presentation presentation = new Presentation();
try
{
	// Tạo biểu đồ bong bóng
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Thêm thanh Lỗi và đặt định dạng của nó
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Đang lưu bản trình bày
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách cải thiện bản trình bày PowerPoint của bạn bằng cách thêm các thanh lỗi vào biểu đồ bằng Aspose.Slides cho Java. Các thanh lỗi cung cấp thông tin chi tiết có giá trị về tính biến đổi và độ không chắc chắn của dữ liệu, giúp bản trình bày của bạn có nhiều thông tin hơn và hấp dẫn trực quan hơn.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể tùy chỉnh thêm giao diện của thanh lỗi?

Bạn có thể tùy chỉnh các thanh lỗi bằng cách sửa đổi các thuộc tính của chúng, chẳng hạn như kiểu đường, màu sắc và chiều rộng, như được minh họa ở Bước 3.

### Tôi có thể thêm thanh lỗi vào các loại biểu đồ khác nhau không?

Có, bạn có thể thêm các thanh lỗi vào các loại biểu đồ khác nhau được Aspose.Slides for Java hỗ trợ. Chỉ cần tạo loại biểu đồ mong muốn và làm theo các bước tùy chỉnh thanh lỗi tương tự.

### Làm cách nào để điều chỉnh vị trí và kích thước của biểu đồ trên slide?

 Bạn có thể kiểm soát vị trí và kích thước của biểu đồ bằng cách điều chỉnh các tham số trong`addChart` phương pháp như ở Bước 2.

### Tôi có thể tìm thêm thông tin về Aspose.Slides cho Java ở đâu?

 Bạn có thể tham khảo các[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/) để biết thông tin chi tiết về việc sử dụng thư viện.