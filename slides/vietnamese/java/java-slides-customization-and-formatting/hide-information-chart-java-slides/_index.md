---
title: Ẩn thông tin khỏi biểu đồ trong Java Slides
linktitle: Ẩn thông tin khỏi biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách ẩn các thành phần biểu đồ trong Java Slides với Aspose.Slides for Java. Tùy chỉnh bản trình bày để rõ ràng và có tính thẩm mỹ với hướng dẫn từng bước và mã nguồn.
weight: 13
url: /vi/java/customization-and-formatting/hide-information-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Ẩn thông tin khỏi biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách ẩn các thành phần khác nhau khỏi biểu đồ trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Bạn có thể sử dụng mã này để tùy chỉnh biểu đồ nếu cần cho bản trình bày của mình.

## Bước 1: Thiết lập môi trường

 Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã thêm thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 2: Tạo bản trình bày mới

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 3: Thêm biểu đồ vào slide

Chúng tôi sẽ thêm biểu đồ dạng đường có điểm đánh dấu vào trang chiếu, sau đó tiến hành ẩn các thành phần khác nhau của biểu đồ.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Bước 4: Ẩn tiêu đề biểu đồ

Bạn có thể ẩn tiêu đề biểu đồ như sau:

```java
chart.setTitle(false);
```

## Bước 5: Ẩn trục giá trị

Để ẩn trục giá trị (trục tung), hãy sử dụng mã sau:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Bước 6: Ẩn trục danh mục

Để ẩn trục danh mục (trục ngang), hãy sử dụng mã này:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Bước 7: Ẩn chú giải

Bạn có thể ẩn chú giải của biểu đồ như thế này:

```java
chart.setLegend(false);
```

## Bước 8: Ẩn các đường lưới chính

Để ẩn các đường lưới chính của trục hoành, bạn có thể sử dụng đoạn mã sau:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Bước 9: Xóa chuỗi

Nếu muốn xóa tất cả chuỗi khỏi biểu đồ, bạn có thể sử dụng vòng lặp như thế này:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Bước 10: Tùy chỉnh chuỗi biểu đồ

Bạn có thể tùy chỉnh chuỗi biểu đồ nếu cần. Trong ví dụ này, chúng tôi thay đổi kiểu điểm đánh dấu, vị trí nhãn dữ liệu, kích thước điểm đánh dấu, màu đường và kiểu dấu gạch ngang:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Bước 11: Lưu bài thuyết trình

Cuối cùng, lưu bản trình bày vào một tệp:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã ẩn thành công nhiều thành phần khác nhau khỏi biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh thêm biểu đồ và bản trình bày nếu cần cho các yêu cầu cụ thể của mình.

## Mã nguồn hoàn chỉnh để ẩn thông tin khỏi biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Ẩn biểu đồ
	chart.setTitle(false);
	///Ẩn trục giá trị
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Khả năng hiển thị trục danh mục
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Ẩn huyền thoại
	chart.setLegend(false);
	//Ẩn MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Đặt màu dòng loạt
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Phần kết luận

Trong hướng dẫn từng bước này, chúng tôi đã khám phá cách ẩn các thành phần khác nhau khỏi biểu đồ trong Java Slides bằng cách sử dụng API Aspose.Slides cho Java. Điều này có thể cực kỳ hữu ích khi bạn cần tùy chỉnh biểu đồ cho bản trình bày và làm cho chúng hấp dẫn hơn về mặt trực quan hoặc phù hợp với nhu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Làm cách nào để tùy chỉnh thêm hình thức của các thành phần biểu đồ?

Bạn có thể tùy chỉnh các thuộc tính khác nhau của các thành phần biểu đồ như màu đường, màu tô, kiểu điểm đánh dấu, v.v. bằng cách truy cập các thuộc tính tương ứng của chuỗi biểu đồ, điểm đánh dấu, nhãn và định dạng.

### Tôi có thể ẩn các điểm dữ liệu cụ thể trong biểu đồ không?

Có, bạn có thể ẩn các điểm dữ liệu cụ thể bằng cách thao tác với dữ liệu trong chuỗi biểu đồ. Bạn có thể xóa điểm dữ liệu hoặc đặt giá trị của chúng thành null để ẩn chúng.

### Làm cách nào tôi có thể thêm chuỗi bổ sung vào biểu đồ?

 Bạn có thể thêm nhiều chuỗi khác vào biểu đồ bằng cách sử dụng`IChartData.getSeries().add` phương pháp và chỉ định các điểm dữ liệu cho chuỗi mới.

### Có thể thay đổi loại biểu đồ một cách linh hoạt không?

Có, bạn có thể thay đổi loại biểu đồ một cách linh hoạt bằng cách tạo biểu đồ mới thuộc loại mong muốn và sao chép dữ liệu từ biểu đồ cũ sang biểu đồ mới.

### Làm cách nào để thay đổi tiêu đề và nhãn trục của biểu đồ theo chương trình?

Bạn có thể đặt tiêu đề và nhãn của biểu đồ và trục bằng cách truy cập các thuộc tính tương ứng của chúng và đặt văn bản cũng như định dạng mong muốn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
