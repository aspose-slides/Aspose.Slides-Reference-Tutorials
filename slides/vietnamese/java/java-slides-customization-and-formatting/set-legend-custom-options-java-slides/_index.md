---
title: Đặt tùy chọn tùy chỉnh chú giải trong Java Slides
linktitle: Đặt tùy chọn tùy chỉnh chú giải trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt tùy chọn chú giải tùy chỉnh trong Java Slides bằng Aspose.Slides for Java. Tùy chỉnh vị trí và kích thước chú giải trong biểu đồ PowerPoint của bạn.
weight: 14
url: /vi/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Đặt tùy chọn tùy chỉnh chú giải trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tùy chỉnh các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bạn có thể sửa đổi vị trí, kích thước của chú giải và các thuộc tính khác cho phù hợp với nhu cầu trình bày của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Aspose.Slides cho API Java đã được cài đặt.
- Môi trường phát triển Java được thiết lập.

## Bước 1: Nhập các lớp cần thiết:

```java
// Nhập Aspose.Slides cho các lớp Java
import com.aspose.slides.*;
```

## Bước 2: Chỉ định đường dẫn đến thư mục tài liệu của bạn:

```java
String dataDir = "Your Document Directory";
```

##  Bước 3: Tạo một thể hiện của`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Bước 4: Thêm slide vào bài thuyết trình:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Bước 5: Thêm biểu đồ cột nhóm vào slide:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Bước 6. Đặt thuộc tính chú giải:

- Đặt vị trí X của chú giải (so với chiều rộng biểu đồ):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Đặt vị trí Y của chú giải (so với chiều cao biểu đồ):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Đặt chiều rộng của chú giải (so với chiều rộng biểu đồ):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Đặt chiều cao của chú giải (so với chiều cao biểu đồ):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Bước 7: Lưu bài thuyết trình vào đĩa:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Đó là nó! Bạn đã tùy chỉnh thành công các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java.

## Mã nguồn hoàn chỉnh cho các tùy chọn tùy chỉnh chú giải trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
try
{
	// Nhận tài liệu tham khảo của slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Thêm biểu đồ cột được nhóm trên trang chiếu
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Đặt thuộc tính chú giải
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Ghi bài thuyết trình vào đĩa
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách tùy chỉnh các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bạn có thể sửa đổi vị trí, kích thước của chú giải và các thuộc tính khác để tạo ra các bản trình bày đầy thông tin và hấp dẫn về mặt trực quan.

## Câu hỏi thường gặp

## Làm cách nào để thay đổi vị trí của huyền thoại?

 Để thay đổi vị trí của chú giải, hãy sử dụng`setX` Và`setY` các phương thức của đối tượng huyền thoại. Các giá trị được chỉ định tương ứng với chiều rộng và chiều cao của biểu đồ.

## Làm cách nào để điều chỉnh kích thước của chú giải?

 Bạn có thể điều chỉnh kích thước của chú giải bằng cách sử dụng`setWidth` Và`setHeight` các phương thức của đối tượng huyền thoại. Các giá trị này cũng liên quan đến chiều rộng và chiều cao của biểu đồ.

## Tôi có thể tùy chỉnh các thuộc tính chú giải khác không?

Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của chú giải, chẳng hạn như kiểu phông chữ, đường viền, màu nền, v.v. Khám phá tài liệu Aspose.Slides để biết thêm thông tin chi tiết về cách tùy chỉnh chú giải.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
