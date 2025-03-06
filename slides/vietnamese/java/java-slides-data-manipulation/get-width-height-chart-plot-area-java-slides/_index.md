---
title: Nhận chiều rộng và chiều cao từ vùng biểu đồ trong trang trình bày Java
linktitle: Nhận chiều rộng và chiều cao từ vùng biểu đồ trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách truy xuất kích thước vùng biểu đồ trong Trang trình bày Java bằng Aspose.Slides cho Java. Nâng cao kỹ năng tự động hóa PowerPoint của bạn.
weight: 21
url: /vi/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu

Biểu đồ là một cách mạnh mẽ để trực quan hóa dữ liệu trong bản trình bày PowerPoint. Đôi khi, bạn có thể cần biết kích thước vùng vẽ của biểu đồ vì nhiều lý do khác nhau, chẳng hạn như thay đổi kích thước hoặc định vị lại các thành phần trong biểu đồ. Hướng dẫn này sẽ trình bày cách lấy chiều rộng và chiều cao của vùng ô bằng cách sử dụng Java và Aspose.Slides cho Java.

## Điều kiện tiên quyết

 Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides cho Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ trang web Aspose[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Thiết lập môi trường

Đảm bảo rằng bạn đã thêm thư viện Aspose.Slides for Java vào dự án Java của mình. Bạn có thể thực hiện việc này bằng cách đưa thư viện vào phần phụ thuộc của dự án hoặc bằng cách thêm tệp JAR theo cách thủ công.

## Bước 2: Tạo bản trình bày PowerPoint

Hãy bắt đầu bằng cách tạo bản trình bày PowerPoint và thêm trang trình bày vào đó. Điều này sẽ đóng vai trò là nơi chứa biểu đồ của chúng tôi.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu của bạn.

## Bước 3: Thêm biểu đồ

Bây giờ, hãy thêm biểu đồ cột được nhóm vào trang chiếu. Chúng tôi cũng sẽ xác nhận bố cục biểu đồ.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Mã này tạo biểu đồ cột được nhóm tại vị trí (100, 100) với kích thước (500, 350).

## Bước 4: Lấy kích thước khu vực lô đất

Để lấy chiều rộng và chiều cao của vùng vẽ biểu đồ, chúng ta có thể sử dụng đoạn mã sau:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Bây giờ, các biến`x`, `y`, `w` , Và`h` chứa các giá trị tương ứng cho tọa độ X, tọa độ Y, chiều rộng và chiều cao của khu vực ô.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình kèm theo biểu đồ.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Đảm bảo thay thế`"Chart_out.pptx"` với tên tệp đầu ra mong muốn của bạn.

## Mã nguồn hoàn chỉnh để lấy chiều rộng và chiều cao từ vùng biểu đồ trong trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Lưu bài thuyết trình bằng biểu đồ
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong bài viết này, chúng tôi đã đề cập đến cách lấy chiều rộng và chiều cao của vùng vẽ biểu đồ trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Thông tin này có thể có giá trị khi bạn cần điều chỉnh linh hoạt bố cục biểu đồ trong bản trình bày PowerPoint.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể thay đổi loại biểu đồ thành một loại biểu đồ khác ngoài các cột được nhóm?

 Bạn có thể thay đổi loại biểu đồ bằng cách thay thế`ChartType.ClusteredColumn` với cách liệt kê loại biểu đồ mong muốn, chẳng hạn như`ChartType.Line` hoặc`ChartType.Pie`.

### Tôi có thể sửa đổi các thuộc tính khác của biểu đồ không?

Có, bạn có thể sửa đổi các thuộc tính khác nhau của biểu đồ, chẳng hạn như dữ liệu, nhãn và định dạng bằng cách sử dụng API Aspose.Slides cho Java. Tham khảo tài liệu để biết thêm chi tiết.

### Aspose.Slides cho Java có phù hợp với việc tự động hóa PowerPoint chuyên nghiệp không?

Có, Aspose.Slides for Java là một thư viện mạnh mẽ để tự động hóa các tác vụ PowerPoint trong ứng dụng Java. Nó cung cấp các tính năng toàn diện để làm việc với bản trình bày, trang trình bày, hình dạng, biểu đồ, v.v.

### Làm cách nào tôi có thể tìm hiểu thêm về Aspose.Slides cho Java?

 Bạn có thể tìm thấy tài liệu và ví dụ mở rộng trên trang tài liệu Aspose.Slides for Java[đây](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
