---
date: '2026-02-19'
description: Tìm hiểu cách tạo biểu đồ tròn trong Java với Aspose.Slides, tùy chỉnh
  màu sắc biểu đồ tròn, thêm chuỗi biểu đồ, làm việc với bảng dữ liệu biểu đồ và đặt
  góc quay.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Cách Tùy Chỉnh Màu Sắc Biểu Đồ Tròn trong Java với Aspose.Slides – Hướng Dẫn
  Toàn Diện
url: /vi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo Biểu Đồ Tròn với Aspose.Slides cho Java: Hướng Dẫn Toàn Diện

## Giới thiệu
Việc tạo các bản thuyết trình động và hấp dẫn về mặt hình ảnh là rất quan trọng để truyền tải thông tin một cách ấn tượng. Với Aspose.Slides cho Java, bạn có thể dễ dàng tích hợp các biểu đồ phức tạp như biểu đồ tròn vào slide, **tùy chỉnh màu sắc biểu đồ tròn**, và nâng cao khả năng trực quan hoá dữ liệu một cách nhẹ nhàng. Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước tạo và tùy chỉnh biểu đồ tròn bằng Aspose.Slides Java, giải quyết các thách thức thường gặp trong việc tạo bản thuyết trình một cách dễ dàng.

**Bạn sẽ học được:**
- Khởi tạo một bản thuyết trình và thêm slide.
- Tạo và cấu hình một biểu đồ tròn trên slide của bạn.
- Đặt tiêu đề biểu đồ, nhãn dữ liệu, và **tùy chỉnh màu sắc biểu đồ tròn**.
- Tối ưu hiệu năng và quản lý tài nguyên một cách hiệu quả.
- Tích hợp Aspose.Slides vào các dự án Java bằng Maven hoặc Gradle.

Hãy bắt đầu bằng cách đảm bảo bạn đã có đầy đủ công cụ và kiến thức cần thiết để làm theo!

## Câu trả lời nhanh
- **Lớp chính để bắt đầu một bản thuyết trình là gì?** `Presentation` từ `com.aspose.slides`.
- **Phương thức nào thêm biểu đồ tròn vào slide?** `addChart(ChartType.Pie, …)`.
- **Làm sao để bật màu sắc đa dạng cho mỗi lát?** Gọi `setColorVaried(true)` trên nhóm series.
- **Có thể xoay biểu đồ tròn không?** Có, sử dụng `setRotationAngle(double)` trên đối tượng chart.
- **Có cần giấy phép cho việc sử dụng trong môi trường production không?** Cần giấy phép Aspose.Slides cho các triển khai thương mại.

## “tùy chỉnh màu sắc biểu đồ tròn” là gì?
Tùy chỉnh màu sắc biểu đồ tròn có nghĩa là gán các màu nền riêng biệt cho mỗi lát của biểu đồ, giúp cải thiện khả năng đọc và tạo ấn tượng thị giác. Trong Aspose.Slides, bạn thực hiện điều này bằng cách bật màu sắc đa dạng và sau đó đặt màu nền rắn cho từng điểm dữ liệu.

## Tại sao nên dùng Aspose.Slides cho Java để tạo biểu đồ tròn?
- **Kiểm soát toàn diện** về giao diện biểu đồ mà không cần Microsoft Office.
- **Tương thích đa nền tảng** – hoạt động trên Windows, Linux và macOS.
- **API phong phú** cho việc ràng buộc dữ liệu, tạo kiểu và xuất ra PPTX, PDF hoặc hình ảnh.
- **Linh hoạt về giấy phép** – bắt đầu với bản dùng thử miễn phí và nâng cấp khi cần đầy đủ tính năng.

## Các điều kiện tiên quyết
Trước khi bắt đầu tutorial này, hãy chắc chắn rằng bạn đã chuẩn bị đầy đủ:

### Thư viện, phiên bản và phụ thuộc cần thiết
- **Aspose.Slides cho Java**: phiên bản 25.4 trở lên.
- **Java Development Kit (JDK)**: phiên bản 16 hoặc cao hơn.

### Yêu cầu thiết lập môi trường
- Một môi trường phát triển đã cài đặt và cấu hình Java.
- Một Integrated Development Environment (IDE) như IntelliJ IDEA, Eclipse hoặc NetBeans.

### Kiến thức nền tảng
- Hiểu biết cơ bản về lập trình Java.
- Quen thuộc với Maven hoặc Gradle để quản lý phụ thuộc.

## Cài đặt Aspose.Slides cho Java
Để bắt đầu sử dụng Aspose.Slides trong dự án Java của bạn, cần thêm thư viện làm phụ thuộc. Dưới đây là cách thực hiện với các công cụ xây dựng khác nhau:

