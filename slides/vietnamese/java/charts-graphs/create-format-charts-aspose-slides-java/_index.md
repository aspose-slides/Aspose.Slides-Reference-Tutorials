---
date: '2026-08-27'
description: Tìm hiểu cách thêm đường lưới vào biểu đồ trong Java bằng Aspose.Slides,
  định dạng các trục, tiêu đề và xuất biểu đồ đường PowerPoint chuyên nghiệp.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Tìm hiểu cách thêm đường lưới vào biểu đồ trong Java bằng Aspose.Slides,
  định dạng các trục, tiêu đề và xuất biểu đồ đường PowerPoint chuyên nghiệp.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Cách thêm các đường lưới vào biểu đồ với Aspose.Slides cho Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Cách thêm các đường lưới vào biểu đồ với Aspose.Slides cho Java
url: /vi/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm các đường lưới vào biểu đồ với Aspose.Slides cho Java

## Giới thiệu
Nếu bạn cần **thêm các đường lưới vào biểu đồ** trong một bản trình bày PowerPoint một cách lập trình, Aspose.Slides cho Java cung cấp cho bạn một API sạch sẽ, đầy đủ tính năng. Dù bạn đang chuẩn bị báo cáo kinh doanh hàng quý, một buổi giảng học thuật, hay một bộ slide bán hàng dựa trên dữ liệu, bạn có thể tạo một biểu đồ đường, tùy chỉnh mọi yếu tố trực quan, và lưu kết quả trong vài giây — mà không cần mở PowerPoint thủ công.

## Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ trong Java?** Aspose.Slides for Java.
- **Loại biểu đồ nào mà hướng dẫn này đề cập?** A line chart with markers and grid lines.
- **Tôi có cần giấy phép để chạy mẫu không?** A free temporary license works for evaluation; a commercial license is required for production.
- **IDE nào tôi có thể sử dụng?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
- **Các yếu tố biểu đồ được định dạng như thế nào?** Using fluent API calls for titles, axes, grid lines, legends, and background colors.

## Cách thêm biểu đồ đường lưới trong Java bằng Aspose.Slides
Tải một `Presentation` mới, chèn một slide, thêm một biểu đồ đường, và sau đó bật các đường lưới chính trên trục dọc — tất cả trong chưa đầy mười dòng mã. Câu trả lời trực tiếp này cho thấy chuỗi chính xác bạn cần, vì vậy bạn có thể sao chép‑dán và ngay lập tức thấy một biểu đồ được định dạng đầy đủ.

### Mục định nghĩa
`Presentation` là lớp cốt lõi của Aspose.Slides đại diện cho một tệp PowerPoint trong bộ nhớ; tất cả các thao tác ở mức slide đều bắt đầu từ đối tượng này.

## Biểu đồ đường là gì và tại sao sử dụng Aspose.Slides?
Biểu đồ đường vẽ một chuỗi các điểm dữ liệu được nối bằng các đường thẳng, làm cho các xu hướng theo thời gian ngay lập tức hiển thị. Aspose.Slides hỗ trợ **hơn 50 loại biểu đồ** và có thể xử lý **lên tới 10.000 điểm dữ liệu mỗi chuỗi** mà không gây chậm đáng kể, mang lại hiệu năng cấp doanh nghiệp cho các bộ dữ liệu lớn.

### Mục định nghĩa
`Chart` là đối tượng cấp cao nhất của Aspose.Slides cho bất kỳ biểu đồ nào; nó lưu trữ các chuỗi, danh mục và thông tin định dạng.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** đã được cài đặt.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, v.v.).
- **Aspose.Slides for Java** thư viện được thêm qua Maven hoặc Gradle (xem phần *aspose.slides maven dependency* bên dưới).

