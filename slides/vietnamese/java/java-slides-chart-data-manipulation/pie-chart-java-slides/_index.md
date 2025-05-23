---
"description": "Tìm hiểu cách tạo Biểu đồ hình tròn tuyệt đẹp trong bài thuyết trình PowerPoint bằng Aspose.Slides for Java. Hướng dẫn từng bước có mã nguồn dành cho nhà phát triển Java."
"linktitle": "Biểu đồ hình tròn trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Biểu đồ hình tròn trong Java Slides"
"url": "/vi/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Biểu đồ hình tròn trong Java Slides


## Giới thiệu về cách tạo biểu đồ hình tròn trong Java Slides bằng Aspose.Slides

Trong hướng dẫn này, chúng tôi sẽ trình bày cách tạo Biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Chúng tôi sẽ cung cấp cho bạn hướng dẫn từng bước và mã nguồn Java để giúp bạn bắt đầu. Hướng dẫn này giả định rằng bạn đã thiết lập môi trường phát triển của mình bằng Aspose.Slides for Java.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và cấu hình thư viện Aspose.Slides for Java trong dự án của mình. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Bước 1: Nhập thư viện cần thiết

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Hãy đảm bảo nhập các lớp cần thiết từ thư viện Aspose.Slides.

## Bước 2: Khởi tạo bài thuyết trình

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";

// Khởi tạo lớp Presentation biểu diễn tệp PPTX
Presentation presentation = new Presentation();
```

Tạo một đối tượng Presentation mới để biểu diễn tệp PowerPoint của bạn. Thay thế `"Your Document Directory"` với đường dẫn thực tế mà bạn muốn lưu bản trình bày.

## Bước 3: Thêm một Slide

```java
// Truy cập trang chiếu đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```

Chọn trang chiếu đầu tiên của bài thuyết trình mà bạn muốn thêm Biểu đồ hình tròn.

## Bước 4: Thêm biểu đồ hình tròn

```java
// Thêm biểu đồ hình tròn với dữ liệu mặc định
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

Đặt tiêu đề cho Biểu đồ hình tròn. Bạn có thể tùy chỉnh tiêu đề khi cần.

## Bước 6: Tùy chỉnh dữ liệu biểu đồ

```java
// Đặt chuỗi đầu tiên để hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Thiết lập chỉ mục của biểu đồ dữ liệu bảng
int defaultWorksheetIndex = 0;

// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Xóa các chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Thêm danh mục mới
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Thêm series mới
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Điền dữ liệu chuỗi
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Tùy chỉnh dữ liệu biểu đồ bằng cách thêm danh mục và chuỗi, và thiết lập giá trị của chúng. Trong ví dụ này, chúng ta có ba danh mục và một chuỗi với các điểm dữ liệu tương ứng.

## Bước 7: Tùy chỉnh các khu vực biểu đồ hình tròn

```java
// Đặt màu cho sector
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Tùy chỉnh giao diện của từng khu vực
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Tùy chỉnh đường viền khu vực
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Tùy chỉnh các khu vực khác theo cách tương tự
```

Tùy chỉnh giao diện của từng khu vực trong Biểu đồ hình tròn. Bạn có thể thay đổi màu sắc, kiểu đường viền và các thuộc tính trực quan khác.

## Bước 8: Tùy chỉnh nhãn dữ liệu

```java
// Tùy chỉnh nhãn dữ liệu
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Tùy chỉnh nhãn dữ liệu cho các điểm dữ liệu khác theo cách tương tự
```

Tùy chỉnh nhãn dữ liệu cho từng điểm dữ liệu trong Biểu đồ hình tròn. Bạn có thể kiểm soát giá trị nào được hiển thị trên biểu đồ.

## Bước 9: Hiển thị các đường dẫn

```java
// Hiển thị các đường dẫn cho biểu đồ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Cho phép các đường dẫn kết nối nhãn dữ liệu với các khu vực tương ứng.

## Bước 10: Thiết lập góc xoay biểu đồ hình tròn

```java
// Đặt góc quay cho các phần của Biểu đồ hình tròn
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Đặt góc xoay cho các phần của Biểu đồ hình tròn. Trong ví dụ này, chúng tôi đặt thành 180 độ.

## Bước 11: Lưu bài thuyết trình

