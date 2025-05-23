---
"description": "Tìm hiểu cách thiết lập tùy chọn chú giải tùy chỉnh trong Java Slides bằng Aspose.Slides for Java. Tùy chỉnh vị trí và kích thước chú giải trong biểu đồ PowerPoint của bạn."
"linktitle": "Thiết lập tùy chọn tùy chỉnh chú giải trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thiết lập tùy chọn tùy chỉnh chú giải trong Java Slides"
"url": "/vi/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập tùy chọn tùy chỉnh chú giải trong Java Slides


## Giới thiệu về Tùy chọn tùy chỉnh Set Legend trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tùy chỉnh các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bạn có thể sửa đổi vị trí, kích thước và các thuộc tính khác của chú giải để phù hợp với nhu cầu trình bày của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Đã cài đặt Aspose.Slides cho Java API.
- Thiết lập môi trường phát triển Java.

## Bước 1: Nhập các lớp cần thiết:

```java
// Nhập Aspose.Slides cho các lớp Java
import com.aspose.slides.*;
```

## Bước 2: Chỉ định đường dẫn đến thư mục tài liệu của bạn:

```java
String dataDir = "Your Document Directory";
```

## Bước 3: Tạo một phiên bản của `Presentation` lớp học:

```java
Presentation presentation = new Presentation();
```

## Bước 4: Thêm slide vào bài thuyết trình:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Bước 5: Thêm biểu đồ cột nhóm vào trang chiếu:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Bước 6. Thiết lập Thuộc tính chú giải:

- Đặt vị trí X của chú giải (tương ứng với chiều rộng biểu đồ):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Đặt vị trí Y của chú giải (so với chiều cao biểu đồ):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Đặt chiều rộng của chú giải (tương ứng với chiều rộng của biểu đồ):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Đặt chiều cao của chú giải (tương ứng với chiều cao của biểu đồ):

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

Vậy là xong! Bạn đã tùy chỉnh thành công các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ cho tùy chọn tùy chỉnh chú giải tập hợp trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
try
{
	// Lấy tham chiếu của slide
	ISlide slide = presentation.getSlides().get_Item(0);
	// Thêm biểu đồ cột nhóm vào trang chiếu
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Đặt Thuộc tính Chú giải
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Ghi bản trình bày vào đĩa
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tùy chỉnh các thuộc tính chú giải của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bạn có thể sửa đổi vị trí, kích thước và các thuộc tính khác của chú giải để tạo ra các bản trình bày hấp dẫn về mặt hình ảnh và nhiều thông tin.

## Câu hỏi thường gặp

## Làm thế nào để tôi có thể thay đổi vị trí của chú giải?

Để thay đổi vị trí của chú giải, hãy sử dụng `setX` Và `setY` phương pháp của đối tượng chú giải. Các giá trị được chỉ định theo chiều rộng và chiều cao của biểu đồ.

## Làm thế nào để tôi có thể điều chỉnh kích thước của chú giải?

Bạn có thể điều chỉnh kích thước của chú giải bằng cách sử dụng `setWidth` Và `setHeight` phương pháp của đối tượng chú giải. Các giá trị này cũng liên quan đến chiều rộng và chiều cao của biểu đồ.

## Tôi có thể tùy chỉnh các thuộc tính chú giải khác không?

Có, bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của chú giải, chẳng hạn như kiểu phông chữ, đường viền, màu nền, v.v. Khám phá tài liệu Aspose.Slides để biết thông tin chi tiết về cách tùy chỉnh chú giải thêm.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}