### Phụ thuộc Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Phụ thuộc Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Ngoài ra, tải xuống JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## Mua giấy phép (áp dụng giấy phép aspose)
- Nhận **giấy phép dùng thử miễn phí** từ trang [free trial license](https://purchase.aspose.com/temporary-license/) để thử nghiệm.
- Mua giấy phép đầy đủ từ [Aspose's official site](https://purchase.aspose.com/buy) cho việc triển khai sản xuất.

## Cài đặt Aspose.Slides cho Java
1. Thêm phụ thuộc Maven hoặc Gradle đã hiển thị ở trên vào dự án của bạn.
2. Tải tệp giấy phép **trước** khi tạo bất kỳ đối tượng `Presentation` nào để mọi tính năng được mở khóa.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Triển khai từng bước

### Bước 1: tạo thư mục đầu ra (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Tiêu đề:* Đảm bảo thư mục tồn tại ngăn ngừa `FileNotFoundException` khi bạn lưu bản trình bày sau này.

### Bước 2: thêm một slide và chèn biểu đồ đường
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Giải thích:* Điều này tạo một slide mới và đặt một **biểu đồ đường với các điểm đánh dấu** tại các tọa độ được chỉ định.

### Bước 3: thêm tiêu đề biểu đồ
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*Mẹo:* Sử dụng tiêu đề in đậm, màu xám giúp biểu đồ ngay lập tức nhận dạng được.

### Bước 4: định dạng trục và thêm các đường lưới
#### Định dạng trục dọc
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Tiêu đề:* Các đường lưới rõ ràng và nhãn xoay cải thiện khả năng đọc, đặc biệt khi các điểm dữ liệu dày đặc.

#### Định dạng trục ngang
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Bước 5: tùy chỉnh chú giải
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Bước 6: đặt màu nền
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Bước 7: lưu bản trình bày
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Kết quả:* Bây giờ bạn có một tệp PowerPoint (`FormattedChart_out.pptx`) chứa một biểu đồ đường được định dạng đầy đủ.

## Ứng dụng thực tiễn (generate line chart powerpoint)
- **Báo cáo kinh doanh:** Hiển thị xu hướng doanh thu hàng quý với các đường lưới sắc nét.
- **Bài giảng học thuật:** Trực quan hoá dữ liệu thí nghiệm qua nhiều buổi.
- **Đề xuất dự án:** Nổi bật tiến độ các mốc và các đường dự báo.
- **Phân tích tiếp thị:** Trình bày xu hướng ROI của chiến dịch cạnh tranh song song với dữ liệu đối thủ.
- **Tích hợp Dashboard:** Xuất phân tích trực tiếp sang PowerPoint cho các cuộc họp với các bên liên quan.

## Xem xét hiệu năng
- **Quản lý bộ nhớ:** Gọi `presentation.dispose()` sau khi lưu để giải phóng nhanh các tài nguyên gốc.
- **Bộ dữ liệu lớn:** Aspose.Slides xử lý biểu đồ với hàng nghìn điểm bằng cách streaming, giữ mức sử dụng bộ nhớ dưới 100 MB trên một máy chủ điển hình.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Chưa áp dụng giấy phép** | Tải giấy phép dùng thử hoặc đầy đủ **trước** khi bất kỳ đối tượng `Presentation` nào được khởi tạo. |
| **Biểu đồ hiển thị trống** | Kiểm tra xem slide có ít nhất một chuỗi dữ liệu; thêm chuỗi qua `chart.getChartData().getSeries().add(...)` nếu cần. |
| **Tệp không được lưu** | Đảm bảo thư mục đầu ra tồn tại (xem Bước 1). |
| **Màu sắc không được áp dụng** | Sử dụng hằng số `java.awt.Color` hoặc enum `PresetColor` để hiển thị màu một cách đáng tin cậy. |

## Câu hỏi thường gặp

**Q: Tôi có thể tạo các loại biểu đồ khác ngoài biểu đồ đường không?**  
A: Có, Aspose.Slides hỗ trợ biểu đồ cột, tròn, phân tán, radar, và hơn 50 loại biểu đồ bổ sung.

**Q: Làm thế nào để tôi thêm nhiều chuỗi dữ liệu vào biểu đồ đường?**  
A: Sử dụng `chart.getChartData().getSeries().add(...)` để chèn các chuỗi bổ sung trước khi áp dụng định dạng.

**Q: Có thể xuất biểu đồ dưới dạng hình ảnh không?**  
A: Chắc chắn. Render slide thành PNG, JPEG, hoặc SVG bằng `presentation.save("slide.png", SaveFormat.Png)`.

**Q: Tôi có cần giấy phép trả phí cho việc phát triển không?**  
A: Giấy phép tạm thời miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho việc sử dụng trong môi trường sản xuất.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Thư viện hoạt động với JDK 8 đến JDK 22; chọn classifier phù hợp (ví dụ, `jdk16`) khi thêm phụ thuộc Maven/Gradle.

---

**Cập nhật lần cuối:** 2026-08-27  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Hướng dẫn liên quan
- [aspose slides maven dependency: Thêm và Cấu hình Biểu đồ trong Bài thuyết trình bằng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Cách Thêm Biểu đồ vào PowerPoint bằng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Tạo và Tùy chỉnh Đường xu hướng cho Biểu đồ Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}