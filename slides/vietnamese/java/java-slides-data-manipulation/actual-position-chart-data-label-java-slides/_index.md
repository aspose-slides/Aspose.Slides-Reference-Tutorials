---
"description": "Tìm hiểu cách lấy vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides cho Java. Hướng dẫn từng bước có mã nguồn."
"linktitle": "Lấy Vị trí Thực tế của Nhãn Dữ liệu Biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lấy Vị trí Thực tế của Nhãn Dữ liệu Biểu đồ trong Java Slides"
"url": "/vi/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lấy Vị trí Thực tế của Nhãn Dữ liệu Biểu đồ trong Java Slides


## Giới thiệu về Lấy Vị trí Thực tế của Nhãn Dữ liệu Biểu đồ trong Java Slides

Trong hướng dẫn này, bạn sẽ học cách lấy vị trí thực tế của nhãn dữ liệu biểu đồ bằng Aspose.Slides for Java. Chúng ta sẽ tạo một chương trình Java tạo bản trình bày PowerPoint có biểu đồ, tùy chỉnh nhãn dữ liệu, sau đó thêm hình dạng biểu diễn vị trí của các nhãn dữ liệu này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng bạn đã thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình.

## Bước 1: Tạo bài thuyết trình PowerPoint

Trước tiên, hãy tạo một bản trình bày PowerPoint mới và thêm biểu đồ vào đó. Chúng ta sẽ tùy chỉnh nhãn dữ liệu của biểu đồ sau trong hướng dẫn.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Bước 2: Tùy chỉnh nhãn dữ liệu
Bây giờ, hãy tùy chỉnh nhãn dữ liệu cho chuỗi biểu đồ. Chúng ta sẽ đặt vị trí của chúng và hiển thị các giá trị.

```java
try {
    // ... (mã trước)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (mã còn lại)
} finally {
    if (pres != null) pres.dispose();
}
```

## Bước 3: Nhận vị trí thực tế của nhãn dữ liệu
Ở bước này, chúng ta sẽ lặp qua các điểm dữ liệu của chuỗi biểu đồ và lấy vị trí thực tế của các nhãn dữ liệu có giá trị lớn hơn 4. Sau đó, chúng ta sẽ thêm dấu ba chấm để biểu diễn các vị trí này.

```java
try {
    // ... (mã trước)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (mã còn lại)
} finally {
    if (pres != null) pres.dispose();
}
```

## Bước 4: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày đã tạo vào một tệp.

```java
try {
    // ... (mã trước)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Mã nguồn đầy đủ để lấy vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//CẦN LÀM
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách lấy vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bây giờ bạn có thể sử dụng kiến thức này để nâng cao bài thuyết trình PowerPoint của mình bằng nhãn dữ liệu tùy chỉnh và biểu diễn trực quan về vị trí của chúng.

## Câu hỏi thường gặp

### Làm thế nào để tùy chỉnh nhãn dữ liệu trong biểu đồ?

Để tùy chỉnh nhãn dữ liệu trong biểu đồ, bạn có thể sử dụng `setDefaultDataLabelFormat` phương pháp trên chuỗi biểu đồ và thiết lập các thuộc tính như vị trí và khả năng hiển thị. Ví dụ:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Làm thế nào tôi có thể thêm hình dạng để biểu diễn vị trí nhãn dữ liệu?

Bạn có thể lặp lại qua các điểm dữ liệu của một loạt biểu đồ và sử dụng `getActualX`, `getActualY`, `getActualWidth`, Và `getActualHeight` phương pháp của nhãn dữ liệu để có được vị trí của nó. Sau đó, bạn có thể thêm hình dạng bằng cách sử dụng `addAutoShape` phương pháp. Đây là một ví dụ:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Tôi có thể lưu bài thuyết trình đã tạo như thế nào?

Bạn có thể lưu bản trình bày đã tạo bằng cách sử dụng `save` phương pháp. Cung cấp đường dẫn tệp mong muốn và `SaveFormat` như các tham số. Ví dụ:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}