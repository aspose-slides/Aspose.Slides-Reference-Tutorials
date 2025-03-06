---
title: Đặt Chế độ bố cục trong Java Slides
linktitle: Đặt Chế độ bố cục trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt chế độ bố cục cho các trang trình bày Java bằng Aspose.Slides. Tùy chỉnh vị trí và kích thước biểu đồ trong hướng dẫn từng bước này bằng mã nguồn.
weight: 23
url: /vi/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Chế độ bố cục trong Java Slides


## Giới thiệu về Đặt chế độ bố cục trong Java Slides

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt chế độ bố cục cho biểu đồ trong các trang chiếu Java bằng Aspose.Slides cho Java. Chế độ bố cục xác định vị trí và kích thước của biểu đồ trong trang chiếu.

## Điều kiện tiên quyết

 Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày

Đầu tiên chúng ta cần tạo một bài thuyết trình mới.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Bước 2: Thêm trang trình bày và biểu đồ

Tiếp theo, chúng ta sẽ thêm một slide và biểu đồ vào đó. Trong ví dụ này, chúng tôi sẽ tạo biểu đồ cột theo cụm.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Bước 3: Đặt bố cục biểu đồ

 Bây giờ, hãy thiết lập bố cục cho biểu đồ. Chúng ta sẽ điều chỉnh vị trí và kích thước của biểu đồ trong slide bằng cách sử dụng`setX`, `setY`, `setWidth`, `setHeight` phương pháp. Ngoài ra, chúng tôi sẽ thiết lập`LayoutTargetType` để xác định chế độ bố trí.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Trong ví dụ này, chúng tôi đã đặt biểu đồ có loại mục tiêu bố cục là "Bên trong", nghĩa là biểu đồ sẽ được định vị và có kích thước tương ứng với khu vực bên trong của trang chiếu.

## Bước 4: Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình với cài đặt bố cục biểu đồ.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để đặt chế độ bố cục trong Java Slides

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

 Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt chế độ bố cục cho biểu đồ trong các trang chiếu Java bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ theo yêu cầu cụ thể của mình bằng cách điều chỉnh các giá trị trong phần`setX`, `setY`, `setWidth`, `setHeight` , Và`setLayoutTargetType`phương pháp. Điều này cho phép bạn kiểm soát vị trí của biểu đồ trong trang trình bày của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi chế độ bố cục cho biểu đồ trong Aspose.Slides cho Java?

 Để thay đổi chế độ bố cục cho biểu đồ trong Aspose.Slides cho Java, bạn có thể sử dụng`setLayoutTargetType` phương pháp trên khu vực vẽ của biểu đồ. Bạn có thể đặt nó thành một trong hai`LayoutTargetType.Inner` hoặc`LayoutTargetType.Outer` tùy thuộc vào cách bố trí mong muốn của bạn.

### Tôi có thể tùy chỉnh vị trí và kích thước của biểu đồ trong slide không?

 Có, bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ trong trang chiếu bằng cách sử dụng`setX`, `setY`, `setWidth` , Và`setHeight` các phương pháp trên vùng vẽ của biểu đồ. Điều chỉnh các giá trị này để định vị và kích thước biểu đồ theo yêu cầu của bạn.

### Tôi có thể tìm thêm thông tin về Aspose.Slides cho Java ở đâu?

 Bạn có thể tìm thêm thông tin về Aspose.Slides for Java trong[tài liệu](https://reference.aspose.com/slides/java/). Nó bao gồm các tài liệu tham khảo và ví dụ API chi tiết để giúp bạn làm việc với các trang trình bày và biểu đồ một cách hiệu quả trong Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
