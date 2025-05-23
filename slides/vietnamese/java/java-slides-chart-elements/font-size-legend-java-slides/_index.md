---
"description": "Cải thiện bài thuyết trình PowerPoint với Aspose.Slides for Java. Tìm hiểu cách tùy chỉnh kích thước phông chữ chú giải và nhiều hơn nữa trong hướng dẫn từng bước của chúng tôi."
"linktitle": "Chú giải cỡ chữ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Chú giải cỡ chữ trong Java Slides"
"url": "/vi/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chú giải cỡ chữ trong Java Slides


## Giới thiệu về Font Size Legend trong Java Slides

Trong hướng dẫn này, bạn sẽ học cách tùy chỉnh kích thước phông chữ của chú giải trong slide PowerPoint bằng Aspose.Slides for Java. Chúng tôi sẽ cung cấp hướng dẫn từng bước và mã nguồn để thực hiện nhiệm vụ này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Khởi tạo bài thuyết trình

Đầu tiên, hãy nhập các lớp cần thiết và khởi tạo bản trình bày PowerPoint của bạn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Thay thế `"Your Document Directory"` với đường dẫn thực tế đến tệp PowerPoint của bạn.

## Bước 2: Thêm biểu đồ

Tiếp theo, chúng ta sẽ thêm biểu đồ vào slide và thiết lập kích thước phông chữ cho chú giải.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Trong mã này, chúng tôi tạo biểu đồ cột nhóm trên trang chiếu đầu tiên và đặt kích thước phông chữ của văn bản chú giải thành 20 điểm. Bạn có thể điều chỉnh `setFontHeight` giá trị để thay đổi kích thước phông chữ khi cần thiết.

## Bước 3: Tùy chỉnh giá trị trục

Bây giờ, chúng ta hãy tùy chỉnh các giá trị trục dọc của biểu đồ.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ở đây, chúng tôi đặt giá trị tối thiểu và tối đa cho trục dọc. Bạn có thể sửa đổi các giá trị theo yêu cầu dữ liệu của mình.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã sửa đổi vào một tệp mới.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Mã này lưu bản trình bày đã sửa đổi dưới dạng "output.pptx" trong thư mục đã chỉ định.

## Mã nguồn đầy đủ cho chú giải kích thước phông chữ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Bạn đã tùy chỉnh thành công kích thước phông chữ của chú giải trong slide Java PowerPoint bằng Aspose.Slides for Java. Bạn có thể khám phá thêm các khả năng của Aspose.Slides để tạo các bài thuyết trình tương tác và hấp dẫn về mặt hình ảnh.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi kích thước phông chữ của văn bản chú giải trong biểu đồ?

Để thay đổi kích thước phông chữ của văn bản chú giải trong biểu đồ, bạn có thể sử dụng mã sau:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Trong mã này, chúng tôi tạo một biểu đồ và đặt kích thước phông chữ của văn bản chú giải thành 20 điểm. Bạn có thể điều chỉnh `setFontHeight` giá trị để thay đổi kích thước phông chữ.

### Tôi có thể tùy chỉnh các thuộc tính khác của chú giải trong biểu đồ không?

Có, bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của chú giải trong biểu đồ bằng Aspose.Slides. Một số thuộc tính phổ biến mà bạn có thể tùy chỉnh bao gồm định dạng văn bản, vị trí, khả năng hiển thị, v.v. Ví dụ: để thay đổi vị trí của chú giải, bạn có thể sử dụng:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Mã này thiết lập chú giải xuất hiện ở cuối biểu đồ. Khám phá tài liệu Aspose.Slides để biết thêm các tùy chọn tùy chỉnh.

### Làm thế nào để thiết lập giá trị tối thiểu và tối đa cho trục dọc trong biểu đồ?

Để đặt giá trị tối thiểu và tối đa cho trục dọc trong biểu đồ, bạn có thể sử dụng mã sau:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ở đây, chúng tôi vô hiệu hóa tính năng tự động thay đổi tỷ lệ trục và chỉ định giá trị tối thiểu và tối đa cho trục dọc. Điều chỉnh các giá trị khi cần thiết cho dữ liệu biểu đồ của bạn.

### Tôi có thể tìm thêm thông tin và tài liệu về Aspose.Slides ở đâu?

Bạn có thể tìm thấy tài liệu toàn diện và tham chiếu API cho Aspose.Slides for Java trên trang web tài liệu Aspose. Truy cập [đây](https://reference.aspose.com/slides/java/) để biết thông tin chi tiết về việc sử dụng thư viện.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}