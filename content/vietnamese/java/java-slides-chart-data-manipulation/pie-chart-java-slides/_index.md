---
title: Biểu đồ hình tròn trong Java Slides
linktitle: Biểu đồ hình tròn trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Biểu đồ hình tròn tuyệt đẹp trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn từng bước với mã nguồn dành cho nhà phát triển Java.
type: docs
weight: 23
url: /vi/java/chart-data-manipulation/pie-chart-java-slides/
---

## Giới thiệu về Tạo biểu đồ hình tròn trong Java Slide bằng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tạo Biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước và mã nguồn Java để giúp bạn bắt đầu. Hướng dẫn này giả định rằng bạn đã thiết lập môi trường phát triển của mình với Aspose.Slides cho Java.

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Slides for Java trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

## Bước 1: Nhập thư viện cần thiết

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Đảm bảo nhập các lớp cần thiết từ thư viện Aspose.Slides.

## Bước 2: Khởi tạo bài thuyết trình

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation presentation = new Presentation();
```

 Tạo một đối tượng Trình bày mới để thể hiện tệp PowerPoint của bạn. Thay thế`"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.

## Bước 3: Thêm trang trình bày

```java
// Truy cập slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

Lấy trang trình bày đầu tiên mà bạn muốn thêm Biểu đồ hình tròn.

## Bước 4: Thêm biểu đồ hình tròn

```java
//Thêm biểu đồ hình tròn với dữ liệu mặc định
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Thêm Biểu đồ hình tròn vào trang chiếu ở vị trí và kích thước đã chỉ định.

## Bước 5: Đặt tiêu đề biểu đồ

```java
// Đặt tiêu đề biểu đồ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Đặt tiêu đề cho Biểu đồ hình tròn. Bạn có thể tùy chỉnh tiêu đề nếu cần.

## Bước 6: Tùy chỉnh dữ liệu biểu đồ

```java
// Đặt chuỗi đầu tiên để hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Đặt chỉ mục cho bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;

// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Xóa chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm danh mục mới
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Thêm loạt phim mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Tùy chỉnh dữ liệu biểu đồ bằng cách thêm danh mục và chuỗi cũng như đặt giá trị của chúng. Trong ví dụ này, chúng tôi có ba danh mục và một chuỗi với các điểm dữ liệu tương ứng.

## Bước 7: Tùy chỉnh các lĩnh vực biểu đồ hình tròn

```java
// Đặt màu khu vực
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Tùy chỉnh giao diện của từng ngành
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Tùy chỉnh đường viền ngành
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Tùy chỉnh các lĩnh vực khác theo cách tương tự
```

Tùy chỉnh giao diện của từng ngành trong Pie Chart. Bạn có thể thay đổi màu sắc, kiểu đường viền và các thuộc tính hình ảnh khác.

## Bước 8: Tùy chỉnh nhãn dữ liệu

```java
// Tùy chỉnh nhãn dữ liệu
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Tùy chỉnh nhãn dữ liệu cho các điểm dữ liệu khác theo cách tương tự
```

Tùy chỉnh nhãn dữ liệu cho từng điểm dữ liệu trong Biểu đồ hình tròn. Bạn có thể kiểm soát giá trị nào được hiển thị trên biểu đồ.

## Bước 9: Hiển thị dòng đầu

```java
// Hiển thị các dòng dẫn đầu cho biểu đồ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Cho phép các dòng chỉ dẫn kết nối nhãn dữ liệu với các lĩnh vực tương ứng của chúng.

## Bước 10: Đặt góc xoay biểu đồ hình tròn

```java
// Đặt góc xoay cho các phần của Biểu đồ hình tròn
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Đặt góc xoay cho các phần của Biểu đồ hình tròn. Trong ví dụ này, chúng tôi đặt nó ở mức 180 độ.

## Bước 11: Lưu bài thuyết trình

