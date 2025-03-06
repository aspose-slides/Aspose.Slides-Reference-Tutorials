---
title: Thiết lập định dạng ngày cho trục danh mục trong Java Slides
linktitle: Thiết lập định dạng ngày cho trục danh mục trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt định dạng ngày cho trục danh mục trong biểu đồ PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn.
weight: 26
url: /vi/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thiết lập định dạng ngày cho trục danh mục trong Java Slides


## Giới thiệu Định dạng ngày tháng cho trục danh mục trong Java Slides

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt định dạng ngày cho trục danh mục trong biểu đồ PowerPoint bằng Aspose.Slides cho Java. Aspose.Slides cho Java là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và quản lý bản trình bày PowerPoint theo chương trình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Thư viện Aspose.Slides cho Java (bạn có thể tải xuống từ[đây](https://releases.aspose.com/slides/java/).
2. Môi trường phát triển Java được thiết lập.

## Bước 1: Tạo bản trình bày PowerPoint

Trước tiên, chúng ta cần tạo một bản trình bày PowerPoint nơi chúng ta sẽ thêm biểu đồ. Đảm bảo bạn đã nhập các lớp Aspose.Slides cần thiết.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Bước 2: Thêm biểu đồ vào slide

Bây giờ, hãy thêm biểu đồ vào slide PowerPoint. Chúng tôi sẽ sử dụng biểu đồ Khu vực trong ví dụ này.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Bước 3: Chuẩn bị dữ liệu biểu đồ

Chúng ta sẽ thiết lập dữ liệu biểu đồ và danh mục. Trong ví dụ này, chúng tôi sẽ sử dụng các danh mục ngày.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Thêm danh mục ngày
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Thêm chuỗi dữ liệu
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Bước 4: Tùy chỉnh trục danh mục
Bây giờ, hãy tùy chỉnh trục danh mục để hiển thị ngày theo định dạng cụ thể (ví dụ: yyyy).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Bước 5: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Đó là nó! Bạn đã đặt thành công định dạng ngày cho trục danh mục trong biểu đồ PowerPoint bằng Aspose.Slides cho Java.

## Mã nguồn hoàn chỉnh để thiết lập định dạng ngày cho trục danh mục trong Java Slides

```java
	// Đường dẫn đến thư mục tài liệu.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Phần kết luận

Bạn đã tùy chỉnh thành công định dạng ngày cho trục danh mục trong biểu đồ Java Slides bằng Aspose.Slides for Java. Điều này cho phép bạn trình bày các giá trị ngày ở định dạng mong muốn trên biểu đồ của mình. Vui lòng khám phá các tùy chọn tùy chỉnh khác dựa trên yêu cầu cụ thể của bạn.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi định dạng ngày cho trục danh mục?

 Để thay đổi định dạng ngày cho trục danh mục, hãy sử dụng`setNumberFormat` trên trục danh mục và cung cấp mẫu định dạng ngày mong muốn, chẳng hạn như "yyyy-MM-dd" hoặc "MM/yyyy". Hãy chắc chắn để thiết lập`setNumberFormatLinkedToSource(false)` để ghi đè định dạng mặc định.

### Tôi có thể sử dụng các định dạng ngày khác nhau cho các biểu đồ khác nhau trong cùng một bản trình bày không?

Có, bạn có thể đặt các định dạng ngày khác nhau cho các trục danh mục trong các biểu đồ khác nhau trong cùng một bản trình bày. Chỉ cần tùy chỉnh trục danh mục cho từng biểu đồ nếu cần.

### Làm cách nào để thêm nhiều điểm dữ liệu hơn vào biểu đồ?

 Để thêm nhiều điểm dữ liệu vào biểu đồ, hãy sử dụng`getDataPoints().addDataPointForLineSeries`phương pháp trên chuỗi dữ liệu và cung cấp các giá trị dữ liệu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
