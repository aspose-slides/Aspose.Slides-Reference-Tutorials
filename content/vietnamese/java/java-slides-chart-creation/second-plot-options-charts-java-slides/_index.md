---
title: Tùy chọn sơ đồ thứ hai cho biểu đồ trong Java Slides
linktitle: Tùy chọn sơ đồ thứ hai cho biểu đồ trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tùy chỉnh biểu đồ trong Java Slides bằng Aspose.Slides for Java. Khám phá các tùy chọn cốt truyện thứ hai và cải thiện bài thuyết trình của bạn.
type: docs
weight: 12
url: /vi/java/chart-creation/second-plot-options-charts-java-slides/
---

## Giới thiệu về Tùy chọn ô thứ hai cho biểu đồ trong Java Slides

Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm tùy chọn biểu đồ thứ hai vào biểu đồ bằng Aspose.Slides cho Java. Tùy chọn biểu đồ thứ hai cho phép bạn tùy chỉnh giao diện và hoạt động của biểu đồ, đặc biệt trong các trường hợp như biểu đồ Pie of Pie. Chúng tôi sẽ cung cấp hướng dẫn từng bước và ví dụ về mã nguồn để đạt được điều này. 

## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập Aspose.Slides cho Java trong dự án Java của mình.

## Bước 1: Tạo bản trình bày
Hãy bắt đầu bằng cách tạo một bản trình bày mới:

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
```

## Bước 2: Thêm biểu đồ vào slide
Tiếp theo, chúng ta sẽ thêm biểu đồ vào slide. Trong ví dụ này, chúng tôi sẽ tạo biểu đồ Pie of Pie:

```java
// Thêm biểu đồ vào slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Bước 3: Tùy chỉnh thuộc tính biểu đồ
Bây giờ, hãy đặt các thuộc tính khác nhau cho biểu đồ, bao gồm các tùy chọn biểu đồ thứ hai:

```java
// Hiển thị nhãn dữ liệu cho chuỗi đầu tiên
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Đặt kích thước của chiếc bánh thứ hai (theo phần trăm)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Chia chiếc bánh theo tỷ lệ phần trăm
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Đặt vị trí phân chia
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Bước 4: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày với các tùy chọn biểu đồ và biểu đồ thứ hai:

```java
// Ghi bài thuyết trình vào đĩa
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Mã nguồn hoàn chỉnh cho các tùy chọn lô thứ hai

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation presentation = new Presentation();
// Thêm biểu đồ vào slide
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Đặt các thuộc tính khác nhau
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Ghi bài thuyết trình vào đĩa
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm tùy chọn biểu đồ thứ hai vào biểu đồ trong Java Slides bằng Aspose.Slides for Java. Bạn có thể tùy chỉnh các thuộc tính khác nhau để nâng cao hình thức và chức năng của biểu đồ, làm cho bản trình bày của bạn có nhiều thông tin hơn và hấp dẫn trực quan hơn.

## Câu hỏi thường gặp

### Làm cách nào tôi có thể thay đổi kích thước của chiếc bánh thứ hai trong biểu đồ Pie of Pie?

 Để thay đổi kích thước của hình tròn thứ hai trong biểu đồ Pie of Pie, hãy sử dụng`setSecondPieSize` phương thức như trong ví dụ mã ở trên. Điều chỉnh giá trị để chỉ định kích thước theo tỷ lệ phần trăm.

###  làm gì`PieSplitBy` control in a Pie of Pie chart?

 Các`PieSplitBy` thuộc tính kiểm soát cách phân chia biểu đồ hình tròn. Bạn có thể đặt nó thành một trong hai`PieSplitType.ByPercentage` hoặc`PieSplitType.ByValue` để chia biểu đồ theo tỷ lệ phần trăm hoặc theo một giá trị cụ thể tương ứng.

### Làm cách nào để đặt vị trí phần tách trong biểu đồ Pie of Pie?

Bạn có thể đặt vị trí của phần phân chia trong biểu đồ Pie of Pie bằng cách sử dụng`setPieSplitPosition` phương pháp. Điều chỉnh giá trị để xác định vị trí mong muốn.