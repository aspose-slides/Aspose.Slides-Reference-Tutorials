---
date: '2026-03-07'
description: Tìm hiểu cách tạo biểu đồ đường trong Java bằng Aspose.Slides, thêm tiêu
  đề biểu đồ, thêm đường lưới, định dạng nhãn biểu đồ và lưu các bản trình bày chuyên
  nghiệp.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Cách tạo biểu đồ đường bằng Aspose.Slides trong Java – Hướng dẫn toàn diện
url: /vi/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ đường bằng Aspose.Slides trong Java

## Cách tạo biểu đồ đường trong Java bằng Aspose.Slides

### Giới thiệu
Tạo các bản trình bày hấp dẫn về mặt hình ảnh là rất quan trọng để giao tiếp hiệu quả. Dù bạn là một chuyên gia kinh doanh hay một nhà giáo dục, bạn thường cần **tạo biểu đồ đường** có tính thông tin và thẩm mỹ. Trong hướng dẫn này, chúng ta sẽ đi qua cách sử dụng **Aspose.Slides for Java** để tạo một biểu đồ đường, thêm tiêu đề biểu đồ, thêm đường lưới, định dạng nhãn biểu đồ và lưu kết quả dưới dạng tệp PowerPoint.

#### Câu trả lời nhanh
- **Thư viện nào tốt nhất để tạo biểu đồ trong Java?** Aspose.Slides for Java
- **Loại biểu đồ nào mà hướng dẫn này tập trung?** Line chart with markers
- **Tôi có cần giấy phép để chạy mẫu không?** A free temporary license works for evaluation
- **IDE nào tôi có thể sử dụng?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- **Các thành phần biểu đồ được định dạng như thế nào?** Using fluent API calls for titles, axes, grid lines, legends, and backgrounds

### Biểu đồ đường là gì và tại sao nên sử dụng Aspose.Slides?
Biểu đồ đường hiển thị các điểm dữ liệu được nối bằng các đường thẳng, rất phù hợp để thể hiện xu hướng theo thời gian. Aspose.Slides cho phép bạn tạo và tùy chỉnh hoàn toàn các biểu đồ này một cách lập trình, loại bỏ nhu cầu chỉnh sửa PowerPoint thủ công.

### Yêu cầu trước
- **Java Development Kit (JDK) 8+** đã được cài đặt
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, v.v.)
- **Aspose.Slides for Java** library (được thêm qua Maven hoặc Gradle)

#### Thư viện và phụ thuộc cần thiết
**Maven**
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

Hoặc tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Cách nhận giấy phép
- Nhận giấy phép dùng thử miễn phí từ [free trial license](https://purchase.aspose.com/temporary-license/) để thử nghiệm.
- Mua giấy phép đầy đủ từ [Aspose's official site](https://purchase.aspose.com/buy) cho việc sử dụng trong môi trường sản xuất.

### Cài đặt Aspose.Slides for Java
1. **Thêm phụ thuộc** được hiển thị ở trên vào dự án của bạn.
2. **Áp dụng giấy phép** (nếu có) trước khi tạo bất kỳ đối tượng Presentation nào.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Triển khai từng bước

### Bước 1: Tạo thư mục đầu ra (tạo thư mục java)
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
*​Tại sao điều này quan trọng:* Đảm bảo thư mục tồn tại ngăn ngừa `FileNotFoundException` khi bạn lưu bản trình bày sau này.

### Bước 2: Thêm một slide và chèn biểu đồ đường
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
*​Giải thích:* Điều này tạo một slide mới và đặt **biểu đồ đường có dấu đánh dấu** tại tọa độ đã chỉ định.

### Bước 3: Thêm tiêu đề biểu đồ (add chart title)
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
*​Mẹo:* Sử dụng tiêu đề in đậm, màu xám giúp biểu đồ ngay lập tức nhận diện được.

### Bước 4: Định dạng trục và thêm đường lưới (add grid lines)
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
*​Tại sao điều này quan trọng:* Đường lưới rõ ràng và nhãn xoay giúp cải thiện khả năng đọc, đặc biệt khi các điểm dữ liệu dày đặc.

### Bước 5: Tùy chỉnh chú giải (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Bước 6: Đặt màu nền (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Bước 7: Lưu bản trình bày
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*​Kết quả:* Bây giờ bạn có một tệp PowerPoint (`FormattedChart_out.pptx`) chứa biểu đồ đường đã được định dạng hoàn chỉnh.

## Ứng dụng thực tế
- **Báo cáo kinh doanh:** Trình bày hiệu suất quý với các đường xu hướng.
- **Slide giáo dục:** Trực quan hoá dữ liệu khoa học cho bài giảng.
- **Đề xuất dự án:** Nổi bật các mốc quan trọng và dự báo.
- **Phân tích marketing:** Trình bày xu hướng ROI của chiến dịch.
- **Tích hợp Dashboard:** Xuất dữ liệu trực tiếp sang PowerPoint cho các buổi họp với các bên liên quan.

## Cân nhắc về hiệu năng
- **Quản lý bộ nhớ:** Luôn gọi `dispose()` trên đối tượng `Presentation` để giải phóng tài nguyên gốc kịp thời.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Giấy phép chưa được áp dụng** | Tải giấy phép dùng thử/đầy đủ trước khi tạo bất kỳ đối tượng `Presentation` nào. |
| **Biểu đồ hiển thị trống** | Kiểm tra xem slide thực sự có chứa chuỗi dữ liệu; thêm chuỗi nếu cần. |
| **Tệp không được lưu** | Đảm bảo thư mục đầu ra tồn tại (sử dụng bước “create directory java”). |
| **Màu sắc không được áp dụng** | Sử dụng hằng số `Color` từ `java.awt.Color` hoặc `PresetColor`. |

## Câu hỏi thường gặp

**Q: Tôi có thể tạo các loại biểu đồ khác ngoài biểu đồ đường không?**  
A: Có, Aspose.Slides hỗ trợ biểu đồ cột, bánh, phân tán và nhiều loại biểu đồ khác.

**Q: Làm thế nào để tôi thêm nhiều chuỗi dữ liệu vào biểu đồ đường?**  
A: Sử dụng `chart.getChartData().getSeries().add(...)` để chèn thêm chuỗi trước khi định dạng.

**Q: Có thể xuất biểu đồ dưới dạng hình ảnh không?**  
A: Chắc chắn. Gọi `chart.getChartData().getChartDataWorkbook().save(...)` hoặc render slide sang định dạng hình ảnh.

**Q: Tôi có cần giấy phép trả phí cho việc phát triển không?**  
A: Giấy phép tạm thời miễn phí hoạt động cho việc đánh giá; giấy phép thương mại là bắt buộc cho triển khai sản xuất.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Thư viện hoạt động với JDK 8 đến JDK 22 (sử dụng classifier phù hợp, ví dụ `jdk16`).

---

**Cập nhật lần cuối:** 2026-03-07  
**Kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}