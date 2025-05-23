---
"description": "Cải thiện bài thuyết trình PowerPoint với kiểu phông chữ, kích thước và màu sắc tùy chỉnh cho từng chú giải trong Java Slides bằng Aspose.Slides for Java."
"linktitle": "Thuộc tính phông chữ cho từng chú giải trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thuộc tính phông chữ cho từng chú giải trong Java Slides"
"url": "/vi/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thuộc tính phông chữ cho từng chú giải trong Java Slides


## Giới thiệu về Thuộc tính Phông chữ cho Chú giải Riêng lẻ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách thiết lập thuộc tính phông chữ cho từng chú giải trong Java Slides bằng Aspose.Slides for Java. Bằng cách tùy chỉnh thuộc tính phông chữ, bạn có thể làm cho chú giải của mình hấp dẫn hơn về mặt thị giác và nhiều thông tin hơn trong các bài thuyết trình PowerPoint của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã tích hợp thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải xuống từ [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

## Bước 1: Khởi tạo Trình bày và Thêm Biểu đồ

Trước tiên, chúng ta hãy bắt đầu bằng cách khởi tạo một bản trình bày PowerPoint và thêm biểu đồ vào đó. Trong ví dụ này, chúng ta sẽ sử dụng biểu đồ cột nhóm làm minh họa.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Phần còn lại của mã ở đây
} finally {
    if (pres != null) pres.dispose();
}
```

Thay thế `"Your Document Directory"` với thư mục thực tế nơi lưu trữ tài liệu PowerPoint của bạn.

## Bước 2: Tùy chỉnh Thuộc tính Phông chữ cho Chú giải

Bây giờ, hãy tùy chỉnh các thuộc tính phông chữ cho một mục chú giải riêng lẻ trong biểu đồ. Trong ví dụ này, chúng tôi đang nhắm mục tiêu mục chú giải thứ hai (chỉ mục 1), nhưng bạn có thể điều chỉnh chỉ mục theo yêu cầu cụ thể của mình.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Sau đây là chức năng của từng dòng mã:

- `get_Item(1)` lấy mục chú giải thứ hai (chỉ mục 1). Bạn có thể thay đổi chỉ mục để nhắm mục tiêu đến mục chú giải khác.
- `setFontBold(NullableBool.True)` đặt phông chữ thành chữ đậm.
- `setFontHeight(20)` đặt kích thước phông chữ là 20 điểm.
- `setFontItalic(NullableBool.True)` đặt phông chữ thành chữ nghiêng.
- `setFillType(FillType.Solid)` chỉ rõ rằng văn bản mục chú giải phải có màu đặc.
- `getSolidFillColor().setColor(Color.BLUE)` đặt màu tô thành màu xanh. Bạn có thể thay thế `Color.BLUE` với màu sắc bạn mong muốn.

## Bước 3: Lưu bản trình bày đã sửa đổi

Cuối cùng, hãy lưu bản trình bày đã sửa đổi vào một tệp mới để giữ nguyên những thay đổi của bạn.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Thay thế `"output.pptx"` với tên tập tin đầu ra mà bạn muốn.

Vậy là xong! Bạn đã tùy chỉnh thành công các thuộc tính phông chữ cho một mục chú giải riêng lẻ trong bản trình bày Java Slides bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ cho các thuộc tính phông chữ cho từng chú giải trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tùy chỉnh các thuộc tính phông chữ cho từng chú giải trong Java Slides bằng Aspose.Slides for Java. Bằng cách điều chỉnh kiểu phông chữ, kích thước và màu sắc, bạn có thể tăng cường tính hấp dẫn trực quan và độ rõ nét của bản trình bày PowerPoint.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi màu phông chữ?

Để thay đổi màu phông chữ, hãy sử dụng `tf.getPortionFormat().getFontColor().setColor(yourColor)` thay vì thay đổi màu tô. Thay thế `yourColor` với màu chữ mong muốn.

### Làm thế nào để tôi có thể sửa đổi các thuộc tính chú giải khác?

Bạn có thể sửa đổi nhiều thuộc tính khác của chú giải, chẳng hạn như vị trí, kích thước và định dạng. Tham khảo tài liệu Aspose.Slides for Java để biết thông tin chi tiết về cách làm việc với chú giải.

### Tôi có thể áp dụng những thay đổi này cho nhiều mục chú giải không?

Có, bạn có thể lặp qua các mục chú giải và áp dụng những thay đổi này cho nhiều mục bằng cách điều chỉnh chỉ mục trong `get_Item(index)` và lặp lại mã tùy chỉnh.

Hãy nhớ loại bỏ đối tượng trình bày khi bạn hoàn tất việc giải phóng tài nguyên:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}