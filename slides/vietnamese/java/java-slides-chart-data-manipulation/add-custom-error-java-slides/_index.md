---
title: Thêm lỗi tùy chỉnh trong Java Slides
linktitle: Thêm lỗi tùy chỉnh trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm các thanh lỗi tùy chỉnh vào biểu đồ PowerPoint trong Java Slides bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn để hiển thị dữ liệu chính xác.
type: docs
weight: 11
url: /vi/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Giới thiệu về Thêm thanh lỗi tùy chỉnh trong Java Slide bằng Aspose.Slides

Trong hướng dẫn này, bạn sẽ tìm hiểu cách thêm các thanh lỗi tùy chỉnh vào biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Thanh lỗi rất hữu ích để hiển thị tính biến đổi hoặc độ không chắc chắn của các điểm dữ liệu trên biểu đồ.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Thư viện Aspose.Slides cho Java được cài đặt và định cấu hình trong dự án của bạn.
- Một môi trường phát triển Java được thiết lập.

## Bước 1: Tạo một bài thuyết trình trống

Đầu tiên, tạo một bản trình bày PowerPoint trống.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bản trình bày trống
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ bong bóng

Tiếp theo, chúng ta sẽ thêm biểu đồ bong bóng vào bản trình bày.

```java
// Tạo biểu đồ bong bóng
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Bước 3: Thêm thanh lỗi tùy chỉnh

Bây giờ, hãy thêm các thanh lỗi tùy chỉnh vào chuỗi biểu đồ.

```java
// Thêm thanh Lỗi tùy chỉnh và đặt định dạng của chúng
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Bước 4: Đặt dữ liệu thanh lỗi

Trong bước này, chúng ta sẽ truy cập vào các điểm dữ liệu của chuỗi biểu đồ và đặt giá trị thanh lỗi tùy chỉnh cho từng điểm.

```java
// Truy cập các điểm dữ liệu của chuỗi biểu đồ và đặt giá trị thanh lỗi cho từng điểm
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Đặt thanh lỗi cho các điểm chuỗi biểu đồ
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với các thanh lỗi tùy chỉnh.

```java
// Đang lưu bản trình bày
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã thêm thành công các thanh lỗi tùy chỉnh vào biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java.

## Mã nguồn hoàn chỉnh để thêm lỗi tùy chỉnh trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bản trình bày trống
Presentation presentation = new Presentation();
try
{
	// Tạo biểu đồ bong bóng
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Thêm thanh Lỗi tùy chỉnh và đặt định dạng của nó
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Truy cập điểm dữ liệu chuỗi biểu đồ và đặt giá trị thanh lỗi cho từng điểm
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Đặt thanh lỗi cho các điểm chuỗi biểu đồ
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Đang lưu bản trình bày
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn toàn diện này, bạn đã học cách cải thiện bản trình bày PowerPoint của mình bằng cách thêm các thanh lỗi tùy chỉnh vào biểu đồ bằng Aspose.Slides cho Java. Thanh lỗi cung cấp thông tin chi tiết có giá trị về tính biến đổi và độ không chắc chắn của dữ liệu, làm cho biểu đồ của bạn có nhiều thông tin hơn và hấp dẫn trực quan hơn.

## Câu hỏi thường gặp

### Làm cách nào để tùy chỉnh giao diện của thanh lỗi?

 Bạn có thể tùy chỉnh sự xuất hiện của các thanh lỗi bằng cách sửa đổi các thuộc tính của`IErrorBarsFormat` đối tượng, chẳng hạn như kiểu đường, màu đường và chiều rộng thanh lỗi.

### Tôi có thể thêm thanh lỗi vào các loại biểu đồ khác không?

Có, bạn có thể thêm các thanh lỗi vào các loại biểu đồ khác nhau được Aspose.Slides cho Java hỗ trợ, bao gồm biểu đồ thanh, biểu đồ đường và biểu đồ phân tán.

### Làm cách nào để đặt các giá trị thanh lỗi khác nhau cho từng điểm dữ liệu?

Bạn có thể lặp qua các điểm dữ liệu và đặt giá trị thanh lỗi tùy chỉnh cho từng điểm, như minh họa trong đoạn mã trên.

### Có thể ẩn các thanh lỗi cho các điểm dữ liệu cụ thể không?

 Có, bạn có thể kiểm soát khả năng hiển thị của các thanh lỗi cho từng điểm dữ liệu bằng cách đặt`setVisible` tài sản của`IErrorBarsFormat` sự vật.