**Maven**  
Thêm đoạn mã sau vào file `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Bao gồm đoạn sau trong file `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp**  
Nếu bạn không muốn dùng công cụ xây dựng, tải bản phát hành mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Các bước lấy giấy phép
- **Dùng thử miễn phí**: Bắt đầu với bản dùng thử để khám phá các tính năng của Aspose.Slides.  
- **Giấy phép tạm thời**: Nhận giấy phép tạm thời để sử dụng mở rộng mà không bị giới hạn.  
- **Mua bản quyền**: Xem xét mua nếu bạn cần truy cập lâu dài.

**Khởi tạo và thiết lập cơ bản**  
Để bắt đầu sử dụng Aspose.Slides, khởi tạo dự án của bạn bằng cách tạo một đối tượng presentation mới:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Hướng dẫn thực hiện
Bây giờ chúng ta sẽ chia quá trình thêm và tùy chỉnh biểu đồ tròn thành các bước dễ quản lý.

### Khởi tạo Presentation và Slide
Bắt đầu bằng việc tạo một bản thuyết trình mới và truy cập slide đầu tiên. Đây sẽ là canvas để tạo biểu đồ:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Thêm biểu đồ tròn vào Slide
Chèn một biểu đồ tròn vào vị trí chỉ định với bộ dữ liệu mặc định:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Đặt tiêu đề biểu đồ
Tùy chỉnh biểu đồ bằng cách đặt và căn giữa tiêu đề:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Cấu hình nhãn dữ liệu cho Series
Đảm bảo nhãn dữ liệu hiển thị giá trị để rõ ràng:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Chuẩn bị Worksheet dữ liệu cho biểu đồ
Thiết lập worksheet dữ liệu của biểu đồ bằng cách xóa các series và category hiện có:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Thêm Category vào biểu đồ
Xác định các category cho biểu đồ tròn:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Thêm Series và Điền dữ liệu cho các điểm
Tạo một series và điền dữ liệu cho các điểm – đây là nơi chúng ta **thêm series cho biểu đồ**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Tùy chỉnh màu và viền cho Series
Nâng cao tính thẩm mỹ bằng cách đặt màu và tùy chỉnh viền – việc này **tùy chỉnh màu sắc biểu đồ tròn**:
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

### Cấu hình nhãn dữ liệu tùy chỉnh
Tinh chỉnh nhãn cho mỗi điểm dữ liệu:
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

### Đặt góc xoay và lưu Presentation
Hoàn thiện biểu đồ tròn bằng **đặt góc xoay** và lưu file:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Các lát đều có cùng màu** | `setColorVaried(true)` chưa được gọi | Đảm bảo bạn đã bật màu sắc đa dạng trên nhóm series. |
| **Nhãn dữ liệu không hiển thị** | Cờ `showValue` bị tắt | Gọi `setShowValue(true)` trên định dạng nhãn tương ứng. |
| **Xoay không có hiệu lực** | Sử dụng phiên bản Aspose.Slides cũ | Nâng cấp lên phiên bản 25.4 hoặc mới hơn. |
| **Lỗi giấy phép khi chạy** | Thiếu hoặc file giấy phép không hợp lệ | Tải giấy phép bằng `License license = new License(); license.setLicense("Aspose.Slides.lic");` trước khi tạo `Presentation`. |

## Câu hỏi thường gặp

**H: Làm sao để lấy giấy phép Aspose.Slides cho Java?**  
Đ: Bạn có thể yêu cầu bản dùng thử miễn phí từ trang web Aspose, sau đó mua giấy phép vĩnh viễn. Tải giấy phép tại thời gian chạy như đã mô tả trong bảng Vấn đề thường gặp.

**H: Có thể dùng đoạn mã này với các phiên bản JDK cũ hơn không?**  
Đ: API yêu cầu JDK 16 hoặc cao hơn; các phiên bản cũ không được hỗ trợ.

**H: Có thể xuất biểu đồ dưới dạng hình ảnh thay vì PPTX không?**  
Đ: Có, gọi `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` sau khi render.

**H: Nếu cần thêm hơn một series vào biểu đồ tròn thì sao?**  
Đ: Biểu đồ tròn thường chỉ hiển thị một series; nếu muốn nhiều series, hãy xem xét sử dụng biểu đồ donut.

**H: Thư viện có hoạt động trên máy chủ Linux không?**  
Đ: Hoàn toàn có – Aspose.Slides cho Java không phụ thuộc vào nền tảng và chạy trên bất kỳ hệ điều hành nào có JDK tương thích.

---

**Cập nhật lần cuối:** 2026-02-19  
**Kiểm tra với:** Aspose.Slides cho Java 25.4 (jdk16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}