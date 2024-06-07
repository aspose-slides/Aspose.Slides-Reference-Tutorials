---
title: Màu chuỗi biểu đồ tự động trong các trang trình bày Java
linktitle: Màu chuỗi biểu đồ tự động trong các trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo biểu đồ động với chuỗi màu tự động trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Tăng cường trực quan hóa dữ liệu của bạn một cách dễ dàng.
type: docs
weight: 14
url: /vi/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Giới thiệu về Màu chuỗi biểu đồ tự động trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo bản trình bày PowerPoint có biểu đồ bằng Aspose.Slides cho Java và đặt màu tô tự động cho chuỗi biểu đồ. Màu tô tự động có thể làm cho biểu đồ của bạn hấp dẫn hơn về mặt trực quan và giúp bạn tiết kiệm thời gian bằng cách cho phép thư viện chọn màu cho bạn.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt thư viện Aspose.Slides for Java trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Tạo bản trình bày mới

Đầu tiên, chúng ta sẽ tạo một bản trình bày PowerPoint mới và thêm một slide vào đó.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ vào slide

Tiếp theo, chúng ta sẽ thêm biểu đồ cột được nhóm vào trang chiếu. Chúng tôi cũng sẽ đặt chuỗi đầu tiên hiển thị các giá trị.

```java
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Bước 3: Điền dữ liệu biểu đồ

Bây giờ, chúng ta sẽ điền dữ liệu vào biểu đồ. Chúng ta sẽ bắt đầu bằng cách xóa chuỗi và danh mục được tạo mặc định, sau đó thêm chuỗi và danh mục mới.

```java
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm loạt phim mới
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Bước 4: Điền dữ liệu chuỗi

Chúng tôi sẽ điền dữ liệu chuỗi cho cả Series 1 và Series 2.

```java
// Lấy loạt biểu đồ đầu tiên
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Lấy loạt biểu đồ thứ hai
series = chart.getChartData().getSeries().get_Item(1);
//Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Bước 5: Đặt màu tô tự động cho chuỗi

Bây giờ, hãy đặt màu tô tự động cho chuỗi biểu đồ. Điều này sẽ làm cho thư viện chọn màu cho chúng ta.

```java
// Đặt màu tô tự động cho chuỗi
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Bước 6: Lưu bài thuyết trình

Cuối cùng, chúng ta sẽ lưu bài thuyết trình có biểu đồ vào file PowerPoint.

```java
// Lưu bài thuyết trình bằng biểu đồ
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh cho màu chuỗi biểu đồ tự động trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
try
{
	// Truy cập slide đầu tiên
	ISlide slide = presentation.getSlides().get_Item(0);
	// Thêm biểu đồ với dữ liệu mặc định
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Đặt chuỗi đầu tiên thành Hiển thị giá trị
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
	int defaultWorksheetIndex = 0;
	// Lấy bảng tính dữ liệu biểu đồ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Xóa chuỗi và danh mục được tạo mặc định
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Thêm loạt phim mới
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Thêm danh mục mới
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Lấy loạt biểu đồ đầu tiên
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//Hiện đang điền dữ liệu chuỗi
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Đặt màu tô tự động cho chuỗi
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Lấy loạt biểu đồ thứ hai
	series = chart.getChartData().getSeries().get_Item(1);
	//Hiện đang điền dữ liệu chuỗi
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//Đặt màu tô cho chuỗi
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Lưu bài thuyết trình bằng biểu đồ
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo bản trình bày PowerPoint có biểu đồ bằng Aspose.Slides cho Java và đặt màu tô tự động cho chuỗi biểu đồ. Màu sắc tự động có thể nâng cao sự hấp dẫn trực quan của biểu đồ và làm cho bản trình bày của bạn hấp dẫn hơn. Bạn có thể tùy chỉnh thêm biểu đồ nếu cần cho các yêu cầu cụ thể của mình.

## Câu hỏi thường gặp

### Làm cách nào để đặt màu tô tự động cho chuỗi biểu đồ trong Aspose.Slides cho Java?

Để đặt màu tô tự động cho chuỗi biểu đồ trong Aspose.Slides cho Java, hãy sử dụng mã sau:

```java
// Đặt màu tô tự động cho chuỗi
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Mã này sẽ cho phép thư viện tự động chọn màu cho chuỗi biểu đồ.

### Tôi có thể tùy chỉnh màu biểu đồ nếu cần không?

 Có, bạn có thể tùy chỉnh màu biểu đồ nếu cần. Trong ví dụ được cung cấp, chúng tôi đã sử dụng màu tô tự động nhưng bạn có thể đặt các màu cụ thể bằng cách sửa đổi`FillType` Và`SolidFillColor` thuộc tính của định dạng của chuỗi.

### Làm cách nào tôi có thể thêm chuỗi hoặc danh mục bổ sung vào biểu đồ?

Để thêm chuỗi hoặc danh mục bổ sung vào biểu đồ, hãy sử dụng`getSeries()` Và`getCategories()` các phương pháp biểu đồ`ChartData` sự vật. Bạn có thể thêm chuỗi và danh mục mới bằng cách chỉ định dữ liệu và nhãn của chúng.

### Có thể định dạng thêm biểu đồ và nhãn không?

Có, bạn có thể định dạng thêm biểu đồ, chuỗi và nhãn nếu cần. Aspose.Slides for Java cung cấp các tùy chọn định dạng mở rộng cho biểu đồ, bao gồm phông chữ, màu sắc, kiểu, v.v. Bạn có thể khám phá tài liệu để biết thêm chi tiết về các tùy chọn định dạng.

### Tôi có thể tìm thêm thông tin về cách làm việc với Aspose.Slides cho Java ở đâu?

 Để biết thêm thông tin và tài liệu chi tiết về Aspose.Slides cho Java, bạn có thể truy cập tài liệu tham khảo[đây](https://reference.aspose.com/slides/java/).