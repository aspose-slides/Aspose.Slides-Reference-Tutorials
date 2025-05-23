---
"description": "Tìm hiểu cách tùy chỉnh biểu đồ trong Java Slides bằng Aspose.Slides for Java. Khám phá các tùy chọn biểu đồ thứ hai và cải thiện bài thuyết trình của bạn."
"linktitle": "Tùy chọn biểu đồ thứ hai cho biểu đồ trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tùy chọn biểu đồ thứ hai cho biểu đồ trong Java Slides"
"url": "/vi/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chọn biểu đồ thứ hai cho biểu đồ trong Java Slides


## Giới thiệu về Tùy chọn Biểu đồ Thứ hai cho Biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm tùy chọn biểu đồ thứ hai vào biểu đồ bằng Aspose.Slides for Java. Tùy chọn biểu đồ thứ hai cho phép bạn tùy chỉnh giao diện và hành vi của biểu đồ, đặc biệt là trong các tình huống như biểu đồ Pie of Pie. Chúng tôi sẽ cung cấp hướng dẫn từng bước và ví dụ về mã nguồn để thực hiện điều này. 

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập Aspose.Slides for Java trong dự án Java của mình.

## Bước 1: Tạo bài thuyết trình
Hãy bắt đầu bằng cách tạo một bài thuyết trình mới:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ vào trang chiếu
Tiếp theo, chúng ta sẽ thêm biểu đồ vào slide. Trong ví dụ này, chúng ta sẽ tạo biểu đồ Pie of Pie:

```java
// Thêm biểu đồ vào trang chiếu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Bước 3: Tùy chỉnh Thuộc tính Biểu đồ
Bây giờ, chúng ta hãy thiết lập các thuộc tính khác nhau cho biểu đồ, bao gồm các tùy chọn biểu đồ thứ hai:

```java
// Hiển thị nhãn dữ liệu cho chuỗi đầu tiên
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Đặt kích thước của hình tròn thứ hai (theo phần trăm)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Chia bánh theo phần trăm
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Đặt vị trí chia tách
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Bước 4: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày với các tùy chọn biểu đồ và sơ đồ thứ hai:

```java
// Ghi bản trình bày vào đĩa
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn đầy đủ cho các tùy chọn lô thứ hai

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Presentation
Presentation presentation = new Presentation();
// Thêm biểu đồ vào trang chiếu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Thiết lập các thuộc tính khác nhau
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Ghi bản trình bày vào đĩa
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm tùy chọn biểu đồ thứ hai vào biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh nhiều thuộc tính khác nhau để nâng cao giao diện và chức năng của biểu đồ, giúp bài thuyết trình của bạn nhiều thông tin hơn và hấp dẫn hơn về mặt hình ảnh.

## Câu hỏi thường gặp

### Làm thế nào để thay đổi kích thước của hình tròn thứ hai trong biểu đồ Pie of Pie?

Để thay đổi kích thước của hình tròn thứ hai trong biểu đồ Pie of Pie, hãy sử dụng `setSecondPieSize` phương pháp như được hiển thị trong ví dụ mã ở trên. Điều chỉnh giá trị để chỉ định kích thước theo phần trăm.

### Cái gì làm `PieSplitBy` kiểm soát trong biểu đồ Pie of Pie?

Các `PieSplitBy` thuộc tính kiểm soát cách biểu đồ hình tròn được chia. Bạn có thể đặt nó thành `PieSplitType.ByPercentage` hoặc `PieSplitType.ByValue` để chia biểu đồ theo phần trăm hoặc theo giá trị cụ thể.

### Làm thế nào để thiết lập vị trí chia tách trong biểu đồ Pie of Pie?

Bạn có thể thiết lập vị trí chia tách trong biểu đồ Pie of Pie bằng cách sử dụng `setPieSplitPosition` phương pháp. Điều chỉnh giá trị để xác định vị trí mong muốn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}