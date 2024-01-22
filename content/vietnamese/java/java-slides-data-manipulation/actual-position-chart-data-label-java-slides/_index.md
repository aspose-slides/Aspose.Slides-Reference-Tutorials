---
title: Nhận vị trí thực tế của nhãn dữ liệu biểu đồ trong các trang trình bày Java
linktitle: Nhận vị trí thực tế của nhãn dữ liệu biểu đồ trong các trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách lấy vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides for Java. Hướng dẫn từng bước với mã nguồn.
type: docs
weight: 18
url: /vi/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Giới thiệu Cách lấy vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides

Trong hướng dẫn này, bạn sẽ tìm hiểu cách truy xuất vị trí thực tế của nhãn dữ liệu biểu đồ bằng Aspose.Slides cho Java. Chúng ta sẽ tạo một chương trình Java để tạo bản trình bày PowerPoint có biểu đồ, tùy chỉnh nhãn dữ liệu, sau đó thêm các hình thể hiện vị trí của các nhãn dữ liệu này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Slides cho Java trong dự án Java của mình.

## Bước 1: Tạo bản trình bày PowerPoint

Trước tiên, hãy tạo một bản trình bày PowerPoint mới và thêm biểu đồ vào đó. Chúng tôi sẽ tùy chỉnh nhãn dữ liệu của biểu đồ sau trong phần hướng dẫn.

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
Bây giờ, hãy tùy chỉnh nhãn dữ liệu cho chuỗi biểu đồ. Chúng tôi sẽ thiết lập vị trí của họ và hiển thị các giá trị.

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
Trong bước này, chúng ta sẽ lặp qua các điểm dữ liệu của chuỗi biểu đồ và truy xuất vị trí thực tế của các nhãn dữ liệu có giá trị lớn hơn 4. Sau đó, chúng ta sẽ thêm các hình elip để thể hiện các vị trí này.

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

## Mã nguồn hoàn chỉnh để nhận vị trí thực tế của nhãn dữ liệu biểu đồ trong các trang trình bày Java

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//LÀM
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

Trong hướng dẫn này, bạn đã học cách truy xuất vị trí thực tế của nhãn dữ liệu biểu đồ trong Java Slides bằng Aspose.Slides for Java. Giờ đây, bạn có thể sử dụng kiến thức này để cải thiện bản trình bày PowerPoint của mình bằng nhãn dữ liệu tùy chỉnh và cách trình bày trực quan về vị trí của chúng.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể tùy chỉnh nhãn dữ liệu trong biểu đồ?

 Để tùy chỉnh nhãn dữ liệu trong biểu đồ, bạn có thể sử dụng`setDefaultDataLabelFormat` trên chuỗi biểu đồ và đặt các thuộc tính như vị trí và mức độ hiển thị. Ví dụ:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Làm cách nào tôi có thể thêm hình dạng để thể hiện vị trí nhãn dữ liệu?

 Bạn có thể lặp qua các điểm dữ liệu của chuỗi biểu đồ và sử dụng`getActualX`, `getActualY`, `getActualWidth` , Và`getActualHeight`phương pháp của nhãn dữ liệu để có được vị trí của nó. Sau đó, bạn có thể thêm hình dạng bằng cách sử dụng`addAutoShape` phương pháp. Đây là một ví dụ:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Làm cách nào để lưu bản trình bày đã tạo?

 Bạn có thể lưu bản trình bày đã tạo bằng cách sử dụng`save` phương pháp. Cung cấp đường dẫn tệp mong muốn và`SaveFormat` như các tham số. Ví dụ:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```