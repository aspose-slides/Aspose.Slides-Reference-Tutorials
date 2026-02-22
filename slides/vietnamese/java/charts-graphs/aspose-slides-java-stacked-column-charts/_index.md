---
date: '2026-02-22'
description: Tìm hiểu cách tạo biểu đồ cột chồng trong Java bằng Aspose.Slides. Hướng
  dẫn này bao gồm phụ thuộc Aspose Slides Maven, thêm biểu đồ chồng phần trăm, định
  dạng nhãn dữ liệu biểu đồ và lưu bản trình bày dưới dạng PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Cách tạo biểu đồ cột chồng trong Java với Aspose.Slides – Hướng dẫn toàn diện
url: /vi/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

 sure no extra spaces or missing elements.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ cột chồng trong Java với Aspose.Slides – Hướng dẫn toàn diện

## Giới thiệu

Nâng cao các bản trình bày của bạn bằng cách tích hợp các biểu đồ dữ liệu sâu sắc với sức mạnh của Aspose.Slides cho Java. Trong hướng dẫn này, bạn sẽ **tạo biểu đồ cột chồng** trên các slide trông chuyên nghiệp, dù bạn đang chuẩn bị báo cáo kinh doanh hay trình bày thống kê dự án. Khi kết thúc bài học, bạn sẽ có thể:

- Cài đặt môi trường với phụ thuộc Maven của Aspose Slides
- Tạo một bản trình bày từ đầu
- **Thêm biểu đồ cột chồng phần trăm** và tùy chỉnh giao diện
- **Định dạng nhãn dữ liệu của biểu đồ** và **thay đổi định dạng trục dọc**
- **Lưu bản trình bày dưới dạng PPTX** chỉ bằng một dòng lệnh

Hãy cùng đi qua từng bước để bạn có thể bắt đầu tạo các bản trình bày ấn tượng ngay lập tức.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** phụ thuộc Maven/Gradle `aspose-slides` (xem “aspose slides maven dependency” bên dưới)  
- **Loại biểu đồ nào được sử dụng?** `ChartType.PercentsStackedColumn` cho biểu đồ cột chồng phần trăm  
- **Làm thế nào để thay đổi định dạng số của trục?** Sử dụng `IAxis.setNumberFormat()` và tắt việc liên kết với nguồn  
- **Có thể tùy chỉnh nhãn dữ liệu không?** Có – duyệt qua các đối tượng `IChartDataPoint` và đặt một `ITextFrame` tùy chỉnh  
- **Làm thế nào để lưu file?** Gọi `presentation.save("output.pptx", SaveFormat.Pptx)`

## Biểu đồ cột chồng là gì?
Biểu đồ cột chồng hiển thị nhiều chuỗi dữ liệu được xếp chồng lên nhau trong các cột dọc. Khi bạn sử dụng biến thể **cột chồng phần trăm**, mỗi cột luôn tổng cộng 100 %, giúp dễ dàng so sánh tỷ lệ đóng góp giữa các danh mục.

## Tại sao nên sử dụng Aspose.Slides cho Java?
Aspose.Slides cung cấp một API thuần Java hoạt động trên bất kỳ nền tảng nào mà không cần cài đặt Microsoft Office. Nó cho phép kiểm soát chi tiết các đối tượng biểu đồ, hỗ trợ nhiều định dạng, và cho phép bạn tạo bản trình bày một cách lập trình—lý tưởng cho báo cáo tự động hoặc tạo tài liệu phía máy chủ.

## Yêu cầu trước
- **Java Development Kit (JDK):** 8 trở lên  
- **IDE:** IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào tương thích Java  
- **Công cụ xây dựng:** Maven hoặc Gradle (tùy chọn nhưng khuyến nghị)  
- **Kiến thức Java cơ bản** – bạn nên quen thuộc với các lớp và phương thức  

## Cài đặt Aspose.Slides cho Java
Để bắt đầu, thêm thư viện Aspose.Slides vào dự án của bạn.

### Phụ thuộc Maven của Aspose Slides
Thêm đoạn sau vào file `pom.xml` của bạn (đây là **aspose slides maven dependency** bạn cần):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Thay thế Gradle
Nếu bạn thích Gradle, thêm dòng sau vào `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cách lấy giấy phép
Bạn có thể bắt đầu với bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Để loại bỏ các giới hạn đánh giá, hãy cân nhắc lấy giấy phép tạm thời hoặc mua bản quyền.

- **Dùng thử miễn phí:** Truy cập các tính năng giới hạn mà không tốn phí ngay lập tức.  
- **Giấy phép tạm thời:** Yêu cầu qua [trang của Aspose](https://purchase.aspose.com/temporary-license/).  
- **Mua bản quyền:** Truy cập trang mua để có toàn quyền truy cập.

### Khởi tạo cơ bản
Đây là đoạn mã tối thiểu cho thấy cách tạo một đối tượng `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Hướng dẫn thực hiện

