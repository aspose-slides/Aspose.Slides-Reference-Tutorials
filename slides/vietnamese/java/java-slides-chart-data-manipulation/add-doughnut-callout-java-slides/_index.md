---
title: Thêm chú thích bánh rán trong trang trình bày Java
linktitle: Thêm chú thích bánh rán trong trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm chú thích bánh rán trong các trang trình bày Java bằng cách sử dụng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để nâng cao bài thuyết trình.
weight: 12
url: /vi/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu về Thêm chú thích bánh rán trong các trang trình bày Java bằng Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm chú thích Donut vào trang chiếu trong Java bằng cách sử dụng Aspose.Slides cho Java. Chú thích Donut là một thành phần biểu đồ có thể được sử dụng để làm nổi bật các điểm dữ liệu cụ thể trong biểu đồ Donut. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước và mã nguồn hoàn chỉnh để thuận tiện cho bạn.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Môi trường phát triển Java
2. Aspose.Slides cho thư viện Java
3. Môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA
4. Bản trình bày PowerPoint nơi bạn muốn thêm chú thích Donut

## Bước 1: Thiết lập dự án Java của bạn

1. Tạo một dự án Java mới trong IDE bạn đã chọn.
2. Thêm thư viện Aspose.Slides for Java vào dự án của bạn dưới dạng phụ thuộc.

## Bước 2: Khởi tạo bài thuyết trình

Để bắt đầu, bạn cần khởi tạo bản trình bày PowerPoint và tạo trang chiếu mà bạn muốn thêm Chú thích Donut. Đây là mã để đạt được điều này:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Đảm bảo thay thế`"Your Document Directory"` với đường dẫn thực tế tới tệp bản trình bày PowerPoint của bạn.

## Bước 3: Tạo biểu đồ bánh rán

Tiếp theo, bạn sẽ tạo biểu đồ Donut trên slide. Bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ theo yêu cầu của mình. Đây là mã để thêm biểu đồ Donut:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Bước 4: Tùy chỉnh biểu đồ Donut

Bây giờ là lúc tùy chỉnh biểu đồ Donut. Chúng tôi sẽ đặt các thuộc tính khác nhau như xóa chú giải, định cấu hình kích thước lỗ và điều chỉnh góc cắt đầu tiên. Đây là mã:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Đoạn mã này đặt các thuộc tính cho biểu đồ Donut. Bạn có thể điều chỉnh các giá trị để đáp ứng nhu cầu cụ thể của mình.

## Bước 5: Thêm dữ liệu vào biểu đồ Donut

Bây giờ, hãy thêm dữ liệu vào biểu đồ Donut. Chúng tôi cũng sẽ tùy chỉnh giao diện của các điểm dữ liệu. Đây là mã để thực hiện điều này:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Tùy chỉnh giao diện điểm dữ liệu tại đây
        i++;
    }
    categoryIndex++;
}
```

Trong mã này, chúng tôi đang thêm các danh mục và điểm dữ liệu vào biểu đồ Donut. Bạn có thể tùy chỉnh thêm sự xuất hiện của các điểm dữ liệu nếu cần.

## Bước 6: Lưu bài thuyết trình

Cuối cùng, đừng quên lưu bản trình bày của bạn sau khi thêm chú thích Donut. Đây là mã để lưu bản trình bày:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Đảm bảo thay thế`"chart.pptx"` với tên tập tin bạn muốn.

Chúc mừng! Bạn đã thêm thành công chú thích Donut vào trang trình bày Java bằng cách sử dụng Aspose.Slides for Java. Bây giờ bạn có thể chạy ứng dụng Java của mình để tạo bản trình bày PowerPoint với biểu đồ Donut và Chú thích.

## Mã nguồn hoàn chỉnh để thêm chú thích bánh rán trong các trang trình bày Java

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày quá trình thêm chú thích Donut vào trang trình bày Java bằng cách sử dụng Aspose.Slides cho Java. Bạn đã học cách tạo biểu đồ Donut, tùy chỉnh giao diện của biểu đồ và thêm điểm dữ liệu. Hãy thoải mái nâng cao hơn nữa bản trình bày của bạn với thư viện mạnh mẽ này và khám phá thêm các tùy chọn biểu đồ.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể thay đổi giao diện của Chú thích Donut?

Bạn có thể tùy chỉnh giao diện của Chú thích Donut bằng cách sửa đổi thuộc tính của các điểm dữ liệu trong biểu đồ. Trong mã được cung cấp, bạn có thể xem cách đặt màu tô, màu đường, kiểu phông chữ và các thuộc tính khác của điểm dữ liệu.

### Tôi có thể thêm nhiều điểm dữ liệu hơn vào biểu đồ Donut không?

Có, bạn có thể thêm bao nhiêu điểm dữ liệu nếu cần vào biểu đồ Donut. Chỉ cần mở rộng các vòng lặp trong mã nơi thêm các danh mục và điểm dữ liệu, đồng thời cung cấp dữ liệu và định dạng phù hợp.

### Làm cách nào để điều chỉnh vị trí và kích thước của biểu đồ Donut trên slide?

 Bạn có thể thay đổi vị trí và kích thước của biểu đồ Donut bằng cách sửa đổi các tham số trong`addChart` phương pháp. Bốn số trong phương thức đó tương ứng với tọa độ X và Y ở góc trên bên trái của biểu đồ cũng như chiều rộng và chiều cao của nó.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
