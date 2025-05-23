---
"description": "Tìm hiểu cách thêm màu vào các điểm dữ liệu trong slide Java bằng Aspose.Slides for Java."
"linktitle": "Thêm màu cho các điểm dữ liệu trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm màu cho các điểm dữ liệu trong Java Slides"
"url": "/vi/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm màu cho các điểm dữ liệu trong Java Slides


## Giới thiệu về Thêm Màu cho Điểm Dữ liệu trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thêm màu vào các điểm dữ liệu trong các slide Java bằng Aspose.Slides for Java. Hướng dẫn từng bước này bao gồm các ví dụ về mã nguồn để giúp bạn thực hiện nhiệm vụ này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Aspose.Slides cho thư viện Java

## Bước 1: Tạo một bài thuyết trình mới

Đầu tiên, chúng ta sẽ tạo một bài thuyết trình mới bằng Aspose.Slides for Java. Bài thuyết trình này sẽ đóng vai trò là vùng chứa cho biểu đồ của chúng ta.

```java
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ Sunburst

Bây giờ, hãy thêm biểu đồ Sunburst vào bài thuyết trình. Chúng ta chỉ định loại biểu đồ, vị trí và kích thước.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Bước 3: Truy cập điểm dữ liệu

Để sửa đổi các điểm dữ liệu trong biểu đồ, chúng ta cần truy cập `IChartDataPointCollection` sự vật.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Bước 4: Tùy chỉnh Điểm Dữ liệu

Trong bước này, chúng ta sẽ tùy chỉnh các điểm dữ liệu cụ thể. Ở đây, chúng ta sẽ thay đổi màu của các điểm dữ liệu và cấu hình cài đặt nhãn.

```java
// Tùy chỉnh điểm dữ liệu 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Tùy chỉnh điểm dữ liệu 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với biểu đồ tùy chỉnh.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã thêm màu thành công vào các điểm dữ liệu cụ thể trong slide Java bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ để thêm màu cho các điểm dữ liệu trong Java Slides

```java
Presentation pres = new Presentation();
try
{
	// Đường dẫn đến thư mục tài liệu.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//CẦN LÀM
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách thêm màu vào các điểm dữ liệu trong các slide Java bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh thêm biểu đồ và bản trình bày của mình dựa trên các yêu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi màu sắc của các điểm dữ liệu khác?

Để thay đổi màu của các điểm dữ liệu khác, bạn có thể làm theo cách tiếp cận tương tự như được hiển thị trong Bước 4. Truy cập điểm dữ liệu bạn muốn tùy chỉnh và sửa đổi cài đặt màu sắc và nhãn của điểm đó.

### Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ không?

Có, bạn có thể tùy chỉnh nhiều khía cạnh khác nhau của biểu đồ, bao gồm phông chữ, nhãn, tiêu đề, v.v. Tham khảo [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/) để biết thêm thông tin chi tiết về các tùy chọn tùy chỉnh.

### Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?

Bạn có thể tìm thêm ví dụ và tài liệu chi tiết về cách sử dụng Aspose.Slides cho Java trên [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/) trang web.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}