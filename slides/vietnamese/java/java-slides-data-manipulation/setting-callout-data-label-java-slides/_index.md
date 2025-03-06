---
title: Đặt chú thích cho nhãn dữ liệu trong Java Slides
linktitle: Đặt chú thích cho nhãn dữ liệu trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thiết lập chú thích cho nhãn dữ liệu trong Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn.
weight: 25
url: /vi/java/data-manipulation/setting-callout-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt chú thích cho nhãn dữ liệu trong Java Slides


## Giới thiệu về Đặt chú thích cho nhãn dữ liệu trong Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ trình bày cách thiết lập chú thích cho nhãn dữ liệu trong biểu đồ bằng Aspose.Slides cho Java. Chú thích có thể hữu ích để làm nổi bật các điểm dữ liệu cụ thể trong biểu đồ của bạn. Chúng tôi sẽ hướng dẫn từng bước về mã và cung cấp mã nguồn cần thiết.

## Điều kiện tiên quyết

- Bạn nên cài đặt Aspose.Slides cho Java.
- Tạo một dự án Java và thêm thư viện Aspose.Slides vào dự án của bạn.

## Bước 1: Tạo bản trình bày và thêm biểu đồ

 Đầu tiên chúng ta cần tạo một bài thuyết trình và thêm biểu đồ vào slide. Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Bước 2: Cấu hình biểu đồ

Tiếp theo, chúng ta sẽ định cấu hình biểu đồ bằng cách đặt các thuộc tính như chú giải, chuỗi và danh mục.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Định cấu hình chuỗi và danh mục (Bạn có thể điều chỉnh số lượng chuỗi và danh mục)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Thêm điểm dữ liệu ở đây
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Bước 3: Tùy chỉnh nhãn dữ liệu

Bây giờ, chúng ta sẽ tùy chỉnh nhãn dữ liệu, bao gồm cả việc thiết lập chú thích cho chuỗi cuối cùng.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Tùy chỉnh định dạng điểm dữ liệu (Điền, Dòng, v.v.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Tùy chỉnh định dạng nhãn (Phông chữ, Điền, v.v.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Bật chú thích
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình với biểu đồ đã cấu hình.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Bây giờ, bạn đã thiết lập thành công chú thích cho nhãn dữ liệu trong biểu đồ bằng Aspose.Slides cho Java. Tùy chỉnh mã theo yêu cầu dữ liệu và biểu đồ cụ thể của bạn.

## Mã nguồn hoàn chỉnh để đặt chú thích cho nhãn dữ liệu trong Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách thiết lập chú thích cho nhãn dữ liệu trong biểu đồ bằng Aspose.Slides cho Java. Chú thích là công cụ có giá trị để nhấn mạnh các điểm dữ liệu cụ thể trong biểu đồ và bản trình bày của bạn. Chúng tôi đã cung cấp hướng dẫn từng bước cùng với mã nguồn để giúp bạn thực hiện việc tùy chỉnh này.

## Câu hỏi thường gặp

### Làm cách nào để tùy chỉnh giao diện của nhãn dữ liệu?

Để tùy chỉnh giao diện của nhãn dữ liệu, bạn có thể sửa đổi các thuộc tính như phông chữ, màu tô và kiểu đường kẻ. Ví dụ:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Làm cách nào để bật hoặc tắt chú thích cho nhãn dữ liệu?

 Để bật hoặc tắt chú thích cho nhãn dữ liệu, hãy sử dụng`setShowLabelAsDataCallout` phương pháp. Đặt nó thành`true` để bật chú thích và`false`để vô hiệu hóa chúng.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Bật chú thích
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Tắt chú thích
```

### Tôi có thể tùy chỉnh dòng dẫn đầu cho nhãn dữ liệu không?

Có, bạn có thể tùy chỉnh dòng đầu cho nhãn dữ liệu bằng các thuộc tính như kiểu đường, màu sắc và chiều rộng. Ví dụ:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Bật dòng chỉ dẫn
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Đây là một số tùy chọn tùy chỉnh phổ biến cho nhãn dữ liệu và chú thích trong Aspose.Slides cho Java. Bạn có thể điều chỉnh thêm giao diện theo nhu cầu cụ thể của mình.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
