---
"description": "Tìm hiểu cách thêm thanh lỗi vào biểu đồ PowerPoint bằng Java bằng Aspose.Slides. Hướng dẫn từng bước có mã nguồn để tùy chỉnh thanh lỗi."
"linktitle": "Thêm Thanh Lỗi vào Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm Thanh Lỗi vào Java Slides"
"url": "/vi/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Thanh Lỗi vào Java Slides


## Giới thiệu về cách thêm thanh lỗi vào Java Slides bằng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thêm thanh lỗi vào biểu đồ trong slide PowerPoint bằng Aspose.Slides for Java. Thanh lỗi cung cấp thông tin có giá trị về tính biến động hoặc không chắc chắn của các điểm dữ liệu trong biểu đồ. Chúng tôi sẽ tạo biểu đồ bong bóng và thêm thanh lỗi vào đó. Hãy bắt đầu nào!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ [Trang web Aspose](https://downloads.aspose.com/slides/java).

## Bước 1: Tạo một bài thuyết trình trống

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bài thuyết trình trống
Presentation presentation = new Presentation();
```

Ở bước này, chúng ta sẽ tạo một bản trình bày trống để thêm biểu đồ có thanh lỗi.

## Bước 2: Tạo biểu đồ bong bóng

```java
// Tạo biểu đồ bong bóng
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Ở đây, chúng ta tạo biểu đồ bong bóng và chỉ định vị trí cũng như kích thước của biểu đồ đó trên trang chiếu.

## Bước 3: Thêm Thanh Lỗi và Thiết lập Định dạng

```java
// Thêm thanh Lỗi và thiết lập định dạng của nó
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

Trong bước này, chúng ta thêm thanh lỗi vào biểu đồ và thiết lập định dạng của chúng. Bạn có thể tùy chỉnh thanh lỗi bằng cách thay đổi giá trị, loại và các thuộc tính khác.

- `errBarX` biểu thị các thanh lỗi dọc theo trục X.
- `errBarY` biểu thị các thanh lỗi dọc theo trục Y.
- Chúng tôi làm cho cả thanh lỗi X và Y hiển thị rõ ràng.
- `setValueType` chỉ định loại giá trị cho thanh lỗi (ví dụ: Cố định hoặc Phần trăm).
- `setValue` đặt giá trị cho thanh lỗi.
- `setType` xác định loại thanh lỗi (ví dụ: Cộng hoặc Trừ).
- Chúng tôi thiết lập chiều rộng của các dòng thanh lỗi bằng cách sử dụng `getFormat().getLine().setWidth(2)`.
- `setEndCap` chỉ rõ có nên bao gồm nắp cuối trên thanh lỗi hay không.

## Bước 4: Lưu bài thuyết trình

```java
// Lưu bài thuyết trình
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Cuối cùng, chúng ta lưu bản trình bày có thêm thanh lỗi vào vị trí đã chỉ định.

Vậy là xong! Bạn đã thêm thành công thanh lỗi vào biểu đồ trong trang chiếu PowerPoint bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ để thêm thanh lỗi trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bài thuyết trình trống
Presentation presentation = new Presentation();
try
{
	// Tạo biểu đồ bong bóng
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Thêm thanh Lỗi và thiết lập định dạng của nó
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
	// Lưu bài thuyết trình
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách cải thiện bài thuyết trình PowerPoint của bạn bằng cách thêm thanh lỗi vào biểu đồ bằng Aspose.Slides for Java. Thanh lỗi cung cấp thông tin chi tiết có giá trị về tính biến động và sự không chắc chắn của dữ liệu, giúp bài thuyết trình của bạn nhiều thông tin hơn và hấp dẫn hơn về mặt hình ảnh.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh giao diện của thanh lỗi như thế nào?

Bạn có thể tùy chỉnh thanh lỗi bằng cách sửa đổi các thuộc tính của chúng, chẳng hạn như kiểu đường kẻ, màu sắc và chiều rộng, như được minh họa trong Bước 3.

### Tôi có thể thêm thanh lỗi vào các loại biểu đồ khác nhau không?

Có, bạn có thể thêm thanh lỗi vào nhiều loại biểu đồ được Aspose.Slides for Java hỗ trợ. Chỉ cần tạo loại biểu đồ mong muốn và làm theo các bước tùy chỉnh thanh lỗi tương tự.

### Làm thế nào để điều chỉnh vị trí và kích thước của biểu đồ trên slide?

Bạn có thể kiểm soát vị trí và kích thước của biểu đồ bằng cách điều chỉnh các thông số trong `addChart` phương pháp như thể hiện ở Bước 2.

### Tôi có thể tìm thêm thông tin về Aspose.Slides cho Java ở đâu?

Bạn có thể tham khảo [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/) để biết thông tin chi tiết về việc sử dụng thư viện.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}