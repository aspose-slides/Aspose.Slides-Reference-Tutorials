---
"description": "Tìm hiểu cách ẩn các thành phần biểu đồ trong Java Slides với Aspose.Slides for Java. Tùy chỉnh bài thuyết trình để rõ ràng và thẩm mỹ hơn với hướng dẫn từng bước và mã nguồn."
"linktitle": "Ẩn thông tin khỏi biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Ẩn thông tin khỏi biểu đồ trong Java Slides"
"url": "/vi/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ẩn thông tin khỏi biểu đồ trong Java Slides


## Giới thiệu về Ẩn thông tin khỏi biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách ẩn nhiều thành phần khác nhau khỏi biểu đồ trong Java Slides bằng cách sử dụng Aspose.Slides for Java API. Bạn có thể sử dụng mã này để tùy chỉnh biểu đồ của mình khi cần cho bài thuyết trình của mình.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thêm thư viện Aspose.Slides for Java vào dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 2: Tạo một bài thuyết trình mới

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 3: Thêm biểu đồ vào trang chiếu

Chúng tôi sẽ thêm biểu đồ đường có đánh dấu vào trang chiếu và sau đó tiến hành ẩn các thành phần khác nhau của biểu đồ.

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

Để ẩn trục giá trị (trục dọc), hãy sử dụng mã sau:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Bước 6: Ẩn Trục Danh mục

Để ẩn trục danh mục (trục ngang), hãy sử dụng mã này:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Bước 7: Ẩn chú giải

Bạn có thể ẩn chú thích của biểu đồ như thế này:

```java
chart.setLegend(false);
```

## Bước 8: Ẩn các đường lưới chính

Để ẩn các đường lưới chính của trục ngang, bạn có thể sử dụng đoạn mã sau:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Bước 9: Xóa Series

Nếu bạn muốn xóa toàn bộ chuỗi khỏi biểu đồ, bạn có thể sử dụng vòng lặp như thế này:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Bước 10: Tùy chỉnh Chuỗi Biểu đồ

Bạn có thể tùy chỉnh chuỗi biểu đồ khi cần. Trong ví dụ này, chúng tôi thay đổi kiểu đánh dấu, vị trí nhãn dữ liệu, kích thước đánh dấu, màu đường và kiểu gạch ngang:

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

Cuối cùng, lưu bài thuyết trình vào một tệp:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Vậy là xong! Bạn đã ẩn thành công nhiều thành phần khác nhau khỏi biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh thêm biểu đồ và bản trình bày của mình khi cần cho các yêu cầu cụ thể của bạn.

## Mã nguồn đầy đủ để ẩn thông tin khỏi biểu đồ trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Ẩn tiêu đề biểu đồ
	chart.setTitle(false);
	///Ẩn trục Giá trị
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Hiển thị trục danh mục
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Ẩn Huyền Thoại
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
	//Thiết lập màu dòng sê-ri
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

Trong hướng dẫn từng bước này, chúng tôi đã khám phá cách ẩn nhiều thành phần khác nhau khỏi biểu đồ trong Java Slides bằng cách sử dụng Aspose.Slides for Java API. Điều này có thể cực kỳ hữu ích khi bạn cần tùy chỉnh biểu đồ cho bài thuyết trình và làm cho chúng hấp dẫn hơn về mặt hình ảnh hoặc phù hợp với nhu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Làm thế nào để tùy chỉnh thêm giao diện của các thành phần biểu đồ?

Bạn có thể tùy chỉnh nhiều thuộc tính khác nhau của các thành phần biểu đồ như màu đường, màu tô, kiểu đánh dấu, v.v. bằng cách truy cập các thuộc tính tương ứng của chuỗi biểu đồ, đánh dấu, nhãn và định dạng.

### Tôi có thể ẩn những điểm dữ liệu cụ thể trong biểu đồ không?

Có, bạn có thể ẩn các điểm dữ liệu cụ thể bằng cách thao tác dữ liệu trong chuỗi biểu đồ. Bạn có thể xóa các điểm dữ liệu hoặc đặt giá trị của chúng thành null để ẩn chúng.

### Làm thế nào tôi có thể thêm chuỗi bổ sung vào biểu đồ?

Bạn có thể thêm nhiều chuỗi hơn vào biểu đồ bằng cách sử dụng `IChartData.getSeries().add` phương pháp và chỉ định các điểm dữ liệu cho chuỗi mới.

### Có thể thay đổi loại biểu đồ một cách linh hoạt không?

Có, bạn có thể thay đổi loại biểu đồ một cách linh hoạt bằng cách tạo biểu đồ mới theo loại mong muốn và sao chép dữ liệu từ biểu đồ cũ sang biểu đồ mới.

### Làm thế nào tôi có thể thay đổi tiêu đề biểu đồ và nhãn trục theo chương trình?

Bạn có thể đặt tiêu đề và nhãn cho biểu đồ và trục bằng cách truy cập vào các thuộc tính tương ứng của chúng và đặt văn bản và định dạng mong muốn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}