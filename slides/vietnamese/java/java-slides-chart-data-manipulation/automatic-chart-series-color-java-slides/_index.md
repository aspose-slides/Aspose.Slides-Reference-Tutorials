---
"description": "Tìm hiểu cách tạo biểu đồ động với màu chuỗi tự động trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Nâng cao khả năng trực quan hóa dữ liệu của bạn một cách dễ dàng."
"linktitle": "Tự động tô màu chuỗi biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tự động tô màu chuỗi biểu đồ trong Java Slides"
"url": "/vi/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tự động tô màu chuỗi biểu đồ trong Java Slides


## Giới thiệu về Màu chuỗi biểu đồ tự động trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo bản trình bày PowerPoint có biểu đồ bằng Aspose.Slides for Java và thiết lập màu tô tự động cho chuỗi biểu đồ. Màu tô tự động có thể làm cho biểu đồ của bạn hấp dẫn hơn về mặt thị giác và tiết kiệm thời gian cho bạn bằng cách để thư viện chọn màu cho bạn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides for Java trong dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo một bài thuyết trình mới

Đầu tiên, chúng ta sẽ tạo một bản trình bày PowerPoint mới và thêm một slide vào đó.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ vào trang chiếu

Tiếp theo, chúng ta sẽ thêm biểu đồ cột nhóm vào slide. Chúng ta cũng sẽ thiết lập chuỗi đầu tiên để hiển thị giá trị.

```java
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Bước 3: Điền dữ liệu biểu đồ

Bây giờ, chúng ta sẽ điền dữ liệu vào biểu đồ. Chúng ta sẽ bắt đầu bằng cách xóa các chuỗi và danh mục được tạo mặc định, sau đó thêm các chuỗi và danh mục mới.

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa các chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm series mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Bước 4: Điền dữ liệu chuỗi

Chúng tôi sẽ điền dữ liệu cho cả Dòng 1 và Dòng 2.

```java
// Lấy chuỗi biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Lấy chuỗi biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Bước 5: Thiết lập màu tô tự động cho Series

Bây giờ, hãy thiết lập màu tô tự động cho chuỗi biểu đồ. Điều này sẽ khiến thư viện chọn màu cho chúng ta.

```java
// Thiết lập màu tô tự động cho chuỗi
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Bước 6: Lưu bài thuyết trình

Cuối cùng, chúng ta sẽ lưu bản trình bày có biểu đồ vào tệp PowerPoint.

```java
// Lưu bài thuyết trình có biểu đồ
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho màu sắc biểu đồ tự động trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
try
{
	// Truy cập trang chiếu đầu tiên
	ISlide slide = presentation.getSlides().get_Item(0);
	// Thêm biểu đồ với dữ liệu mặc định
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Đặt chuỗi đầu tiên thành Hiển thị giá trị
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
	int defaultWorksheetIndex = 0;
	// Nhận bảng tính dữ liệu biểu đồ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Xóa các chuỗi và danh mục được tạo mặc định
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Thêm series mới
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Thêm danh mục mới
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Lấy chuỗi biểu đồ đầu tiên
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Đang điền dữ liệu chuỗi
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Thiết lập màu tô tự động cho chuỗi
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Lấy chuỗi biểu đồ thứ hai
	series = chart.getChartData().getSeries().get_Item(1);
	// Đang điền dữ liệu chuỗi
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Thiết lập màu tô cho chuỗi
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Lưu bài thuyết trình có biểu đồ
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo bản trình bày PowerPoint có biểu đồ bằng Aspose.Slides for Java và thiết lập màu tô tự động cho chuỗi biểu đồ. Màu tự động có thể tăng cường sức hấp dẫn trực quan của biểu đồ và làm cho bản trình bày của bạn hấp dẫn hơn. Bạn có thể tùy chỉnh thêm biểu đồ khi cần cho các yêu cầu cụ thể của mình.

## Câu hỏi thường gặp

### Làm thế nào để thiết lập màu tô tự động cho chuỗi biểu đồ trong Aspose.Slides cho Java?

Để thiết lập màu tô tự động cho chuỗi biểu đồ trong Aspose.Slides cho Java, hãy sử dụng mã sau:

```java
// Thiết lập màu tô tự động cho chuỗi
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Mã này sẽ cho phép thư viện tự động chọn màu cho chuỗi biểu đồ.

### Tôi có thể tùy chỉnh màu biểu đồ nếu cần không?

Có, bạn có thể tùy chỉnh màu biểu đồ khi cần. Trong ví dụ được cung cấp, chúng tôi đã sử dụng màu tô tự động, nhưng bạn có thể đặt màu cụ thể bằng cách sửa đổi `FillType` Và `SolidFillColor` tính chất của định dạng của loạt phim.

### Làm thế nào tôi có thể thêm chuỗi hoặc danh mục bổ sung vào biểu đồ?

Để thêm các chuỗi hoặc danh mục bổ sung vào biểu đồ, hãy sử dụng `getSeries()` Và `getCategories()` phương pháp của biểu đồ `ChartData` đối tượng. Bạn có thể thêm chuỗi và danh mục mới bằng cách chỉ định dữ liệu và nhãn của chúng.

### Có thể định dạng thêm biểu đồ và nhãn không?

Có, bạn có thể định dạng thêm biểu đồ, chuỗi và nhãn khi cần. Aspose.Slides for Java cung cấp nhiều tùy chọn định dạng cho biểu đồ, bao gồm phông chữ, màu sắc, kiểu dáng, v.v. Bạn có thể khám phá tài liệu để biết thêm chi tiết về các tùy chọn định dạng.

### Tôi có thể tìm thêm thông tin về cách sử dụng Aspose.Slides cho Java ở đâu?

Để biết thêm thông tin và tài liệu chi tiết về Aspose.Slides cho Java, bạn có thể truy cập tài liệu tham khảo [đây](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}