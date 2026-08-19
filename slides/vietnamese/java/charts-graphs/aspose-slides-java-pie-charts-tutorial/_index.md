---
date: '2026-07-17'
description: Tìm hiểu cách xoay Pie Chart, tùy chỉnh màu sắc của Pie Chart và xuất
  slide sang PDF bằng Aspose.Slides for Java – hướng dẫn toàn diện về trực quan hoá
  dữ liệu.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Xoay Pie Chart và tùy chỉnh màu sắc của Pie Chart bằng Aspose.Slides
  for Java. Tìm hiểu cách xuất slide sang PDF và làm việc với chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Xoay Pie Chart và Tùy chỉnh Màu sắc trong Java – Hướng dẫn Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Cách xoay Pie Chart và tùy chỉnh màu sắc trong Java với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo Biểu Đồ Tròn với Aspose.Slides cho Java: Hướng Dẫn Toàn Diện

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **xoay biểu đồ tròn**, tùy chỉnh màu sắc cho từng lát cắt, và xuất slide cuối cùng ra PDF — tất cả đều sử dụng Aspose.Slides cho Java. Dù bạn đang xây dựng bảng điều khiển bán hàng, báo cáo tài chính, hay bất kỳ bản trình bày dựa trên dữ liệu nào, việc thành thạo các kỹ thuật này sẽ giúp bạn tạo ra những hình ảnh rõ ràng, bắt mắt mà không cần phụ thuộc vào Microsoft Office. Hãy chuẩn bị công cụ và bắt đầu ngay.

## Câu trả lời nhanh
- **Lớp nào khởi tạo một bản trình bày mới?** `Presentation` từ `com.aspose.slides`.
- **Lệnh API nào thêm biểu đồ tròn?** `slide.addChart(ChartType.Pie, …)`.
- **Làm sao để mỗi lát cắt có màu riêng?** Gọi `series.setColorVaried(true)` và đặt màu nền đặc cho từng điểm dữ liệu.
- **Phương thức nào xoay biểu đồ?** `chart.setRotationAngle(double)` – sử dụng giá trị độ từ 0 đến 360.
- **Slide có thể xuất ra PDF không?** Có, gọi `presentation.save("output.pdf", SaveFormat.Pdf)`.

## “Tùy chỉnh màu sắc biểu đồ tròn” là gì?
Tùy chỉnh màu sắc biểu đồ tròn có nghĩa là gán các màu nền khác nhau cho từng lát cắt của biểu đồ, giúp cải thiện khả năng đọc và tạo ấn tượng thị giác. Trong Aspose.Slides, bạn thực hiện điều này bằng cách bật màu đa dạng và sau đó đặt màu nền đặc cho từng điểm dữ liệu. Cách tiếp cận này đảm bảo mỗi phân đoạn dữ liệu nổi bật rõ ràng trong bản trình bày.

## Tại sao nên dùng Aspose.Slides cho Java để tạo biểu đồ tròn?
Aspose.Slides hỗ trợ **hơn 150 loại biểu đồ** và có thể render một bản trình bày 300 trang trong vòng **dưới 5 giây** trên máy chủ tiêu chuẩn, mà không cần cài đặt Microsoft Office. Thư viện chạy trên Windows, Linux và macOS, mang lại sự linh hoạt đa nền tảng cho bất kỳ dự án trực quan dữ liệu Java nào.

## Yêu cầu trước
- **Aspose.Slides cho Java** ≥ 25.4
- **JDK** 16 trở lên
- IDE như IntelliJ IDEA, Eclipse hoặc NetBeans
- Kiến thức cơ bản về Java và quen thuộc với Maven hoặc Gradle

## Cài đặt Aspose.Slides cho Java
Thêm thư viện vào cấu hình build của bạn.

