---
"description": "Tìm hiểu cách tạo Biểu đồ Radar trong bài thuyết trình PowerPoint bằng Java bằng Aspose.Slides for Java API."
"linktitle": "Tạo biểu đồ radar trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tạo biểu đồ radar trong Java Slides"
"url": "/vi/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tạo biểu đồ radar trong Java Slides


## Giới thiệu về việc tạo biểu đồ radar trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Biểu đồ Radar bằng API Aspose.Slides for Java. Biểu đồ Radar hữu ích để trực quan hóa dữ liệu theo dạng hình tròn, giúp dễ dàng so sánh nhiều chuỗi dữ liệu. Chúng tôi sẽ cung cấp hướng dẫn từng bước cùng với mã nguồn Java.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn đã tích hợp thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Thiết lập bài thuyết trình

Hãy bắt đầu bằng cách thiết lập một bản trình bày PowerPoint mới và thêm một slide vào đó.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ radar

Tiếp theo, chúng ta sẽ thêm biểu đồ radar vào slide. Chúng ta sẽ chỉ định vị trí và kích thước của biểu đồ.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Bước 3: Thiết lập dữ liệu biểu đồ

Bây giờ chúng ta sẽ thiết lập dữ liệu biểu đồ. Điều này bao gồm việc tạo một bảng tính dữ liệu, thêm danh mục và thêm chuỗi.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Đặt tiêu đề biểu đồ
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Xóa các chuỗi và danh mục được tạo mặc định
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Thêm danh mục mới
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Thêm series mới
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Bước 4: Điền dữ liệu chuỗi

Bây giờ, chúng ta sẽ điền dữ liệu chuỗi vào biểu đồ radar.

```java
// Điền dữ liệu cho Series 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Đặt màu cho loạt phim
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Điền dữ liệu cho Series 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Đặt màu cho loạt phim
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Bước 5: Tùy chỉnh Trục và Chú giải

Hãy tùy chỉnh trục và chú thích cho biểu đồ radar của chúng ta.

```java
// Đặt vị trí chú giải
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Thiết lập Thuộc tính Văn bản Trục Thể loại
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Thiết lập Thuộc tính Văn bản Huyền thoại
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Thiết lập Thuộc tính Văn bản Trục Giá trị
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Thiết lập định dạng số trục giá trị
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Thiết lập biểu đồ giá trị đơn vị chính
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Bước 6: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày đã tạo với biểu đồ radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Vậy là xong! Bạn đã tạo thành công biểu đồ radar trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bây giờ bạn có thể tùy chỉnh ví dụ này thêm nữa để phù hợp với nhu cầu cụ thể của mình.

## Mã nguồn đầy đủ để tạo biểu đồ radar trong Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Truy cập trang chiếu đầu tiên
	ISlide sld = pres.getSlides().get_Item(0);
	// Thêm biểu đồ Radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
	int defaultWorksheetIndex = 0;
	// Lấy dữ liệu biểu đồ WorkSheet
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Đặt tiêu đề biểu đồ
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Xóa các chuỗi và danh mục được tạo mặc định
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Thêm danh mục mới
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Thêm series mới
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Đang điền dữ liệu chuỗi
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Đặt màu cho loạt phim
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Bây giờ đang điền dữ liệu cho một loạt khác
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Đặt màu cho loạt phim
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Đặt vị trí chú giải
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Thiết lập Thuộc tính Văn bản Trục Thể loại
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Thiết lập Thuộc tính Văn bản Huyền thoại
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Thiết lập Thuộc tính Văn bản Trục Giá trị
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Thiết lập định dạng số trục giá trị
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Thiết lập biểu đồ giá trị đơn vị chính
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Lưu bài thuyết trình đã tạo
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tạo biểu đồ radar trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bạn có thể áp dụng các khái niệm này để trực quan hóa và trình bày dữ liệu của mình một cách hiệu quả trong các ứng dụng Java.

## Câu hỏi thường gặp

### Làm thế nào để tôi có thể thay đổi tiêu đề biểu đồ?

Để thay đổi tiêu đề biểu đồ, hãy sửa đổi dòng sau:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Tôi có thể thêm nhiều chuỗi dữ liệu hơn vào biểu đồ radar không?

Có, bạn có thể thêm nhiều chuỗi dữ liệu hơn bằng cách làm theo các bước trong "Bước 3" và "Bước 4" cho mỗi chuỗi bổ sung mà bạn muốn đưa vào.

### Làm thế nào để tùy chỉnh màu biểu đồ?

Bạn có thể tùy chỉnh màu sắc của chuỗi bằng cách sửa đổi các dòng thiết lập `SolidFillColor` thuộc tính cho mỗi chuỗi. Ví dụ:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Làm thế nào để thay đổi nhãn trục và định dạng?

Tham khảo "Bước 5" để tùy chỉnh nhãn trục và định dạng, bao gồm kích thước phông chữ và màu sắc.

### Làm thế nào để lưu biểu đồ sang định dạng tệp khác?

Bạn có thể thay đổi định dạng đầu ra bằng cách sửa đổi phần mở rộng tệp trong `outPath` biến và sử dụng thích hợp `SaveFormat`. Ví dụ, để lưu dưới dạng PDF, hãy sử dụng `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}