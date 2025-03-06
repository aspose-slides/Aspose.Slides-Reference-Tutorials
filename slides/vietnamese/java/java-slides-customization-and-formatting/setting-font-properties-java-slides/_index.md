---
title: Đặt thuộc tính phông chữ trong Java Slides
linktitle: Đặt thuộc tính phông chữ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt thuộc tính phông chữ trong các trang chiếu Java bằng Aspose.Slides cho Java. Hướng dẫn từng bước này bao gồm các ví dụ về mã và Câu hỏi thường gặp.
weight: 15
url: /vi/java/customization-and-formatting/setting-font-properties-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Đặt thuộc tính phông chữ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt thuộc tính phông chữ cho văn bản trong các trang chiếu Java bằng Aspose.Slides cho Java. Các thuộc tính phông chữ như độ đậm và kích thước phông chữ có thể được tùy chỉnh để nâng cao hình thức của trang trình bày của bạn.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã thêm thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Khởi tạo bản trình bày

 Trước tiên, bạn cần khởi tạo đối tượng trình bày bằng cách tải tệp PowerPoint hiện có. Thay thế`"Your Document Directory"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Bước 2: Thêm biểu đồ

Trong ví dụ này, chúng ta sẽ làm việc với biểu đồ trên slide đầu tiên. Bạn có thể thay đổi chỉ mục slide theo nhu cầu của mình. Chúng tôi sẽ thêm biểu đồ cột được nhóm và kích hoạt bảng dữ liệu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## Bước 3: Tùy chỉnh thuộc tính phông chữ

Bây giờ, hãy tùy chỉnh thuộc tính phông chữ của bảng dữ liệu biểu đồ. Chúng ta sẽ cài đặt font chữ đậm và điều chỉnh độ cao (size) của font chữ.

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: Dòng này đặt phông chữ ở dạng đậm.
- `setFontHeight(20)`: Dòng này đặt chiều cao phông chữ thành 20 điểm. Bạn có thể điều chỉnh giá trị này nếu cần.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã sửa đổi vào một tệp mới. Bạn có thể chỉ định định dạng đầu ra; trong trường hợp này, chúng tôi đang lưu nó dưới dạng tệp PPTX.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để đặt thuộc tính phông chữ trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt thuộc tính phông chữ cho văn bản trong các trang chiếu Java bằng Aspose.Slides cho Java. Bạn có thể áp dụng những kỹ thuật này để nâng cao hình thức của văn bản trong bản trình bày PowerPoint của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu phông chữ?

 Để thay đổi màu chữ, hãy sử dụng`setFontColor` phương pháp và chỉ định màu sắc mong muốn. Ví dụ:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### Tôi có thể thay đổi phông chữ cho văn bản khác trong slide không?

Có, bạn có thể thay đổi phông chữ cho các thành phần văn bản khác trong trang chiếu, chẳng hạn như tiêu đề và nhãn. Sử dụng các đối tượng và phương thức thích hợp để truy cập và tùy chỉnh các thuộc tính phông chữ cho các thành phần văn bản cụ thể.

### Làm cách nào để đặt kiểu phông chữ nghiêng?

 Để đặt kiểu phông chữ thành nghiêng, hãy sử dụng`setFontItalic` phương pháp:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 Điều chỉnh`NullableBool.True` tham số nếu cần để bật hoặc tắt kiểu in nghiêng.

### Làm cách nào để thay đổi phông chữ cho nhãn dữ liệu trong biểu đồ?

Để thay đổi phông chữ cho nhãn dữ liệu trong biểu đồ, bạn cần truy cập định dạng văn bản nhãn dữ liệu bằng các phương pháp thích hợp. Ví dụ:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // Thay đổi chỉ mục khi cần thiết
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

Mã này đặt phông chữ của nhãn dữ liệu trong chuỗi đầu tiên thành đậm.

### Làm cách nào để thay đổi phông chữ cho một phần văn bản cụ thể?

 Nếu bạn muốn thay đổi phông chữ cho một phần văn bản cụ thể trong thành phần văn bản, bạn có thể sử dụng`PortionFormat` lớp học. Truy cập phần bạn muốn sửa đổi và sau đó đặt thuộc tính phông chữ mong muốn.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // Thay đổi chỉ mục khi cần thiết
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // Thay đổi chỉ mục khi cần thiết
IPortion portion = paragraph.getPortions().get_Item(0); // Thay đổi chỉ mục khi cần thiết

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

Mã này đặt phông chữ của phần văn bản đầu tiên trong hình thành in đậm và điều chỉnh chiều cao phông chữ.

### Làm cách nào để áp dụng thay đổi phông chữ cho tất cả các trang chiếu trong bản trình bày?

Để áp dụng thay đổi phông chữ cho tất cả các trang chiếu trong bản trình bày, bạn có thể lặp qua các trang chiếu và điều chỉnh thuộc tính phông chữ nếu cần. Sử dụng vòng lặp để truy cập từng trang chiếu và các thành phần văn bản bên trong chúng, sau đó tùy chỉnh các thuộc tính phông chữ.

```java
for (ISlide slide : pres.getSlides()) {
    // Truy cập và tùy chỉnh thuộc tính phông chữ của thành phần văn bản tại đây
}
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