### Tạo bản trình bày và thêm slide
**Tổng quan:**  
Đầu tiên, chúng ta sẽ tạo một bản trình bày trống và xác nhận rằng một slide đã tồn tại.

#### Bước 1: Khởi tạo đối tượng Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Bước 2: Lưu bản trình bày
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Thêm biểu đồ cột chồng phần trăm vào slide
**Tổng quan:**  
Bây giờ chúng ta sẽ đặt một **biểu đồ cột chồng phần trăm** lên slide đầu tiên.

#### Bước 1: Khởi tạo và truy cập Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Bước 2: Thêm biểu đồ vào Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Tùy chỉnh định dạng số của trục biểu đồ
**Tổng quan:**  
Để dễ đọc hơn, chúng ta sẽ **thay đổi định dạng trục dọc** để hiển thị phần trăm.

#### Bước 1: Thêm và truy cập biểu đồ
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Bước 2: Đặt định dạng số tùy chỉnh
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Thêm chuỗi và điểm dữ liệu vào biểu đồ
**Tổng quan:**  
Chúng ta sẽ điền dữ liệu mẫu vào biểu đồ.

#### Bước 1: Khởi tạo Presentation và biểu đồ
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Bước 2: Thêm chuỗi dữ liệu
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Định dạng màu nền cho chuỗi
**Tổng quan:**  
Đặt màu riêng cho mỗi chuỗi để biểu đồ dễ đọc hơn.

#### Bước 1: Khởi tạo và truy cập biểu đồ
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Bước 2: Đặt màu nền
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Định dạng nhãn dữ liệu
**Tổng quan:**  
Bây giờ chúng ta sẽ **định dạng nhãn dữ liệu của biểu đồ** để chúng hiển thị văn bản tùy chỉnh.

#### Bước 1: Truy cập chuỗi biểu đồ và các điểm dữ liệu
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Bước 2: Tùy chỉnh nhãn dữ liệu
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Các vấn đề thường gặp và giải pháp
- **Biểu đồ trống:** Đảm bảo bạn đã thêm ít nhất một chuỗi dữ liệu và điểm dữ liệu trước khi lưu.  
- **Số trên trục không hiển thị phần trăm:** Nhớ đặt `verticalAxis.setNumberFormatLinkedToSource(false)`; nếu không, định dạng tùy chỉnh sẽ bị bỏ qua.  
- **Thông báo đánh giá giấy phép:** Áp dụng file giấy phép hợp lệ trước khi tạo đối tượng `Presentation` để loại bỏ banner đánh giá.

## Câu hỏi thường gặp

**Hỏi: Tôi có thể dùng mã này với Java 11 hoặc mới hơn không?**  
**Đáp:** Có. Thư viện hỗ trợ JDK 8+; chỉ cần dùng classifier phù hợp (ví dụ, `jdk16` cho JDK 16 trở lên).

**Hỏi: Làm sao để xuất biểu đồ dưới dạng hình ảnh thay vì PPTX?**  
**Đáp:** Sử dụng `chart.getImage().save("chart.png", ImageFormat.Png);` sau khi đã thêm biểu đồ vào slide.

**Hỏi: Có thể thêm chú giải (legend) vào biểu đồ cột chồng không?**  
**Đáp:** Chắc chắn. Gọi `chart.getChartTitle().addTextFrameForOverriding("My Chart");` và cấu hình `chart.getLegend()` theo nhu cầu.

**Hỏi: Nếu cần cập nhật dữ liệu sau khi bản trình bày đã được tạo thì sao?**  
**Đáp:** Bạn có thể sửa các ô trong `ChartDataWorkbook` rồi gọi `chart.refresh();` để cập nhật.

**Hỏi: Aspose.Slides có hoạt động trên máy chủ Linux không?**  
**Đáp:** Có. Thư viện thuần Java và chạy trên bất kỳ hệ điều hành nào có JRE tương thích.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách **tạo biểu đồ cột chồng** trong các bản trình bày với Aspose.Slides cho Java, từ cài đặt môi trường đến tinh chỉnh phong cách hình ảnh. Hãy thử nghiệm với các bộ dữ liệu, màu sắc và định dạng nhãn khác nhau để báo cáo của bạn thực sự nổi bật.

---

**Cập nhật lần cuối:** 2026-02-22  
**Đã kiểm tra với:** Aspose.Slides 25.4 (classifier jdk16)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}