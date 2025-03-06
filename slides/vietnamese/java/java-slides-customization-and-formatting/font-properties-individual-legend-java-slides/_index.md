---
title: Thuộc tính phông chữ cho chú thích riêng lẻ trong trang trình bày Java
linktitle: Thuộc tính phông chữ cho chú thích riêng lẻ trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Nâng cao bản trình bày PowerPoint với các kiểu, kích thước và màu sắc phông chữ tùy chỉnh cho từng chú giải trong Java Slides bằng Aspose.Slides for Java.
weight: 12
url: /vi/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thuộc tính phông chữ cho chú thích riêng lẻ trong trang trình bày Java


## Giới thiệu về Thuộc tính phông chữ cho từng chú thích trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt thuộc tính phông chữ cho một chú giải riêng lẻ trong Java Slides bằng Aspose.Slides cho Java. Bằng cách tùy chỉnh các thuộc tính phông chữ, bạn có thể làm cho chú giải của mình hấp dẫn trực quan hơn và mang tính thông tin hơn trong bản trình bày PowerPoint của mình.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã tích hợp thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải nó xuống từ[Aspose.Slides cho Tài liệu Java](https://reference.aspose.com/slides/java/).

## Bước 1: Khởi tạo bản trình bày và thêm biểu đồ

Trước tiên, hãy bắt đầu bằng cách khởi tạo bản trình bày PowerPoint và thêm biểu đồ vào đó. Trong ví dụ này, chúng tôi sẽ sử dụng biểu đồ cột nhóm làm minh họa.

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

 Thay thế`"Your Document Directory"` với thư mục thực nơi chứa tài liệu PowerPoint của bạn.

## Bước 2: Tùy chỉnh thuộc tính phông chữ cho chú giải

Bây giờ, hãy tùy chỉnh thuộc tính phông chữ cho từng mục chú thích trong biểu đồ. Trong ví dụ này, chúng tôi đang nhắm mục tiêu mục chú giải thứ hai (chỉ mục 1), nhưng bạn có thể điều chỉnh chỉ mục theo yêu cầu cụ thể của mình.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Đây là chức năng của từng dòng mã:

- `get_Item(1)` truy xuất mục chú giải thứ hai (chỉ mục 1). Bạn có thể thay đổi chỉ mục để nhắm mục tiêu một mục chú giải khác.
- `setFontBold(NullableBool.True)` đặt phông chữ thành đậm.
- `setFontHeight(20)` đặt kích thước phông chữ thành 20 điểm.
- `setFontItalic(NullableBool.True)` đặt phông chữ thành nghiêng.
- `setFillType(FillType.Solid)` chỉ định rằng văn bản mục nhập chú giải phải được điền đầy đủ.
- `getSolidFillColor().setColor(Color.BLUE)` đặt màu tô thành màu xanh lam. Bạn có thể thay thế`Color.BLUE` với màu sắc bạn mong muốn.

## Bước 3: Lưu bản trình bày đã sửa đổi

Cuối cùng, lưu bản trình bày đã sửa đổi vào một tệp mới để giữ nguyên các thay đổi của bạn.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Thay thế`"output.pptx"` với tên tệp đầu ra ưa thích của bạn.

Đó là nó! Bạn đã tùy chỉnh thành công các thuộc tính phông chữ cho một mục chú giải riêng lẻ trong bản trình bày Java Slides bằng Aspose.Slides for Java.

## Mã nguồn hoàn chỉnh cho các thuộc tính phông chữ cho từng chú thích trong các trang trình bày Java

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

Trong hướng dẫn này, chúng ta đã tìm hiểu cách tùy chỉnh các thuộc tính phông chữ cho một chú giải riêng lẻ trong Java Slides bằng cách sử dụng Aspose.Slides cho Java. Bằng cách điều chỉnh kiểu phông chữ, kích thước và màu sắc, bạn có thể nâng cao sự hấp dẫn trực quan và độ rõ ràng của bản trình bày PowerPoint của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu phông chữ?

 Để thay đổi màu phông chữ, hãy sử dụng`tf.getPortionFormat().getFontColor().setColor(yourColor)` thay vì thay đổi màu tô. Thay thế`yourColor` với màu chữ mong muốn.

### Làm cách nào để sửa đổi các thuộc tính chú giải khác?

Bạn có thể sửa đổi nhiều thuộc tính khác của chú giải, chẳng hạn như vị trí, kích thước và định dạng. Tham khảo tài liệu Aspose.Slides for Java để biết thông tin chi tiết về cách làm việc với chú giải.

### Tôi có thể áp dụng những thay đổi này cho nhiều mục chú thích không?

 Có, bạn có thể lặp qua các mục chú thích và áp dụng những thay đổi này cho nhiều mục bằng cách điều chỉnh chỉ mục trong`get_Item(index)` và lặp lại mã tùy chỉnh.

Hãy nhớ loại bỏ đối tượng trình bày khi bạn hoàn tất việc giải phóng tài nguyên:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
