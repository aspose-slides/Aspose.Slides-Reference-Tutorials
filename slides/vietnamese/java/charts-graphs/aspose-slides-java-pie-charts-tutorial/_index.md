---
date: '2026-01-22'
description: Tìm hiểu cách tùy chỉnh màu sắc biểu đồ tròn và thêm tiêu đề biểu đồ
  bằng Aspose.Slides cho Java. Bao gồm cài đặt Maven Aspose Slides và cách lưu bản
  trình bày pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Cách tùy chỉnh màu sắc biểu đồ tròn trong Java với Aspose.Slides: Hướng dẫn
  đầy đủ'
url: /vi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ tròn với Aspose.Slides cho Java: Cách **tùy chỉnh màu sắc biểu đồ tròn** – Hướng dẫn đầy đủ

## Introduction
Việc truyền tải các câu chuyện dựa trên dữ liệu trong bài thuyết trình trở nên dễ dàng hơn khi bạn có thể **tùy chỉnh màu sắc biểu đồ tròn** để phù hợp với thương hiệu hoặc làm nổi bật các giá trị quan trọng. Trong hướng dẫn này, bạn sẽ thấy cách tạo biểu đồ tròn, thêm tiêu đề biểu đồ, làm việc với các điểm dữ liệu của biểu đồ tròn, và tinh chỉnh màu sắc của từng lát cắt bằng Aspose.Slides cho Java. Khi kết thúc, bạn cũng sẽ biết cách **lưu bản trình chiếu pptx** và tích hợp thư viện với Maven Aspose Slides.

**What You'll Learn**
- Cách tạo biểu đồ tròn (cách tạo pie) và thiết lập dự án Java.
- Các bước thêm tiêu đề biểu đồ và quản lý các điểm dữ liệu của biểu đồ tròn.
- Kỹ thuật **tùy chỉnh màu sắc biểu đồ tròn** để đạt hiệu quả hình ảnh tối đa.
- Cấu hình phụ thuộc Maven Aspose Slides.
- Lưu tệp cuối cùng dưới dạng bản trình chiếu PPTX.

Hãy bắt đầu!

## Quick Answers
- **Làm thế nào để thêm tiêu đề biểu đồ?** Sử dụng `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **Công cụ xây dựng nào hoạt động tốt nhất?** Cả Maven và Gradle đều được hỗ trợ; Maven Aspose Slides là phổ biến nhất.
- **Tôi có thể thay đổi màu sắc các lát cắt không?** Có—đặt `setColorVaried(true)` và điều chỉnh màu nền của mỗi `DataPoint`.
- **Tệp sẽ được lưu ở định dạng nào?** Sử dụng `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép vĩnh viễn cần thiết cho môi trường sản xuất.

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4 (phiên bản mới nhất được khuyến nghị).
- **JDK 16+** đã được cài đặt và cấu hình.
- Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans.
- Kiến thức cơ bản về Java và quen thuộc với Maven hoặc Gradle.

## Setting Up Aspose.Slides for Java
Để bắt đầu sử dụng Aspose.Slides, thêm thư viện vào dự án của bạn.

**Maven** (maven aspose slides)  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Nếu bạn không muốn sử dụng công cụ xây dựng, tải bản phát hành mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Free Trial** – bắt đầu thử nghiệm mà không cần giấy phép.
- **Temporary License** – kéo dài thời gian dùng thử.
- **Purchase** – mua giấy phép đầy đủ cho triển khai sản xuất.

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
Dưới đây là hướng dẫn từng bước giữ nguyên mã như thư viện gốc yêu cầu.

### Step 1: Initialize Presentation and Slide
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Step 2: Add a Pie Chart to the Slide
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Step 3: Add Chart Title
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Step 4: Show Data Labels for the First Series
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Step 5: Prepare the Chart Data Worksheet
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Step 6: Add Categories (pie chart data points)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Step 7: Add Series and Populate Data Points
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Step 8: **Customize Pie Chart Colors** – The Core of This Tutorial
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Step 9: Configure Custom Data Labels
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Step 10: Set Rotation Angle and **Save Presentation PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Common Issues & Troubleshooting
- **Màu sắc bị thiếu sau khi xuất** – Đảm bảo `setColorVaried(true)` được gọi trước khi chỉnh sửa các điểm dữ liệu riêng lẻ.
- **Các điểm dữ liệu không hiển thị** – Kiểm tra rằng các danh mục và chuỗi đã được xóa trước khi thêm mới (xem Bước 5).
- **Giấy phép chưa được áp dụng** – Tải tệp giấy phép của bạn trước khi tạo đối tượng `Presentation` để tránh dấu bản dùng thử.

## Frequently Asked Questions

**Q: Tôi có thể sử dụng mã này với các phiên bản JDK cũ hơn không?**  
A: Thư viện yêu cầu JDK 16 trở lên; các phiên bản cũ không được hỗ trợ.

**Q: Làm thế nào để thay đổi tiêu đề biểu đồ sau khi tạo?**  
A: Gọi `chart.getChartTitle().addTextFrameForOverriding("New Title")` và điều chỉnh định dạng văn bản nếu cần.

**Q: Có thể xuất sang các định dạng khác ngoài PPTX không?**  
A: Có—Aspose.Slides hỗ trợ PDF, ODP và một số định dạng hình ảnh thông qua enum `SaveFormat`.

**Q: Nếu tôi muốn tạo hoạt ảnh cho các lát cắt của biểu đồ tròn thì sao?**  
A: Sử dụng API `SlideShow` để thêm chuyển đổi slide hoặc hoạt ảnh hình dạng sau khi biểu đồ được tạo.

**Q: Phụ thuộc Maven có bao gồm tất cả các thư viện phụ thuộc không?**  
A: Artifact Maven Aspose Slides tự động kéo các phụ thuộc cần thiết; không cần bước bổ sung.

## Conclusion
Bây giờ bạn đã có một ví dụ đầy đủ, sẵn sàng cho môi trường sản xuất, cho thấy **cách tùy chỉnh màu sắc biểu đồ tròn**, thêm tiêu đề biểu đồ, làm việc với các điểm dữ liệu của biểu đồ tròn, và **lưu bản trình chiếu pptx** bằng Aspose.Slides cho Java. Hãy thoải mái thử nghiệm các bảng màu, bộ dữ liệu và góc quay khác nhau để phù hợp với phong cách thương hiệu của bạn.

---

**Cập nhật lần cuối:** 2026-01-22  
**Kiểm tra với:** Aspose.Slides 25.4 (JDK 16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}