```java
// Lưu bài thuyết trình với Biểu đồ hình tròn
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Lưu bản trình bày có Biểu đồ tròn vào thư mục đã chỉ định.

## Mã nguồn đầy đủ cho biểu đồ hình tròn trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Presentation biểu diễn tệp PPTX
Presentation presentation = new Presentation();
// Truy cập trang chiếu đầu tiên
ISlide slides = presentation.getSlides().get_Item(0);
// Thêm biểu đồ với dữ liệu mặc định
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Thiết lập biểu đồ Tiêu đề
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Đặt chuỗi đầu tiên thành Hiển thị giá trị
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Thiết lập chỉ mục của bảng dữ liệu biểu đồ
int defaultWorksheetIndex = 0;
// Nhận bảng tính dữ liệu biểu đồ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Xóa các chuỗi và danh mục được tạo mặc định
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Thêm danh mục mới
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Thêm series mới
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Đang điền dữ liệu chuỗi
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Không hoạt động trong phiên bản mới
// Thêm điểm mới và thiết lập màu cho khu vực
// series.IsColorVaried = đúng;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Thiết lập đường viền Sector
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Thiết lập đường viền Sector
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Thiết lập đường viền Sector
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Tạo nhãn tùy chỉnh cho từng danh mục cho loạt bài mới
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(đúng);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Hiển thị Đường dẫn cho Biểu đồ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Thiết lập góc quay cho các khu vực biểu đồ hình tròn
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Lưu bài thuyết trình có biểu đồ
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Bạn đã tạo thành công Biểu đồ hình tròn trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh giao diện và nhãn dữ liệu của biểu đồ theo yêu cầu cụ thể của mình. Hướng dẫn này cung cấp một ví dụ cơ bản và bạn có thể cải thiện và tùy chỉnh thêm biểu đồ của mình khi cần.

## Câu hỏi thường gặp

### Làm thế nào tôi có thể thay đổi màu sắc của từng khu vực trong Biểu đồ hình tròn?

Để thay đổi màu sắc của từng sector trong Biểu đồ hình tròn, bạn có thể tùy chỉnh màu tô cho từng điểm dữ liệu. Trong ví dụ mã được cung cấp, chúng tôi đã trình bày cách đặt màu tô cho từng sector bằng cách sử dụng `getSolidFillColor().setColor()` phương pháp. Bạn có thể sửa đổi các giá trị màu sắc để đạt được hình thức mong muốn.

### Tôi có thể thêm nhiều danh mục và chuỗi dữ liệu vào Biểu đồ hình tròn không?

Có, bạn có thể thêm các danh mục và chuỗi dữ liệu bổ sung vào Biểu đồ hình tròn. Để thực hiện việc này, bạn có thể sử dụng `getChartData().getCategories().add()` Và `getChartData().getSeries().add()` phương pháp, như được hiển thị trong ví dụ. Chỉ cần cung cấp dữ liệu và nhãn thích hợp cho các danh mục và chuỗi mới để mở rộng biểu đồ của bạn.

### Làm thế nào để tùy chỉnh giao diện của nhãn dữ liệu?

Bạn có thể tùy chỉnh giao diện của nhãn dữ liệu bằng cách sử dụng `getDataLabelFormat()` phương pháp trên nhãn của mỗi điểm dữ liệu. Trong ví dụ, chúng tôi đã trình bày cách hiển thị giá trị trên nhãn dữ liệu bằng cách sử dụng `getDataLabelFormat().setShowValue(true)`. Bạn có thể tùy chỉnh thêm nhãn dữ liệu bằng cách kiểm soát các giá trị được hiển thị, hiển thị các phím chú giải và điều chỉnh các tùy chọn định dạng khác.

### Tôi có thể thay đổi tiêu đề của Biểu đồ hình tròn không?

Có, bạn có thể thay đổi tiêu đề của Biểu đồ hình tròn. Trong mã được cung cấp, chúng tôi đặt tiêu đề biểu đồ bằng cách sử dụng `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Bạn có thể thay thế `"Sample Title"` với tiêu đề văn bản bạn mong muốn.

### Làm thế nào để lưu bản trình bày được tạo bằng Biểu đồ hình tròn?

Để lưu bản trình bày với Biểu đồ hình tròn, hãy sử dụng `presentation.save()` phương pháp. Cung cấp đường dẫn và tên tệp mong muốn cùng với định dạng mà bạn muốn lưu bản trình bày. Ví dụ:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Hãy đảm bảo chỉ định đúng đường dẫn tệp và định dạng.

### Tôi có thể tạo các loại biểu đồ khác bằng Aspose.Slides cho Java không?

Có, Aspose.Slides for Java hỗ trợ nhiều loại biểu đồ, bao gồm Biểu đồ thanh, Biểu đồ đường và nhiều loại khác. Bạn có thể tạo nhiều loại biểu đồ khác nhau bằng cách thay đổi `ChartType` khi thêm biểu đồ. Tham khảo tài liệu Aspose.Slides để biết thêm chi tiết về cách tạo các loại biểu đồ khác nhau.

### Tôi có thể tìm thêm thông tin và ví dụ về cách làm việc với Aspose.Slides cho Java ở đâu?

Để biết thêm thông tin, tài liệu chi tiết và các ví dụ bổ sung, bạn có thể truy cập [Tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/). Nó cung cấp các nguồn tài nguyên toàn diện giúp bạn sử dụng thư viện hiệu quả.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}