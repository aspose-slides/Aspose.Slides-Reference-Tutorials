---
"description": "Tìm hiểu cách lấy kích thước vùng vẽ biểu đồ trong Java Slides bằng Aspose.Slides for Java. Nâng cao kỹ năng tự động hóa PowerPoint của bạn."
"linktitle": "Lấy chiều rộng và chiều cao từ vùng vẽ biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lấy chiều rộng và chiều cao từ vùng vẽ biểu đồ trong Java Slides"
"url": "/vi/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lấy chiều rộng và chiều cao từ vùng vẽ biểu đồ trong Java Slides


## Giới thiệu

Biểu đồ là một cách mạnh mẽ để trực quan hóa dữ liệu trong các bài thuyết trình PowerPoint. Đôi khi, bạn có thể cần biết kích thước của vùng vẽ biểu đồ vì nhiều lý do, chẳng hạn như thay đổi kích thước hoặc định vị lại các thành phần trong biểu đồ. Hướng dẫn này sẽ trình bày cách lấy chiều rộng và chiều cao của vùng vẽ bằng Java và Aspose.Slides for Java.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ trang web Aspose [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Thiết lập môi trường

Đảm bảo rằng bạn đã thêm thư viện Aspose.Slides for Java vào dự án Java của mình. Bạn có thể thực hiện việc này bằng cách đưa thư viện vào các phụ thuộc của dự án hoặc bằng cách thêm tệp JAR theo cách thủ công.

## Bước 2: Tạo bài thuyết trình PowerPoint

Hãy bắt đầu bằng cách tạo một bài thuyết trình PowerPoint và thêm một slide vào đó. Đây sẽ là nơi chứa biểu đồ của chúng ta.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Thay thế `"Your Document Directory"` với đường dẫn đến thư mục tài liệu của bạn.

## Bước 3: Thêm biểu đồ

Bây giờ, chúng ta hãy thêm biểu đồ cột nhóm vào slide. Chúng ta cũng sẽ xác thực bố cục biểu đồ.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Mã này tạo biểu đồ cột cụm ở vị trí (100, 100) với kích thước (500, 350).

## Bước 4: Lấy kích thước diện tích lô đất

Để lấy chiều rộng và chiều cao của vùng vẽ biểu đồ, chúng ta có thể sử dụng đoạn mã sau:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Bây giờ, các biến `x`, `y`, `w`, Và `h` chứa các giá trị tương ứng cho tọa độ X, tọa độ Y, chiều rộng và chiều cao của vùng vẽ.

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày có biểu đồ.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Hãy chắc chắn thay thế `"Chart_out.pptx"` với tên tập tin đầu ra bạn mong muốn.

## Mã nguồn đầy đủ để lấy chiều rộng và chiều cao từ vùng vẽ biểu đồ trong Java Slides

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
	// Lưu bài thuyết trình có biểu đồ
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong bài viết này, chúng tôi đã đề cập đến cách lấy chiều rộng và chiều cao của vùng vẽ biểu đồ trong Java Slides bằng cách sử dụng Aspose.Slides for Java API. Thông tin này có thể hữu ích khi bạn cần điều chỉnh động bố cục biểu đồ của mình trong bản trình bày PowerPoint.

## Câu hỏi thường gặp

### Làm thế nào tôi có thể thay đổi loại biểu đồ thành loại biểu đồ khác ngoài biểu đồ cột cụm?

Bạn có thể thay đổi loại biểu đồ bằng cách thay thế `ChartType.ClusteredColumn` với loại biểu đồ mong muốn được liệt kê, chẳng hạn như `ChartType.Line` hoặc `ChartType.Pie`.

### Tôi có thể sửa đổi các thuộc tính khác của biểu đồ không?

Có, bạn có thể sửa đổi nhiều thuộc tính khác nhau của biểu đồ, chẳng hạn như dữ liệu, nhãn và định dạng, bằng cách sử dụng Aspose.Slides for Java API. Tham khảo tài liệu để biết thêm chi tiết.

### Aspose.Slides for Java có phù hợp để tự động hóa PowerPoint chuyên nghiệp không?

Có, Aspose.Slides for Java là một thư viện mạnh mẽ để tự động hóa các tác vụ PowerPoint trong các ứng dụng Java. Nó cung cấp các tính năng toàn diện để làm việc với các bài thuyết trình, slide, hình dạng, biểu đồ, v.v.

### Tôi có thể tìm hiểu thêm về Aspose.Slides cho Java bằng cách nào?

Bạn có thể tìm thấy tài liệu và ví dụ mở rộng trên trang tài liệu Aspose.Slides for Java [đây](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}