```java
// Lưu bài thuyết trình bằng Biểu đồ hình tròn
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Lưu bản trình bày có Biểu đồ hình tròn vào thư mục được chỉ định.

## Mã nguồn hoàn chỉnh cho biểu đồ hình tròn trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation presentation = new Presentation();
// Truy cập slide đầu tiên
ISlide slides = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Đặt tiêu đề biểu đồ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Lấy bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Thêm loạt phim mới
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
//Hiện đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Không hoạt động trong phiên bản mới
// Thêm điểm mới và thiết lập màu khu vực
// loạt.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Thiết lập đường viền ngành
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Thiết lập đường viền ngành
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Thiết lập đường viền ngành
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Tạo nhãn tùy chỉnh cho từng danh mục cho chuỗi mới
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Hiển thị các dòng dẫn đầu cho biểu đồ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Đặt góc xoay cho các phần biểu đồ hình tròn
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Lưu bài thuyết trình bằng biểu đồ
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Bạn đã tạo thành công Biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bạn có thể tùy chỉnh giao diện và nhãn dữ liệu của biểu đồ theo yêu cầu cụ thể của mình. Hướng dẫn này cung cấp một ví dụ cơ bản và bạn có thể nâng cao và tùy chỉnh thêm biểu đồ của mình nếu cần.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi màu của từng khu vực trong Biểu đồ hình tròn?

 Để thay đổi màu của từng khu vực trong Biểu đồ hình tròn, bạn có thể tùy chỉnh màu tô cho từng điểm dữ liệu. Trong ví dụ về mã được cung cấp, chúng tôi đã trình bày cách đặt màu tô cho từng khu vực bằng cách sử dụng`getSolidFillColor().setColor()` phương pháp. Bạn có thể sửa đổi các giá trị màu để đạt được diện mạo mong muốn.

### Tôi có thể thêm nhiều danh mục và chuỗi dữ liệu hơn vào Biểu đồ hình tròn không?

 Có, bạn có thể thêm các danh mục và chuỗi dữ liệu bổ sung vào Biểu đồ hình tròn. Để làm điều này, bạn có thể sử dụng`getChartData().getCategories().add()` Và`getChartData().getSeries().add()` các phương pháp như trong ví dụ. Chỉ cần cung cấp dữ liệu và nhãn thích hợp cho các danh mục và chuỗi mới để mở rộng biểu đồ của bạn.

### Làm cách nào để tùy chỉnh giao diện của nhãn dữ liệu?

 Bạn có thể tùy chỉnh hình thức của nhãn dữ liệu bằng cách sử dụng`getDataLabelFormat()` phương pháp trên nhãn của mỗi điểm dữ liệu. Trong ví dụ này, chúng tôi đã trình bày cách hiển thị giá trị trên nhãn dữ liệu bằng cách sử dụng`getDataLabelFormat().setShowValue(true)`. Bạn có thể tùy chỉnh thêm nhãn dữ liệu bằng cách kiểm soát giá trị nào được hiển thị, hiển thị các phím chú giải và điều chỉnh các tùy chọn định dạng khác.

### Tôi có thể thay đổi tiêu đề của Biểu đồ hình tròn không?

 Có, bạn có thể thay đổi tiêu đề của Biểu đồ hình tròn. Trong mã được cung cấp, chúng tôi đặt tiêu đề biểu đồ bằng cách sử dụng`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Bạn có thể thay thế`"Sample Title"` với văn bản tiêu đề mong muốn của bạn.

### Làm cách nào để lưu bản trình bày đã tạo bằng Biểu đồ hình tròn?

 Để lưu bài thuyết trình bằng Biểu đồ hình tròn, hãy sử dụng`presentation.save()` phương pháp. Cung cấp đường dẫn và tên tệp mong muốn cùng với định dạng mà bạn muốn lưu bản trình bày. Ví dụ:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Đảm bảo chỉ định đường dẫn và định dạng tệp chính xác.

### Tôi có thể tạo các loại biểu đồ khác bằng Aspose.Slides cho Java không?

Có, Aspose.Slides cho Java hỗ trợ nhiều loại biểu đồ khác nhau, bao gồm Biểu đồ thanh, Biểu đồ đường, v.v. Bạn có thể tạo các loại biểu đồ khác nhau bằng cách thay đổi`ChartType` khi thêm biểu đồ. Tham khảo tài liệu Aspose.Slides để biết thêm chi tiết về cách tạo các loại biểu đồ khác nhau.

### Làm cách nào tôi có thể tìm thêm thông tin và ví dụ để làm việc với Aspose.Slides cho Java?

 Để biết thêm thông tin, tài liệu chi tiết và các ví dụ bổ sung, bạn có thể truy cập[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/). Nó cung cấp các tài nguyên toàn diện để giúp bạn sử dụng thư viện một cách hiệu quả.