---
title: Đặt màu lát biểu đồ hình tròn tự động trong trang trình bày Java
linktitle: Đặt màu lát biểu đồ hình tròn tự động trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo biểu đồ hình tròn động với các màu lát cắt tự động trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn.
weight: 24
url: /vi/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt màu lát biểu đồ hình tròn tự động trong trang trình bày Java


## Giới thiệu về Thiết lập màu lát biểu đồ hình tròn tự động trong các trang trình bày Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides cho Java và đặt màu lát cắt tự động cho biểu đồ. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải xuống thư viện từ trang web Aspose:[Tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

## Bước 1: Nhập các gói cần thiết

Trước tiên, bạn cần nhập các gói cần thiết từ Aspose.Slides cho Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Bước 2: Tạo bản trình bày PowerPoint

 Khởi tạo`Presentation` lớp để tạo một bản trình bày PowerPoint mới:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Bước 3: Thêm trang trình bày

Truy cập slide đầu tiên của bản trình bày và thêm biểu đồ vào đó với dữ liệu mặc định:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Bước 4: Đặt tiêu đề biểu đồ

Đặt tiêu đề cho biểu đồ:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Bước 5: Định cấu hình dữ liệu biểu đồ

Đặt biểu đồ để hiển thị các giá trị cho chuỗi đầu tiên và định cấu hình dữ liệu biểu đồ:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Bước 6: Thêm danh mục và bộ truyện

Thêm danh mục và chuỗi mới vào biểu đồ:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Bước 7: Điền dữ liệu chuỗi

Điền dữ liệu chuỗi cho biểu đồ hình tròn:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Bước 8: Kích hoạt màu sắc lát cắt đa dạng

Bật các màu lát khác nhau cho biểu đồ hình tròn:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Bước 9: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày vào tệp PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh để thiết lập màu sắc lát cắt biểu đồ hình tròn tự động trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation presentation = new Presentation();
try
{
	// Truy cập slide đầu tiên
	ISlide slides = presentation.getSlides().get_Item(0);
	// Thêm biểu đồ với dữ liệu mặc định
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Đặt tiêu đề biểu đồ
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Đặt chuỗi đầu tiên thành Hiển thị giá trị
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
	int defaultWorksheetIndex = 0;
	// Lấy bảng tính dữ liệu biểu đồ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Xóa chuỗi và danh mục được tạo mặc định
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Thêm danh mục mới
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Thêm loạt phim mới
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Hiện đang điền dữ liệu chuỗi
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Bạn đã tạo thành công biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides cho Java và định cấu hình nó để có các màu lát cắt tự động. Hướng dẫn từng bước này cung cấp cho bạn mã nguồn cần thiết để đạt được điều này. Bạn có thể tùy chỉnh thêm biểu đồ và cách trình bày nếu cần.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể tùy chỉnh màu sắc của từng lát trong biểu đồ hình tròn?

 Để tùy chỉnh màu của từng lát trong biểu đồ hình tròn, bạn có thể sử dụng`getAutomaticSeriesColors` phương pháp để truy xuất bảng màu mặc định và sau đó sửa đổi màu nếu cần. Đây là một ví dụ:

```java
//Lấy bảng màu mặc định
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Sửa đổi màu sắc theo nhu cầu
colors.get_Item(0).setColor(Color.RED); // Đặt màu của lát đầu tiên thành màu đỏ
colors.get_Item(1).setColor(Color.BLUE); // Đặt màu của lát thứ hai thành màu xanh
// Thêm nhiều sửa đổi màu sắc theo yêu cầu
```

### Làm cách nào để thêm chú giải vào biểu đồ hình tròn?

 Để thêm chú giải vào biểu đồ hình tròn, bạn có thể sử dụng`getLegend` phương pháp và cấu hình nó như sau:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Đặt vị trí chú giải
legend.setOverlay(true); // Hiển thị chú giải trên biểu đồ
```

### Tôi có thể thay đổi phông chữ và kiểu tiêu đề không?

Có, bạn có thể thay đổi phông chữ và kiểu tiêu đề. Sử dụng đoạn mã sau để đặt phông chữ và kiểu tiêu đề:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Đặt kích thước phông chữ
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Làm tiêu đề in đậm
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Làm tiêu đề in nghiêng
```

Bạn có thể điều chỉnh kích thước phông chữ, độ đậm và kiểu in nghiêng nếu cần.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
