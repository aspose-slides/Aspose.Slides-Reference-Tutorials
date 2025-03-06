---
title: Thực thể biểu đồ trong Java Slides
linktitle: Thực thể biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo và tùy chỉnh biểu đồ Java Slides bằng Aspose.Slides. Nâng cao bản trình bày của bạn với các thực thể biểu đồ mạnh mẽ.
weight: 13
url: /vi/java/data-manipulation/chart-entities-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về các thực thể biểu đồ trong Java Slides

Biểu đồ là công cụ mạnh mẽ để trực quan hóa dữ liệu trong bài thuyết trình. Cho dù bạn đang tạo báo cáo kinh doanh, thuyết trình học thuật hay bất kỳ dạng nội dung nào khác, biểu đồ đều giúp truyền tải thông tin một cách hiệu quả. Aspose.Slides for Java cung cấp các tính năng mạnh mẽ để làm việc với biểu đồ, khiến nó trở thành lựa chọn phù hợp cho các nhà phát triển Java.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào thế giới của các thực thể biểu đồ, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Đã cài đặt Bộ công cụ phát triển Java (JDK)
- Thư viện Aspose.Slides cho Java được tải xuống và thêm vào dự án của bạn
- Kiến thức cơ bản về lập trình Java

Bây giờ, hãy bắt đầu tạo và tùy chỉnh biểu đồ bằng Aspose.Slides cho Java.

## Bước 1: Tạo bản trình bày

Bước đầu tiên là tạo bản trình bày mới nơi bạn sẽ thêm biểu đồ của mình. Đây là một đoạn mã để tạo một bản trình bày:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Khi bạn đã sẵn sàng cho bản trình bày của mình, đã đến lúc thêm biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm một biểu đồ đường đơn giản có điểm đánh dấu. Đây là cách bạn có thể làm điều đó:

```java
// Truy cập slide đầu tiên
ISlide slide = pres.getSlides().get_Item(0);

// Thêm biểu đồ mẫu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Bước 3: Tùy chỉnh tiêu đề biểu đồ

Biểu đồ được xác định rõ ràng phải có tiêu đề. Hãy đặt tiêu đề cho biểu đồ của chúng tôi:

```java
// Đặt tiêu đề biểu đồ
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Bước 4: Định dạng đường lưới

Bạn có thể định dạng các đường lưới chính và phụ của biểu đồ. Hãy thiết lập một số định dạng cho các đường lưới trục tung:

```java
// Đặt định dạng đường lưới chính cho trục giá trị
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Đặt định dạng đường lưới nhỏ cho trục giá trị
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Bước 5: Tùy chỉnh trục giá trị

Bạn có quyền kiểm soát định dạng số, giá trị tối đa và tối thiểu của trục giá trị. Đây là cách tùy chỉnh nó:

```java
// Cài đặt định dạng số trục giá trị
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Thiết lập biểu đồ giá trị tối đa, tối thiểu
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Bước 6: Thêm tiêu đề trục giá trị

Để làm cho biểu đồ của bạn có nhiều thông tin hơn, bạn có thể thêm tiêu đề vào trục giá trị:

```java
// Đặt tiêu đề trục giá trị
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Bước 7: Định dạng trục danh mục

Trục danh mục, thường biểu thị các danh mục dữ liệu, cũng có thể được tùy chỉnh:

```java
// Đặt định dạng đường lưới chính cho trục Danh mục
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Đặt định dạng đường lưới nhỏ cho trục Danh mục
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Bước 8: Thêm huyền thoại

Chú giải giúp giải thích chuỗi dữ liệu trong biểu đồ của bạn. Hãy tùy chỉnh các truyền thuyết:

```java
// Đặt thuộc tính văn bản chú giải
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Đặt chú thích biểu đồ hiển thị mà không có biểu đồ chồng chéo
chart.getLegend().setOverlay(true);
```

## Bước 9: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày của bạn với biểu đồ:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh cho các thực thể biểu đồ trong các trang trình bày Java

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Khởi tạo bản trình bày// Khởi tạo bản trình bày
Presentation pres = new Presentation();
try
{
	// Truy cập slide đầu tiên
	ISlide slide = pres.getSlides().get_Item(0);
	// Thêm biểu đồ mẫu
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Đặt tiêu đề biểu đồ
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Đặt định dạng đường lưới chính cho trục giá trị
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Đặt định dạng đường lưới nhỏ cho trục giá trị
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Cài đặt định dạng số trục giá trị
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Thiết lập biểu đồ giá trị tối đa, tối thiểu
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Đặt thuộc tính văn bản trục giá trị
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Đặt tiêu đề trục giá trị
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Đặt định dạng đường trục giá trị: Hiện đã lỗi thời
	// Chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Đặt định dạng đường lưới chính cho trục Danh mục
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Đặt định dạng đường lưới nhỏ cho trục Danh mục
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Đặt thuộc tính văn bản trục danh mục
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Đặt tiêu đề danh mục
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Đặt vị trí nhãn trục danh mục
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Cài đặt góc xoay nhãn trục danh mục
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Đặt thuộc tính văn bản chú giải
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Đặt chú thích biểu đồ hiển thị mà không có biểu đồ chồng chéo
	chart.getLegend().setOverlay(true);
	// Vẽ chuỗi đầu tiên trên trục giá trị thứ cấp
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Bảng thiết lập màu tường sau
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//Cài đặt màu vùng Lô
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Lưu bản trình bày
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá thế giới của các thực thể biểu đồ trong Java Slides bằng cách sử dụng Aspose.Slides cho Java. Bạn đã học cách tạo, tùy chỉnh và thao tác với biểu đồ để cải thiện bản trình bày của mình. Biểu đồ không chỉ làm cho dữ liệu của bạn hấp dẫn về mặt trực quan mà còn giúp khán giả hiểu thông tin phức tạp dễ dàng hơn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi loại biểu đồ?

 Để thay đổi loại biểu đồ, hãy sử dụng`chart.setType()` phương pháp và chỉ định loại biểu đồ mong muốn.

### Tôi có thể thêm nhiều chuỗi dữ liệu vào biểu đồ không?

 Có, bạn có thể thêm nhiều chuỗi dữ liệu vào biểu đồ bằng cách sử dụng`chart.getChartData().getSeries().addSeries()` phương pháp.

### Làm cách nào để tùy chỉnh màu biểu đồ?

Bạn có thể tùy chỉnh màu biểu đồ bằng cách đặt định dạng tô cho các thành phần biểu đồ khác nhau, chẳng hạn như đường lưới, tiêu đề và chú giải.

### Tôi có thể tạo biểu đồ 3D không?

 Có, Aspose.Slides for Java hỗ trợ tạo biểu đồ 3D. Bạn có thể thiết lập`ChartType` sang loại biểu đồ 3D để tạo một loại biểu đồ.

### Aspose.Slides cho Java có tương thích với các phiên bản Java mới nhất không?

Có, Aspose.Slides cho Java được cập nhật thường xuyên để hỗ trợ các phiên bản Java mới nhất và cung cấp khả năng tương thích trên nhiều môi trường Java.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
