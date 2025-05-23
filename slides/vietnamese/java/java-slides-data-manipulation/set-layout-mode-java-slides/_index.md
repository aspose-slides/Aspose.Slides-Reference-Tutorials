---
"description": "Tìm hiểu cách thiết lập chế độ bố trí cho slide Java bằng Aspose.Slides. Tùy chỉnh vị trí và kích thước biểu đồ trong hướng dẫn từng bước này với mã nguồn."
"linktitle": "Thiết lập chế độ bố trí trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thiết lập chế độ bố trí trong Java Slides"
"url": "/vi/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập chế độ bố trí trong Java Slides


## Giới thiệu về Set Layout Mode trong Java Slides

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thiết lập chế độ bố trí cho biểu đồ trong Java slide bằng Aspose.Slides for Java. Chế độ bố trí xác định vị trí và kích thước của biểu đồ trong slide.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bài thuyết trình

Đầu tiên, chúng ta cần tạo một bài thuyết trình mới.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Bước 2: Thêm Slide và Biểu đồ

Tiếp theo, chúng ta sẽ thêm một slide và một biểu đồ vào đó. Trong ví dụ này, chúng ta sẽ tạo một biểu đồ cột nhóm.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Bước 3: Thiết lập Bố cục Biểu đồ

Bây giờ, chúng ta hãy thiết lập bố cục cho biểu đồ. Chúng ta sẽ điều chỉnh vị trí và kích thước của biểu đồ trong slide bằng cách sử dụng `setX`, `setY`, `setWidth`, `setHeight` phương pháp. Ngoài ra, chúng tôi sẽ thiết lập `LayoutTargetType` để xác định chế độ bố trí.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Trong ví dụ này, chúng tôi đã thiết lập biểu đồ để có loại mục tiêu bố cục là "Bên trong", nghĩa là biểu đồ sẽ được định vị và định kích thước theo vùng bên trong của trang chiếu.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, hãy lưu bản trình bày với cài đặt bố cục biểu đồ.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho chế độ thiết lập bố cục trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thiết lập chế độ bố trí cho biểu đồ trong Java slides bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ theo yêu cầu cụ thể của mình bằng cách điều chỉnh các giá trị trong `setX`, `setY`, `setWidth`, `setHeight`, Và `setLayoutTargetType` phương pháp. Điều này cho phép bạn kiểm soát vị trí của biểu đồ trong slide của mình.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi chế độ bố cục cho biểu đồ trong Aspose.Slides cho Java?

Để thay đổi chế độ bố trí cho biểu đồ trong Aspose.Slides cho Java, bạn có thể sử dụng `setLayoutTargetType` phương pháp trên vùng vẽ biểu đồ. Bạn có thể đặt nó thành `LayoutTargetType.Inner` hoặc `LayoutTargetType.Outer` tùy thuộc vào bố cục bạn mong muốn.

### Tôi có thể tùy chỉnh vị trí và kích thước của biểu đồ trong slide không?

Có, bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ trong slide bằng cách sử dụng `setX`, `setY`, `setWidth`, Và `setHeight` phương pháp trên vùng vẽ biểu đồ. Điều chỉnh các giá trị này để định vị và kích thước biểu đồ theo yêu cầu của bạn.

### Tôi có thể tìm thêm thông tin về Aspose.Slides cho Java ở đâu?

Bạn có thể tìm thêm thông tin về Aspose.Slides cho Java trong [tài liệu](https://reference.aspose.com/slides/java/). Nó bao gồm các ví dụ và tham chiếu API chi tiết để giúp bạn làm việc với các slide và biểu đồ hiệu quả trong Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}