**Maven**  
Thêm đoạn mã sau vào tệp `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Thêm phần sau vào tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp**  
Nếu bạn muốn cách tiếp cận thủ công, tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Các bước lấy giấy phép
- **Dùng thử miễn phí** – khám phá tất cả tính năng mà không tốn phí.  
- **Giấy phép tạm thời** – mở rộng giới hạn dùng thử trong thời gian ngắn.  
- **Mua bản quyền** – nhận giấy phép vĩnh viễn cho môi trường sản xuất.

**Khởi tạo và Cấu hình Cơ bản**  
Lớp `Presentation` đại diện cho một tệp PowerPoint trong bộ nhớ và cung cấp các phương thức để thao tác với các slide.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Hướng dẫn thực hiện
Dưới đây là quy trình từng bước, bao gồm mọi thứ từ tạo slide đến xoay biểu đồ tròn cuối cùng.

### Khởi tạo Presentation và Slide
Tạo một thể hiện `Presentation` mới và lấy slide đầu tiên làm canvas cho biểu đồ.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Thêm Biểu Đồ Tròn vào Slide
`addChart` thêm một hình dạng biểu đồ loại đã chỉ định vào slide tại tọa độ cho trước.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Đặt Tiêu Đề cho Biểu Đồ
`setTitle` gán tiêu đề văn bản cho biểu đồ và đặt nó ở vị trí trung tâm.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Cấu hình Nhãn Dữ Liệu cho Series
`setShowValue(true)` bật hiển thị nhãn giá trị số trên mỗi điểm dữ liệu của series.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Chuẩn bị Bảng Dữ Liệu cho Biểu Đồ
`ChartDataWorkbook` lưu trữ bảng dữ liệu nền mà cung cấp dữ liệu cho các series và danh mục của biểu đồ.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Thêm Danh Mục vào Biểu Đồ
`addCategory` tạo một nhãn danh mục mới cho series dữ liệu của biểu đồ.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Thêm Series và Điền Dữ Liệu cho Các Điểm
`addSeries` tạo một series dữ liệu, và `addDataPointForBarSeries` chèn giá trị số cho mỗi danh mục.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Tùy chỉnh Màu và Đường Viền cho Series
`setColorVaried(true)` bật màu đa dạng cho từng lát cắt, và `setFillFormat` gán màu nền đặc cho mỗi điểm dữ liệu.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Cấu hình Nhãn Dữ Liệu Tùy Chỉnh
`setDataLabelFormat` tùy chỉnh giao diện, vị trí và phông chữ của nhãn để chú thích biểu đồ rõ ràng hơn.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Đặt Góc Xoay và Lưu Presentation
`setRotationAngle` xoay toàn bộ biểu đồ tròn, và `save` ghi bản trình bày ra tệp.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Cách xoay biểu đồ tròn?
Tải đối tượng biểu đồ, gọi `chart.setRotationAngle(45.0)` (hoặc bất kỳ giá trị độ nào), sau đó lưu presentation. Việc xoay biểu đồ tròn thay đổi góc bắt đầu, cho phép bạn nhấn mạnh một lát cắt cụ thể mà không thay đổi dữ liệu. Lệnh duy nhất này hoạt động cho bất kỳ đối tượng `Chart` nào trong Aspose.Slides. Bạn cũng có thể kết hợp xoay với màu sắc đa dạng để thu hút sự chú ý đến điểm dữ liệu quan trọng nhất.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Các lát cắt đều có cùng màu** | `setColorVaried(true)` chưa được gọi | Đảm bảo bật màu đa dạng trên nhóm series. |
| **Nhãn dữ liệu không hiển thị** | Cờ `showValue` bị tắt | Gọi `setShowValue(true)` trên định dạng nhãn. |
| **Xoay không có hiệu lực** | Sử dụng phiên bản Aspose.Slides cũ | Nâng cấp lên phiên bản 25.4 hoặc mới hơn. |
| **Lỗi giấy phép khi chạy** | Thiếu hoặc file giấy phép không hợp lệ | Tải giấy phép bằng `License license = new License(); license.setLicense("Aspose.Slides.lic");` trước khi tạo `Presentation`. |

## Câu hỏi thường gặp

**H: Làm sao để lấy giấy phép Aspose.Slides cho Java?**  
Đ: Yêu cầu dùng thử miễn phí từ trang web Aspose, sau đó mua giấy phép vĩnh viễn. Tải giấy phép tại thời gian chạy như trong bảng “Các vấn đề thường gặp”.

**H: Có thể dùng mã này với các phiên bản JDK cũ hơn không?**  
Đ: API yêu cầu JDK 16 trở lên; các phiên bản cũ không được hỗ trợ.

**H: Có thể xuất biểu đồ dưới dạng hình ảnh thay vì PPTX không?**  
Đ: Có — sau khi render, gọi `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**H: Nếu cần hơn một series trong biểu đồ tròn thì sao?**  
Đ: Biểu đồ tròn chỉ hỗ trợ một series dữ liệu; nếu cần nhiều series, hãy xem xét sử dụng biểu đồ donut.

**H: Aspose.Slides có chạy trên máy chủ Linux không?**  
Đ: Chắc chắn — Aspose.Slides cho Java không phụ thuộc vào nền tảng và hoạt động trên bất kỳ hệ điều hành nào có JDK tương thích.

---

**Cập nhật lần cuối:** 2026-07-17  
**Kiểm tra với:** Aspose.Slides cho Java 25.4 (JDK 16)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Cách Tạo Biểu Đồ Tròn trong Bản Trình Bày Java bằng Aspose.Slides: Hướng Dẫn Toàn Diện](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Làm Chủ Biểu Đồ Tròn trong Java bằng Aspose.Slides: Hướng Dẫn Toàn Diện](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Xoay Văn Bản Biểu Đồ trong Java với Aspose.Slides: Hướng Dẫn Toàn Diện](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}