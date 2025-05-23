---
"description": "Học cách thêm chú thích hình bánh rán vào Java Slides bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn để nâng cao bài thuyết trình."
"linktitle": "Thêm Doughnut Callout vào Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm Doughnut Callout vào Java Slides"
"url": "/vi/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Doughnut Callout vào Java Slides


## Giới thiệu về Thêm chú thích hình bánh rán trong Java Slides bằng Aspose.Slides cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm Doughnut Callout vào slide trong Java bằng Aspose.Slides for Java. Doughnut Callout là một thành phần biểu đồ có thể được sử dụng để làm nổi bật các điểm dữ liệu cụ thể trong biểu đồ Doughnut. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước và mã nguồn hoàn chỉnh để bạn tiện theo dõi.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

1. Môi trường phát triển Java
2. Aspose.Slides cho thư viện Java
3. Môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA
4. Bài thuyết trình PowerPoint mà bạn muốn thêm chú thích hình bánh rán

## Bước 1: Thiết lập Dự án Java của bạn

1. Tạo một dự án Java mới trong IDE mà bạn chọn.
2. Thêm thư viện Aspose.Slides cho Java vào dự án của bạn dưới dạng thư viện phụ thuộc.

## Bước 2: Khởi tạo bài thuyết trình

Để bắt đầu, bạn sẽ cần khởi tạo bản trình bày PowerPoint và tạo một trang chiếu nơi bạn muốn thêm Doughnut Callout. Sau đây là mã để thực hiện việc này:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Hãy chắc chắn thay thế `"Your Document Directory"` với đường dẫn thực tế đến tệp bản trình bày PowerPoint của bạn.

## Bước 3: Tạo biểu đồ hình bánh rán

Tiếp theo, bạn sẽ tạo biểu đồ Doughnut trên slide. Bạn có thể tùy chỉnh vị trí và kích thước của biểu đồ theo yêu cầu của mình. Sau đây là mã để thêm biểu đồ Doughnut:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Bước 4: Tùy chỉnh Biểu đồ hình tròn

Bây giờ, đã đến lúc tùy chỉnh biểu đồ Doughnut. Chúng ta sẽ thiết lập nhiều thuộc tính khác nhau như xóa chú giải, cấu hình kích thước lỗ và điều chỉnh góc lát cắt đầu tiên. Đây là mã:

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

Đoạn mã này thiết lập các thuộc tính cho biểu đồ Doughnut. Bạn có thể điều chỉnh các giá trị để đáp ứng nhu cầu cụ thể của mình.

## Bước 5: Thêm dữ liệu vào biểu đồ hình tròn

Bây giờ, hãy thêm dữ liệu vào biểu đồ Doughnut. Chúng ta cũng sẽ tùy chỉnh giao diện của các điểm dữ liệu. Sau đây là mã để thực hiện việc này:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Tùy chỉnh giao diện điểm dữ liệu ở đây
        i++;
    }
    categoryIndex++;
}
```

Trong mã này, chúng tôi đang thêm các danh mục và điểm dữ liệu vào biểu đồ Doughnut. Bạn có thể tùy chỉnh thêm giao diện của các điểm dữ liệu khi cần.

## Bước 6: Lưu bài thuyết trình

Cuối cùng, đừng quên lưu bài thuyết trình của bạn sau khi thêm Doughnut Callout. Đây là mã để lưu bài thuyết trình:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Hãy chắc chắn thay thế `"chart.pptx"` với tên tập tin bạn muốn.

Xin chúc mừng! Bạn đã thêm thành công Doughnut Callout vào slide Java bằng Aspose.Slides for Java. Bây giờ bạn có thể chạy ứng dụng Java của mình để tạo bản trình bày PowerPoint với biểu đồ Doughnut và Callout.

## Mã nguồn đầy đủ để thêm chú thích hình bánh rán vào trang trình bày Java

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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(đúng);
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

Trong hướng dẫn này, chúng tôi đã trình bày quy trình thêm Doughnut Callout vào slide Java bằng Aspose.Slides for Java. Bạn đã học cách tạo biểu đồ Doughnut, tùy chỉnh giao diện và thêm điểm dữ liệu. Hãy thoải mái cải thiện bài thuyết trình của bạn hơn nữa bằng thư viện mạnh mẽ này và khám phá thêm nhiều tùy chọn biểu đồ hơn.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi giao diện của chú thích Doughnut?

Bạn có thể tùy chỉnh giao diện của Doughnut Callout bằng cách sửa đổi các thuộc tính của điểm dữ liệu trong biểu đồ. Trong mã được cung cấp, bạn có thể xem cách đặt màu tô, màu đường, kiểu phông chữ và các thuộc tính khác của điểm dữ liệu.

### Tôi có thể thêm nhiều điểm dữ liệu hơn vào biểu đồ Doughnut không?

Có, bạn có thể thêm bao nhiêu điểm dữ liệu tùy ý vào biểu đồ Doughnut. Chỉ cần mở rộng các vòng lặp trong mã nơi các danh mục và điểm dữ liệu được thêm vào, và cung cấp dữ liệu và định dạng phù hợp.

### Làm thế nào để điều chỉnh vị trí và kích thước của biểu đồ Doughnut trên trang chiếu?

Bạn có thể thay đổi vị trí và kích thước của biểu đồ Doughnut bằng cách sửa đổi các tham số trong `addChart` phương pháp. Bốn số trong phương pháp đó tương ứng với tọa độ X và Y của góc trên cùng bên trái của biểu đồ, chiều rộng và chiều cao của biểu đồ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}