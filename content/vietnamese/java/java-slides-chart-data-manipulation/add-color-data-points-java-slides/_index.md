---
title: Thêm màu vào điểm dữ liệu trong trang trình bày Java
linktitle: Thêm màu vào điểm dữ liệu trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm màu vào điểm dữ liệu trong các trang trình bày Java bằng Aspose.Slides cho Java.
type: docs
weight: 10
url: /vi/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Giới thiệu về Thêm màu vào điểm dữ liệu trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thêm màu vào các điểm dữ liệu trong các trang chiếu Java bằng Aspose.Slides cho Java. Hướng dẫn từng bước này bao gồm các ví dụ về mã nguồn để giúp bạn đạt được nhiệm vụ này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Aspose.Slides cho thư viện Java

## Bước 1: Tạo bản trình bày mới

Đầu tiên, chúng ta sẽ tạo một bản trình bày mới bằng Aspose.Slides cho Java. Bản trình bày này sẽ đóng vai trò là nơi chứa đựng biểu đồ của chúng tôi.

```java
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ Sunburst

Bây giờ, hãy thêm biểu đồ Sunburst vào bản trình bày. Chúng tôi chỉ định loại biểu đồ, vị trí và kích thước.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Bước 3: Truy cập điểm dữ liệu

 Để sửa đổi các điểm dữ liệu trong biểu đồ, chúng ta cần truy cập vào`IChartDataPointCollection` sự vật.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Bước 4: Tùy chỉnh điểm dữ liệu

Trong bước này, chúng tôi sẽ tùy chỉnh các điểm dữ liệu cụ thể. Ở đây, chúng tôi đang thay đổi màu của các điểm dữ liệu và định cấu hình cài đặt nhãn.

```java
//Tùy chỉnh điểm dữ liệu 0
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

Cuối cùng, lưu bài thuyết trình với biểu đồ tùy chỉnh.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã thêm thành công màu vào các điểm dữ liệu cụ thể trong trang chiếu Java bằng Aspose.Slides for Java.

## Mã nguồn hoàn chỉnh để thêm màu vào điểm dữ liệu trong trang trình bày Java

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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//LÀM
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách thêm màu vào điểm dữ liệu trong các trang chiếu Java bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh thêm biểu đồ và bản trình bày dựa trên yêu cầu cụ thể của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu của các điểm dữ liệu khác?

Để thay đổi màu của các điểm dữ liệu khác, bạn có thể thực hiện theo cách tiếp cận tương tự như được hiển thị trong Bước 4. Truy cập vào điểm dữ liệu mà bạn muốn tùy chỉnh và sửa đổi cài đặt màu và nhãn của nó.

### Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ không?

 Có, bạn có thể tùy chỉnh các khía cạnh khác nhau của biểu đồ, bao gồm phông chữ, nhãn, tiêu đề, v.v. Tham khảo đến[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/) để biết các tùy chọn tùy chỉnh chi tiết.

### Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?

Bạn có thể tìm thêm ví dụ và tài liệu chi tiết về cách sử dụng Aspose.Slides cho Java trên[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/) trang mạng.