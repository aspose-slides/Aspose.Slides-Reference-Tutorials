---
"description": "Học cách tạo và tùy chỉnh biểu đồ Java Slides bằng Aspose.Slides. Nâng cao bài thuyết trình của bạn bằng các thực thể biểu đồ mạnh mẽ."
"linktitle": "Biểu đồ thực thể trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ thực thể trong Java Slides"
"url": "/vi/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ thực thể trong Java Slides


## Giới thiệu về Biểu đồ thực thể trong Java Slides

Biểu đồ là công cụ mạnh mẽ để trực quan hóa dữ liệu trong các bài thuyết trình. Cho dù bạn đang tạo báo cáo kinh doanh, bài thuyết trình học thuật hay bất kỳ hình thức nội dung nào khác, biểu đồ đều giúp truyền tải thông tin hiệu quả. Aspose.Slides for Java cung cấp các tính năng mạnh mẽ để làm việc với biểu đồ, khiến nó trở thành lựa chọn hàng đầu cho các nhà phát triển Java.

## Điều kiện tiên quyết

Trước khi đi sâu vào thế giới của các thực thể biểu đồ, hãy đảm bảo bạn đã có đủ các điều kiện tiên quyết sau:

- Đã cài đặt Java Development Kit (JDK)
- Thư viện Aspose.Slides for Java đã được tải xuống và thêm vào dự án của bạn
- Kiến thức cơ bản về lập trình Java

Bây giờ, chúng ta hãy bắt đầu tạo và tùy chỉnh biểu đồ bằng Aspose.Slides cho Java.

## Bước 1: Tạo bài thuyết trình

Bước đầu tiên là tạo một bài thuyết trình mới, trong đó bạn sẽ thêm biểu đồ của mình. Sau đây là một đoạn mã để tạo bài thuyết trình:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ

Khi bạn đã chuẩn bị xong bài thuyết trình, đã đến lúc thêm biểu đồ. Trong ví dụ này, chúng ta sẽ thêm một biểu đồ đường đơn giản có đánh dấu. Sau đây là cách bạn có thể thực hiện:

```java
// Truy cập vào slide đầu tiên
ISlide slide = pres.getSlides().get_Item(0);

// Thêm biểu đồ mẫu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Bước 3: Tùy chỉnh tiêu đề biểu đồ

Một biểu đồ được định nghĩa rõ ràng phải có tiêu đề. Chúng ta hãy đặt tiêu đề cho biểu đồ của mình:

```java
// Thiết lập tiêu đề biểu đồ
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Bước 4: Định dạng đường lưới

Bạn có thể định dạng các đường lưới chính và phụ của biểu đồ. Hãy thiết lập một số định dạng cho các đường lưới trục dọc:

```java
// Thiết lập định dạng đường lưới chính cho trục giá trị
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Thiết lập định dạng đường lưới phụ cho trục giá trị
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Bước 5: Tùy chỉnh Trục Giá trị

Bạn có thể kiểm soát định dạng số, giá trị tối đa và tối thiểu của trục giá trị. Sau đây là cách tùy chỉnh:

```java
// Thiết lập định dạng số trục giá trị
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

## Bước 6: Thêm Tiêu đề Trục Giá trị

Để biểu đồ của bạn cung cấp nhiều thông tin hơn, bạn có thể thêm tiêu đề vào trục giá trị:

```java
// Thiết lập giá trị tiêu đề trục
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Bước 7: Định dạng trục danh mục

Trục danh mục, thường biểu diễn các danh mục dữ liệu, cũng có thể được tùy chỉnh:

```java
// Thiết lập định dạng đường lưới chính cho trục Danh mục
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Thiết lập định dạng đường lưới phụ cho trục Danh mục
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Bước 8: Thêm chú thích

Chú giải giúp giải thích chuỗi dữ liệu trong biểu đồ của bạn. Hãy tùy chỉnh chú giải:

```java
// Thiết lập Thuộc tính Văn bản Huyền thoại
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Đặt hiển thị chú giải biểu đồ mà không chồng chéo biểu đồ
chart.getLegend().setOverlay(true);
```

## Bước 9: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình có biểu đồ:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho các thực thể biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu thư mục đó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Khởi tạo bản trình bày// Khởi tạo bản trình bày
Presentation pres = new Presentation();
try
{
	// Truy cập vào slide đầu tiên
	ISlide slide = pres.getSlides().get_Item(0);
	// Thêm biểu đồ mẫu
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Thiết lập tiêu đề biểu đồ
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Thiết lập định dạng đường lưới chính cho trục giá trị
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Thiết lập định dạng đường lưới phụ cho trục giá trị
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Thiết lập định dạng số trục giá trị
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
	// Thiết lập Thuộc tính Văn bản Trục Giá trị
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Thiết lập giá trị tiêu đề trục
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Thiết lập giá trị trục định dạng đường: Hiện đã lỗi thời
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Thiết lập định dạng đường lưới chính cho trục Danh mục
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Thiết lập định dạng đường lưới phụ cho trục Danh mục
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Thiết lập Thuộc tính Văn bản Trục Thể loại
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Thiết lập Tiêu đề Thể loại
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Thiết lập vị trí nhãn trục danh mục
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Thiết lập nhãn trục loại góc quay
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Thiết lập Thuộc tính Văn bản Huyền thoại
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Đặt hiển thị chú giải biểu đồ mà không chồng chéo biểu đồ
	chart.getLegend().setOverlay(true);
	// Vẽ chuỗi đầu tiên trên trục giá trị thứ cấp
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = đúng;
	// Thiết lập biểu đồ màu tường phía sau
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Thiết lập màu vùng vẽ
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Lưu bài thuyết trình
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá thế giới của các thực thể biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn đã học cách tạo, tùy chỉnh và thao tác biểu đồ để nâng cao bài thuyết trình của mình. Biểu đồ không chỉ làm cho dữ liệu của bạn hấp dẫn về mặt trực quan mà còn giúp khán giả của bạn hiểu thông tin phức tạp dễ dàng hơn.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi loại biểu đồ?

Để thay đổi loại biểu đồ, hãy sử dụng `chart.setType()` phương pháp và chỉ định loại biểu đồ mong muốn.

### Tôi có thể thêm nhiều chuỗi dữ liệu vào biểu đồ không?

Có, bạn có thể thêm nhiều chuỗi dữ liệu vào biểu đồ bằng cách sử dụng `chart.getChartData().getSeries().addSeries()` phương pháp.

### Làm thế nào để tùy chỉnh màu biểu đồ?

Bạn có thể tùy chỉnh màu biểu đồ bằng cách thiết lập định dạng tô cho nhiều thành phần biểu đồ khác nhau, chẳng hạn như đường lưới, tiêu đề và chú thích.

### Tôi có thể tạo biểu đồ 3D không?

Có, Aspose.Slides for Java hỗ trợ việc tạo biểu đồ 3D. Bạn có thể thiết lập `ChartType` vào biểu đồ 3D để tạo một biểu đồ.

### Aspose.Slides for Java có tương thích với các phiên bản Java mới nhất không?

Có, Aspose.Slides for Java được cập nhật thường xuyên để hỗ trợ các phiên bản Java mới nhất và tương thích với nhiều môi trường Java khác nhau.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}