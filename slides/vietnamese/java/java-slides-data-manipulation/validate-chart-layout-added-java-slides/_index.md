---
"description": "Xác thực bố cục biểu đồ chính trong PowerPoint với Aspose.Slides cho Java. Học cách thao tác biểu đồ theo chương trình để có bài thuyết trình ấn tượng."
"linktitle": "Xác thực Bố cục Biểu đồ được Thêm vào Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Xác thực Bố cục Biểu đồ được Thêm vào Java Slides"
"url": "/vi/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Xác thực Bố cục Biểu đồ được Thêm vào Java Slides


## Giới thiệu về Xác thực Bố cục Biểu đồ trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách xác thực bố cục biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Thư viện này cho phép bạn làm việc với các bản trình bày PowerPoint theo chương trình, giúp bạn dễ dàng thao tác và xác thực nhiều thành phần khác nhau, bao gồm cả biểu đồ.

## Bước 1: Khởi tạo bài thuyết trình

Đầu tiên, chúng ta cần khởi tạo một đối tượng trình bày và tải một bản trình bày PowerPoint hiện có. Thay thế `"Your Document Directory"` với đường dẫn thực tế đến tệp trình bày của bạn (`test.pptx` trong ví dụ này).

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Bước 2: Thêm biểu đồ

Tiếp theo, chúng ta sẽ thêm một biểu đồ vào bài thuyết trình. Trong ví dụ này, chúng ta sẽ thêm một biểu đồ cột nhóm, nhưng bạn có thể thay đổi `ChartType` khi cần thiết.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Bước 3: Xác thực bố cục biểu đồ

Bây giờ, chúng ta sẽ xác thực bố cục biểu đồ bằng cách sử dụng `validateChartLayout()` phương pháp. Điều này đảm bảo rằng biểu đồ được trình bày đúng cách trong slide.

```java
chart.validateChartLayout();
```

## Bước 4: Lấy lại vị trí và kích thước biểu đồ

Sau khi xác thực bố cục biểu đồ, bạn có thể muốn lấy thông tin về vị trí và kích thước của biểu đồ. Chúng ta có thể lấy tọa độ X và Y thực tế, cũng như chiều rộng và chiều cao của vùng vẽ biểu đồ.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, đừng quên lưu bản trình bày đã sửa đổi. Trong ví dụ này, chúng tôi lưu nó dưới dạng `Result.pptx`nhưng bạn có thể chỉ định tên tệp khác nếu cần.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để xác thực bố cục biểu đồ được thêm vào Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Lưu bài thuyết trình
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã đi sâu vào thế giới làm việc với biểu đồ trong các bài thuyết trình PowerPoint bằng Aspose.Slides for Java. Chúng tôi đã đề cập đến các bước thiết yếu để xác thực bố cục biểu đồ, lấy vị trí và kích thước của biểu đồ và lưu bản trình bày đã sửa đổi. Sau đây là tóm tắt nhanh:

## Câu hỏi thường gặp

### Làm thế nào để thay đổi loại biểu đồ?

Để thay đổi loại biểu đồ, chỉ cần thay thế `ChartType.ClusteredColumn` với loại biểu đồ mong muốn trong `addChart()` phương pháp.

### Tôi có thể tùy chỉnh dữ liệu biểu đồ không?

Có, bạn có thể tùy chỉnh dữ liệu biểu đồ bằng cách thêm và sửa đổi chuỗi dữ liệu, danh mục và giá trị. Tham khảo tài liệu Aspose.Slides để biết thêm chi tiết.

### Tôi phải làm sao nếu muốn sửa đổi các thuộc tính khác của biểu đồ?

Bạn có thể truy cập nhiều thuộc tính biểu đồ khác nhau và tùy chỉnh chúng theo yêu cầu của mình. Khám phá tài liệu Aspose.Slides để biết thông tin toàn diện về thao tác biểu đồ.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}