---
title: Thuộc tính phông chữ cho biểu đồ trong Java Slides
linktitle: Thuộc tính phông chữ cho biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Nâng cao thuộc tính phông chữ biểu đồ trong các trang trình bày Java với Aspose.Slides cho Java. Tùy chỉnh kích thước phông chữ, kiểu dáng và màu sắc để có bài thuyết trình ấn tượng.
weight: 11
url: /vi/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thuộc tính phông chữ cho biểu đồ trong Java Slides


## Giới thiệu về Thuộc tính phông chữ cho biểu đồ trong Java Slides

Hướng dẫn này sẽ hướng dẫn bạn cách đặt thuộc tính phông chữ cho biểu đồ trong Java Slides bằng Aspose.Slides. Bạn có thể tùy chỉnh kích thước phông chữ và hình thức của văn bản biểu đồ để nâng cao sức hấp dẫn trực quan cho bản trình bày của bạn.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã tích hợp API Aspose.Slides cho Java vào dự án của mình. Nếu chưa có, bạn có thể tải xuống từ[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày

Đầu tiên, tạo một bản trình bày mới bằng mã sau:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Bây giờ, hãy thêm biểu đồ cột được nhóm vào bản trình bày của bạn:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Ở đây, chúng tôi đang thêm biểu đồ cột được nhóm vào trang chiếu đầu tiên tại tọa độ (100, 100) với chiều rộng 500 đơn vị và chiều cao 400 đơn vị.

## Bước 3: Tùy chỉnh thuộc tính phông chữ

Tiếp theo, chúng ta sẽ tùy chỉnh thuộc tính phông chữ của biểu đồ. Trong ví dụ này, chúng tôi đang đặt cỡ chữ thành 20 cho tất cả văn bản biểu đồ:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Mã này đặt kích thước phông chữ thành 20 điểm cho tất cả văn bản trong biểu đồ.

## Bước 4: Hiển thị nhãn dữ liệu

Bạn cũng có thể hiển thị nhãn dữ liệu trên biểu đồ bằng mã sau:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Dòng mã này kích hoạt nhãn dữ liệu cho chuỗi đầu tiên trong biểu đồ, hiển thị các giá trị trên các cột biểu đồ.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với các thuộc tính phông chữ biểu đồ tùy chỉnh của bạn:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Mã này sẽ lưu bản trình bày vào thư mục được chỉ định với tên tệp "FontPropertiesForChart.pptx."

## Mã nguồn hoàn chỉnh cho thuộc tính phông chữ cho biểu đồ trong Java Slides

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

Trong hướng dẫn này, bạn đã học cách tùy chỉnh thuộc tính phông chữ cho biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể áp dụng những kỹ thuật này để cải thiện hình thức của biểu đồ và bản trình bày của mình. Khám phá thêm các lựa chọn trong[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/).

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu phông chữ?

 Để thay đổi màu phông chữ cho văn bản biểu đồ, hãy sử dụng`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , thay thế`Color.RED` với màu sắc mong muốn.

### Tôi có thể thay đổi kiểu phông chữ (đậm, nghiêng, v.v.) không?

 Có, bạn có thể thay đổi kiểu phông chữ. Sử dụng`chart.getTextFormat().getPortionFormat().setFontBold(true);` để làm đậm phông chữ. Tương tự, bạn có thể sử dụng`setFontItalic(true)` để làm cho nó in nghiêng.

### Làm cách nào để tùy chỉnh thuộc tính phông chữ cho các thành phần biểu đồ cụ thể?

Để tùy chỉnh thuộc tính phông chữ cho các thành phần biểu đồ cụ thể, chẳng hạn như nhãn trục hoặc văn bản chú giải, bạn có thể truy cập các thành phần đó và đặt thuộc tính phông chữ của chúng bằng các phương pháp tương tự như được hiển thị ở trên.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
