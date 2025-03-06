---
title: Tạo biểu đồ radar trong Java Slides
linktitle: Tạo biểu đồ radar trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Biểu đồ Radar trong bản trình bày Java PowerPoint bằng Aspose.Slides cho API Java.
weight: 10
url: /vi/java/chart-creation/radar-chart-creating-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Tạo biểu đồ radar trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ Radar bằng cách sử dụng API Aspose.Slides cho Java. Biểu đồ radar rất hữu ích trong việc hiển thị dữ liệu theo dạng hình tròn, giúp việc so sánh nhiều chuỗi dữ liệu trở nên dễ dàng hơn. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn Java.

## Điều kiện tiên quyết

 Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn đã tích hợp thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Thiết lập bài thuyết trình

Hãy bắt đầu bằng cách thiết lập một bản trình bày PowerPoint mới và thêm một trang trình bày vào đó.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ radar

Tiếp theo, chúng ta sẽ thêm biểu đồ radar vào slide. Chúng tôi sẽ chỉ định vị trí và kích thước của biểu đồ.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Bước 3: Thiết lập dữ liệu biểu đồ

Bây giờ chúng ta sẽ thiết lập dữ liệu biểu đồ. Điều này liên quan đến việc tạo sổ làm việc dữ liệu, thêm danh mục và thêm chuỗi.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Đặt tiêu đề biểu đồ
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Xóa chuỗi và danh mục được tạo mặc định
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Thêm danh mục mới
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Thêm loạt phim mới
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Bước 4: Điền dữ liệu chuỗi

Bây giờ, chúng tôi sẽ điền dữ liệu chuỗi cho biểu đồ radar của mình.

```java
// Điền dữ liệu chuỗi cho Series 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Đặt màu chuỗi
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Điền dữ liệu chuỗi cho Series 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Đặt màu chuỗi
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Bước 5: Tùy chỉnh Trục và Truyền thuyết

Hãy tùy chỉnh trục và chú giải cho biểu đồ radar của chúng ta.

```java
// Đặt vị trí chú giải
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Đặt thuộc tính văn bản trục danh mục
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Đặt thuộc tính văn bản chú giải
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Đặt thuộc tính văn bản trục giá trị
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Cài đặt định dạng số trục giá trị
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Thiết lập biểu đồ giá trị đơn vị chính
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Bước 6: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã tạo bằng biểu đồ radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Đó là nó! Bạn đã tạo thành công biểu đồ radar trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bây giờ bạn có thể tùy chỉnh thêm ví dụ này cho phù hợp với nhu cầu cụ thể của mình.

## Mã nguồn hoàn chỉnh để tạo biểu đồ radar trong Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Truy cập slide đầu tiên
	ISlide sld = pres.getSlides().get_Item(0);
	// Thêm biểu đồ Radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
	int defaultWorksheetIndex = 0;
	// Lấy dữ liệu biểu đồ WorkSheet
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Đặt tiêu đề biểu đồ
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Xóa chuỗi và danh mục được tạo mặc định
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Thêm danh mục mới
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Thêm loạt phim mới
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Hiện đang điền dữ liệu chuỗi
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Đặt màu chuỗi
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//Hiện đang điền dữ liệu chuỗi khác
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Đặt màu chuỗi
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Đặt vị trí chú giải
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Đặt thuộc tính văn bản trục danh mục
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Đặt thuộc tính văn bản chú giải
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Đặt thuộc tính văn bản trục giá trị
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Cài đặt định dạng số trục giá trị
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Thiết lập biểu đồ giá trị đơn vị chính
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Lưu bản trình bày đã tạo
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ radar trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bạn có thể áp dụng các khái niệm này để trực quan hóa và trình bày dữ liệu một cách hiệu quả trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi tiêu đề biểu đồ?

Để thay đổi tiêu đề biểu đồ, hãy sửa đổi dòng sau:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Tôi có thể thêm nhiều chuỗi dữ liệu hơn vào biểu đồ radar không?

Có, bạn có thể thêm nhiều chuỗi dữ liệu hơn bằng cách làm theo các bước trong "Bước 3" và "Bước 4" cho mỗi chuỗi bổ sung mà bạn muốn đưa vào.

### Làm cách nào để tùy chỉnh màu biểu đồ?

 Bạn có thể tùy chỉnh màu của chuỗi bằng cách sửa đổi các đường đặt`SolidFillColor` tài sản cho mỗi chuỗi. Ví dụ:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Làm cách nào để thay đổi nhãn và định dạng trục?

Tham khảo "Bước 5" để tùy chỉnh nhãn và định dạng trục, bao gồm kích thước phông chữ và màu sắc.

### Làm cách nào để lưu biểu đồ sang định dạng tệp khác?

Bạn có thể thay đổi định dạng đầu ra bằng cách sửa đổi phần mở rộng của tệp trong`outPath` biến và sử dụng thích hợp`SaveFormat` . Ví dụ: để lưu dưới dạng PDF, hãy sử dụng`SaveFormat.Pdf`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
