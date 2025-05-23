---
"description": "Tìm hiểu cách thêm thanh lỗi tùy chỉnh vào biểu đồ PowerPoint trong Java Slides bằng Aspose.Slides. Hướng dẫn từng bước với mã nguồn để trực quan hóa dữ liệu chính xác."
"linktitle": "Thêm lỗi tùy chỉnh vào Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm lỗi tùy chỉnh vào Java Slides"
"url": "/vi/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm lỗi tùy chỉnh vào Java Slides


## Giới thiệu về cách thêm thanh lỗi tùy chỉnh vào Java Slides bằng Aspose.Slides

Trong hướng dẫn này, bạn sẽ học cách thêm thanh lỗi tùy chỉnh vào biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Thanh lỗi hữu ích để hiển thị độ biến thiên hoặc độ không chắc chắn trong các điểm dữ liệu trên biểu đồ.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- Thư viện Aspose.Slides for Java được cài đặt và cấu hình trong dự án của bạn.
- Thiết lập môi trường phát triển Java.

## Bước 1: Tạo một bài thuyết trình trống

Đầu tiên, hãy tạo một bài thuyết trình PowerPoint trống.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bài thuyết trình trống
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ bong bóng

Tiếp theo, chúng ta sẽ thêm biểu đồ bong bóng vào bài thuyết trình.

```java
// Tạo biểu đồ bong bóng
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Bước 3: Thêm Thanh Lỗi Tùy Chỉnh

Bây giờ, chúng ta hãy thêm các thanh lỗi tùy chỉnh vào chuỗi biểu đồ.

```java
// Thêm thanh Lỗi tùy chỉnh và thiết lập định dạng của chúng
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Bước 4: Thiết lập dữ liệu thanh lỗi

Ở bước này, chúng ta sẽ truy cập các điểm dữ liệu của chuỗi biểu đồ và thiết lập các giá trị thanh lỗi tùy chỉnh cho từng điểm.

```java
// Truy cập các điểm dữ liệu chuỗi biểu đồ và thiết lập giá trị thanh lỗi cho từng điểm
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Thiết lập thanh lỗi cho các điểm chuỗi biểu đồ
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Bước 5: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày với thanh lỗi tùy chỉnh.

```java
// Lưu bài thuyết trình
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã thêm thành công thanh lỗi tùy chỉnh vào biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides for Java.

## Mã nguồn đầy đủ để thêm lỗi tùy chỉnh vào Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo bài thuyết trình trống
Presentation presentation = new Presentation();
try
{
	// Tạo biểu đồ bong bóng
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Thêm thanh Lỗi tùy chỉnh và thiết lập định dạng của nó
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Truy cập điểm dữ liệu chuỗi biểu đồ và thiết lập giá trị thanh lỗi cho từng điểm
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Thiết lập thanh lỗi cho các điểm chuỗi biểu đồ
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Lưu bài thuyết trình
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn toàn diện này, bạn đã học cách cải thiện bài thuyết trình PowerPoint của mình bằng cách thêm thanh lỗi tùy chỉnh vào biểu đồ bằng Aspose.Slides for Java. Thanh lỗi cung cấp thông tin chi tiết có giá trị về tính biến động và sự không chắc chắn của dữ liệu, giúp biểu đồ của bạn có nhiều thông tin hơn và hấp dẫn hơn về mặt trực quan.

## Câu hỏi thường gặp

### Làm thế nào để tùy chỉnh giao diện của thanh lỗi?

Bạn có thể tùy chỉnh giao diện của thanh lỗi bằng cách sửa đổi các thuộc tính của `IErrorBarsFormat` đối tượng, chẳng hạn như kiểu đường kẻ, màu đường kẻ và chiều rộng thanh lỗi.

### Tôi có thể thêm thanh lỗi vào các loại biểu đồ khác không?

Có, bạn có thể thêm thanh lỗi vào nhiều loại biểu đồ khác nhau được Aspose.Slides for Java hỗ trợ, bao gồm biểu đồ thanh, biểu đồ đường và biểu đồ phân tán.

### Làm thế nào để thiết lập các giá trị thanh lỗi khác nhau cho mỗi điểm dữ liệu?

Bạn có thể lặp qua các điểm dữ liệu và đặt giá trị thanh lỗi tùy chỉnh cho từng điểm, như được hiển thị trong đoạn mã trên.

### Có thể ẩn thanh lỗi cho các điểm dữ liệu cụ thể không?

Có, bạn có thể kiểm soát khả năng hiển thị của các thanh lỗi cho từng điểm dữ liệu bằng cách thiết lập `setVisible` tài sản của `IErrorBarsFormat` sự vật.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}