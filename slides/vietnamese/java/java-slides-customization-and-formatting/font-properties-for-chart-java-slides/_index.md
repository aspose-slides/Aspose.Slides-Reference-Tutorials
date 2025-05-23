---
"description": "Cải thiện Thuộc tính Phông chữ Biểu đồ trong Java Slides với Aspose.Slides cho Java. Tùy chỉnh kích thước phông chữ, kiểu dáng và màu sắc cho các bài thuyết trình có sức ảnh hưởng."
"linktitle": "Thuộc tính phông chữ cho biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thuộc tính phông chữ cho biểu đồ trong Java Slides"
"url": "/vi/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thuộc tính phông chữ cho biểu đồ trong Java Slides


## Giới thiệu về Thuộc tính Phông chữ cho Biểu đồ trong Java Slides

Hướng dẫn này sẽ hướng dẫn bạn cách thiết lập thuộc tính phông chữ cho biểu đồ trong Java Slides bằng Aspose.Slides. Bạn có thể tùy chỉnh kích thước phông chữ và giao diện của văn bản biểu đồ để tăng tính hấp dẫn trực quan cho bài thuyết trình của mình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã tích hợp Aspose.Slides for Java API vào dự án của mình. Nếu chưa, bạn có thể tải xuống từ [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

## Bước 1: Tạo bài thuyết trình

Đầu tiên, hãy tạo một bài thuyết trình mới bằng đoạn mã sau:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Bây giờ, chúng ta hãy thêm biểu đồ cột nhóm vào bài thuyết trình của bạn:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Ở đây, chúng ta sẽ thêm biểu đồ cột nhóm vào trang chiếu đầu tiên tại tọa độ (100, 100) với chiều rộng là 500 đơn vị và chiều cao là 400 đơn vị.

## Bước 3: Tùy chỉnh Thuộc tính Phông chữ

Tiếp theo, chúng ta sẽ tùy chỉnh các thuộc tính phông chữ của biểu đồ. Trong ví dụ này, chúng ta đang đặt kích thước phông chữ là 20 cho tất cả văn bản biểu đồ:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Mã này đặt kích thước phông chữ là 20 điểm cho toàn bộ văn bản trong biểu đồ.

## Bước 4: Hiển thị nhãn dữ liệu

Bạn cũng có thể hiển thị nhãn dữ liệu trên biểu đồ bằng cách sử dụng mã sau:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Dòng mã này cho phép dán nhãn dữ liệu cho chuỗi đầu tiên trong biểu đồ, hiển thị giá trị trên các cột biểu đồ.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với thuộc tính phông chữ biểu đồ tùy chỉnh của bạn:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Mã này sẽ lưu bản trình bày vào thư mục được chỉ định với tên tệp là "FontPropertiesForChart.pptx".

## Mã nguồn đầy đủ cho các thuộc tính phông chữ cho biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tùy chỉnh các thuộc tính phông chữ cho biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể áp dụng các kỹ thuật này để cải thiện giao diện của biểu đồ và bản trình bày của mình. Khám phá thêm các tùy chọn trong [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi màu phông chữ?

Để thay đổi màu phông chữ cho văn bản biểu đồ, hãy sử dụng `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, thay thế `Color.RED` với màu sắc mong muốn.

### Tôi có thể thay đổi kiểu phông chữ (in đậm, in nghiêng, v.v.) không?

Có, bạn có thể thay đổi kiểu phông chữ. Sử dụng `chart.getTextFormat().getPortionFormat().setFontBold(true);` để làm cho phông chữ đậm. Tương tự như vậy, bạn có thể sử dụng `setFontItalic(true)` để làm cho nó nghiêng.

### Làm thế nào để tùy chỉnh thuộc tính phông chữ cho các thành phần biểu đồ cụ thể?

Để tùy chỉnh thuộc tính phông chữ cho các thành phần biểu đồ cụ thể, chẳng hạn như nhãn trục hoặc văn bản chú giải, bạn có thể truy cập các thành phần đó và đặt thuộc tính phông chữ của chúng bằng các phương pháp tương tự như được hiển thị ở trên.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}