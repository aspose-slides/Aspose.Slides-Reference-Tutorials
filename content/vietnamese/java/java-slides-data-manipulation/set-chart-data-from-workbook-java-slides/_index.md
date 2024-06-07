---
title: Đặt dữ liệu biểu đồ từ sổ làm việc trong các trang trình bày Java
linktitle: Đặt dữ liệu biểu đồ từ sổ làm việc trong các trang trình bày Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt dữ liệu biểu đồ từ sổ làm việc Excel trong Java Slides bằng Aspose.Slides. Hướng dẫn từng bước với các ví dụ về mã cho bản trình bày động.
type: docs
weight: 15
url: /vi/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Giới thiệu về Đặt dữ liệu biểu đồ từ sổ làm việc trong Java Slides

Aspose.Slides for Java là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint theo chương trình. Nó cung cấp các tính năng mở rộng để tạo, thao tác và quản lý các slide PowerPoint. Một yêu cầu chung khi làm việc với bản trình bày là đặt dữ liệu biểu đồ một cách linh hoạt từ nguồn dữ liệu bên ngoài, chẳng hạn như sổ làm việc Excel. Trong hướng dẫn này, chúng tôi sẽ trình bày cách đạt được điều này bằng cách sử dụng Java.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào triển khai, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides dành cho Java đã được thêm vào dự án của bạn.
- Sổ làm việc Excel có dữ liệu bạn muốn sử dụng cho biểu đồ.

## Bước 1: Tạo bản trình bày

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Chúng tôi bắt đầu bằng cách tạo bản trình bày PowerPoint mới bằng Aspose.Slides cho Java.

## Bước 2: Thêm biểu đồ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Tiếp theo, chúng ta thêm biểu đồ vào một trong các slide trong bài thuyết trình. Trong ví dụ này, chúng tôi đang thêm biểu đồ hình tròn nhưng bạn có thể chọn loại biểu đồ phù hợp với nhu cầu của mình.

## Bước 3: Xóa dữ liệu biểu đồ

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Chúng tôi xóa mọi dữ liệu hiện có khỏi biểu đồ để chuẩn bị cho dữ liệu mới từ sổ làm việc Excel.

## Bước 4: Tải sổ làm việc Excel

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Chúng tôi tải sổ làm việc Excel chứa dữ liệu chúng tôi muốn sử dụng cho biểu đồ. Thay thế`"book1.xlsx"` với đường dẫn đến tệp Excel của bạn.

## Bước 5: Viết luồng sổ làm việc vào dữ liệu biểu đồ

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Chúng tôi chuyển đổi dữ liệu sổ làm việc Excel thành một luồng và ghi nó vào dữ liệu biểu đồ.

## Bước 6: Đặt phạm vi dữ liệu biểu đồ

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Chúng tôi chỉ định phạm vi ô từ sổ làm việc Excel sẽ được sử dụng làm dữ liệu cho biểu đồ. Điều chỉnh phạm vi khi cần thiết cho dữ liệu của bạn.

## Bước 7: Tùy chỉnh chuỗi biểu đồ

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Bạn có thể tùy chỉnh các thuộc tính khác nhau của chuỗi biểu đồ để phù hợp với yêu cầu của mình. Trong ví dụ này, chúng tôi kích hoạt nhiều màu sắc khác nhau cho chuỗi biểu đồ.

## Bước 8: Lưu bài thuyết trình

```java
pres.save(outPath, SaveFormat.Pptx);
```

Cuối cùng, chúng tôi lưu bản trình bày có dữ liệu biểu đồ được cập nhật vào đường dẫn đầu ra đã chỉ định.

## Mã nguồn hoàn chỉnh cho dữ liệu biểu đồ tập hợp từ sổ làm việc trong các trang trình bày Java

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thiết lập dữ liệu biểu đồ từ sổ làm việc Excel trong Java Slides bằng thư viện Aspose.Slides cho Java. Bằng cách làm theo hướng dẫn từng bước và sử dụng các ví dụ về mã nguồn được cung cấp, bạn có thể dễ dàng tích hợp dữ liệu biểu đồ động vào bản trình bày PowerPoint của mình.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể tùy chỉnh giao diện của biểu đồ trong bản trình bày của mình?

Bạn có thể tùy chỉnh giao diện của biểu đồ bằng cách sửa đổi các thuộc tính như màu sắc, phông chữ, nhãn, v.v. Tham khảo tài liệu Aspose.Slides for Java để biết thông tin chi tiết về các tùy chọn tùy chỉnh biểu đồ.

### Tôi có thể sử dụng dữ liệu từ tệp Excel khác cho biểu đồ không?

Có, bạn có thể sử dụng dữ liệu từ bất kỳ tệp Excel nào bằng cách chỉ định đường dẫn tệp chính xác khi tải sổ làm việc trong mã.

### Tôi có thể tạo những loại biểu đồ nào khác bằng Aspose.Slides cho Java?

Aspose.Slides for Java hỗ trợ nhiều loại biểu đồ khác nhau, bao gồm biểu đồ thanh, biểu đồ đường, biểu đồ phân tán, v.v. Bạn có thể chọn loại biểu đồ phù hợp nhất với nhu cầu trình bày dữ liệu của mình.

### Có thể cập nhật dữ liệu biểu đồ một cách linh hoạt trong bản trình bày đang chạy không?

Có, bạn có thể cập nhật dữ liệu biểu đồ một cách linh hoạt trong bản trình bày bằng cách sửa đổi sổ làm việc cơ bản rồi làm mới dữ liệu biểu đồ.

### Tôi có thể tìm thêm ví dụ và tài nguyên để làm việc với Aspose.Slides cho Java ở đâu?

 Bạn có thể khám phá các ví dụ và tài nguyên bổ sung trên[trang web giả định](https://www.aspose.com/). Ngoài ra, tài liệu Aspose.Slides for Java cung cấp hướng dẫn toàn diện về cách làm việc với thư viện.