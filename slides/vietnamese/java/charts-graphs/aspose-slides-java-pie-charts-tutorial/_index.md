---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ hình tròn bằng Aspose.Slides for Java. Hướng dẫn này bao gồm mọi thứ từ thiết lập đến tùy chỉnh nâng cao."
"title": "Tạo biểu đồ hình tròn trong Java với Aspose.Slides&#58; Hướng dẫn toàn diện"
"url": "/vi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo biểu đồ hình tròn với Aspose.Slides cho Java: Hướng dẫn đầy đủ

## Giới thiệu
Tạo các bài thuyết trình năng động và hấp dẫn về mặt hình ảnh là rất quan trọng để truyền tải thông tin có tác động. Với Aspose.Slides for Java, bạn có thể tích hợp liền mạch các biểu đồ phức tạp như biểu đồ hình tròn vào slide của mình, nâng cao khả năng trực quan hóa dữ liệu một cách dễ dàng. Hướng dẫn toàn diện này sẽ hướng dẫn bạn quy trình tạo và tùy chỉnh biểu đồ hình tròn bằng Aspose.Slides Java, giải quyết các thách thức trình bày phổ biến một cách dễ dàng.

**Những gì bạn sẽ học được:**
- Khởi tạo bài thuyết trình và thêm slide.
- Tạo và cấu hình biểu đồ hình tròn trên trang chiếu của bạn.
- Đặt tiêu đề biểu đồ, nhãn dữ liệu và màu sắc.
- Tối ưu hóa hiệu suất và quản lý tài nguyên hiệu quả.
- Tích hợp Aspose.Slides vào các dự án Java bằng Maven hoặc Gradle.

Hãy bắt đầu bằng cách đảm bảo bạn có đủ các công cụ và kiến thức cần thiết để thực hiện!

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo rằng bạn đã chuẩn bị sẵn các thiết lập sau:

### Thư viện, Phiên bản và Phụ thuộc bắt buộc
- **Aspose.Slides cho Java**: Đảm bảo bạn có phiên bản 25.4 trở lên.
- **Bộ phát triển Java (JDK)**: Yêu cầu sử dụng phiên bản 16 trở lên.

### Yêu cầu thiết lập môi trường
- Môi trường phát triển có cài đặt và cấu hình Java.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA, Eclipse hoặc NetBeans.

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình Java.
- Quen thuộc với Maven hoặc Gradle để quản lý sự phụ thuộc.

## Thiết lập Aspose.Slides cho Java
Để bắt đầu sử dụng Aspose.Slides trong các dự án Java của bạn, bạn cần thêm thư viện dưới dạng phụ thuộc. Sau đây là cách bạn có thể thực hiện bằng các công cụ xây dựng khác nhau:

**Maven**
Thêm đoạn trích này vào `pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Tốt nghiệp**
Bao gồm những điều sau đây trong `build.gradle` tài liệu:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp**
Nếu bạn không muốn sử dụng công cụ xây dựng, hãy tải xuống bản phát hành mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Các bước xin cấp giấy phép
- **Dùng thử miễn phí**: Bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để sử dụng lâu dài mà không bị giới hạn.
- **Mua**: Hãy cân nhắc mua nếu bạn cần truy cập lâu dài.

**Khởi tạo và thiết lập cơ bản**
Để bắt đầu sử dụng Aspose.Slides, hãy khởi tạo dự án của bạn bằng cách tạo một đối tượng trình bày mới:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Hướng dẫn thực hiện
Bây giờ chúng ta hãy chia nhỏ quá trình thêm và tùy chỉnh biểu đồ hình tròn thành các bước dễ quản lý.

### Khởi tạo bài trình bày và slide
Bắt đầu bằng cách thiết lập một bài thuyết trình mới và truy cập vào trang chiếu đầu tiên. Đây là khung vẽ để tạo biểu đồ:
```java
import com.aspose.slides.*;

// Tạo một phiên bản trình bày mới.
Presentation presentation = new Presentation();
// Truy cập vào trang chiếu đầu tiên trong bài thuyết trình.
islide slides = presentation.getSlides().get_Item(0);
```

### Thêm biểu đồ hình tròn vào trang chiếu
Chèn biểu đồ hình tròn vào vị trí đã chỉ định với tập dữ liệu mặc định:
```java
import com.aspose.slides.*;

// Thêm biểu đồ hình tròn ở vị trí (100, 100) với kích thước (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Đặt tiêu đề biểu đồ
Tùy chỉnh biểu đồ của bạn bằng cách đặt và căn giữa tiêu đề:
```java
import com.aspose.slides.*;

// Thêm tiêu đề vào biểu đồ hình tròn.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Cấu hình nhãn dữ liệu cho Series
Đảm bảo rằng nhãn dữ liệu hiển thị giá trị rõ ràng:
```java
import com.aspose.slides.*;

// Hiển thị giá trị dữ liệu trên chuỗi đầu tiên.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Chuẩn bị bảng tính dữ liệu biểu đồ
Thiết lập bảng tính dữ liệu của biểu đồ bằng cách xóa các chuỗi và danh mục hiện có:
```java
import com.aspose.slides.*;

// Chuẩn bị sổ làm việc dữ liệu biểu đồ.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Thêm danh mục vào biểu đồ
Xác định danh mục cho biểu đồ hình tròn của bạn:
```java
import com.aspose.slides.*;

// Thêm danh mục mới.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Thêm Chuỗi và Điền Điểm Dữ Liệu
Tạo một chuỗi và điền các điểm dữ liệu vào đó:
```java
import com.aspose.slides.*;

// Thêm một series mới và đặt tên cho series đó.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Tùy chỉnh màu sắc và đường viền của Series
Tăng cường sức hấp dẫn về mặt thị giác bằng cách thiết lập màu sắc và tùy chỉnh đường viền:
```java
import com.aspose.slides.*;

// Thiết lập nhiều màu sắc khác nhau cho các phần của chuỗi.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Lặp lại với các điểm dữ liệu khác có màu sắc và kiểu dáng khác nhau.
```

### Cấu hình nhãn dữ liệu tùy chỉnh
Tinh chỉnh nhãn cho từng điểm dữ liệu:
```java
import com.aspose.slides.*;

// Cấu hình nhãn tùy chỉnh.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Bật đường dẫn cho nhãn.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Đặt góc quay và lưu bản trình bày
Hoàn thiện biểu đồ hình tròn của bạn bằng cách thiết lập góc xoay và lưu bản trình bày:
```java
import com.aspose.slides.*;

// Đặt góc quay.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Lưu bài thuyết trình vào một tập tin.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách tạo và tùy chỉnh biểu đồ hình tròn bằng Aspose.Slides for Java. Bằng cách làm theo các bước này, bạn có thể nâng cao bài thuyết trình của mình bằng hình ảnh dữ liệu hấp dẫn trực quan. Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, vui lòng liên hệ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}