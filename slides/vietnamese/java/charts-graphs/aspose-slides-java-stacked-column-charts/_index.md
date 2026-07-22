---
date: '2026-07-22'
description: Tìm hiểu Aspose Slides Maven Dependency để tạo biểu đồ cột chồng trong
  Java, thêm nhãn dữ liệu, thay đổi định dạng số của trục dọc và xuất kết quả dưới
  dạng tệp PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency cho phép bạn xây dựng biểu đồ cột chồng
  trong Java, tùy chỉnh nhãn dữ liệu, điều chỉnh định dạng trục dọc và lưu dưới dạng
  PPTX – tất cả với mã ngắn gọn, sẵn sàng cho sản xuất.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Biểu đồ cột chồng trong Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Biểu đồ cột chồng trong Java'
url: /vi/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Biểu đồ Cột chồng trong Java

## Giới thiệu

Nâng cao các bản trình bày của bạn bằng cách tích hợp các hình ảnh dữ liệu sâu sắc với sức mạnh của **Aspose.Slides for Java**. Trong hướng dẫn này, bạn sẽ **tạo một biểu đồ cột chồng** trông chuyên nghiệp, dù bạn đang chuẩn bị báo cáo kinh doanh hay trình bày thống kê dự án. Khi hoàn thành tutorial này, bạn sẽ có thể:

- Thiết lập môi trường với **phụ thuộc Aspose Slides Maven**
- Tạo một bản trình bày từ đầu
- **Thêm biểu đồ cột chồng phần trăm** và tùy chỉnh giao diện
- **Định dạng nhãn dữ liệu biểu đồ** và **thay đổi định dạng số trục tung**
- **Lưu bản trình bày dưới dạng PPTX** chỉ bằng một dòng lệnh

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Thêm phụ thuộc `aspose-slides` cho Maven/Gradle (xem “Aspose Slides Maven Dependency” bên dưới).  
- **Loại biểu đồ nào tạo dạng chồng?** Sử dụng `ChartType.PercentsStackedColumn` cho biểu đồ cột chồng phần trăm.  
- **Làm sao thay đổi định dạng số của trục?** Gọi `IAxis.setNumberFormat()` và đặt `setNumberFormatLinkedToSource(false)`.  
- **Có thể tùy chỉnh nhãn dữ liệu không?** Có – lặp qua từng `IChartDataPoint` và gán một `ITextFrame` tùy chỉnh.  
- **Làm sao lưu file?** Gọi `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Biểu đồ cột chồng là gì?
Biểu đồ cột chồng hiển thị nhiều chuỗi dữ liệu được xếp chồng lên nhau theo chiều dọc trong mỗi cột danh mục, với biến thể **phần trăm‑chồng** chuẩn hoá mỗi cột về 100 % để so sánh tỷ lệ dễ dàng. Định dạng này cho phép người xem nhanh chóng đánh giá cách mỗi thành phần đóng góp vào tổng thể qua các danh mục khác nhau, làm cho xu hướng và kích thước tương đối trở nên rõ ràng ngay lập tức.

## Tại sao sử dụng Aspose.Slides cho Java?
Aspose.Slides cho Java cho phép bạn tạo, chỉnh sửa và chuyển đổi các tệp PowerPoint **không cần Microsoft Office** và hỗ trợ **hơn 50 định dạng xuất** trên Windows, Linux và macOS. Thư viện chạy hoàn toàn trên JRE, cho phép tự động hoá phía máy chủ và báo cáo hiệu suất cao. Nó cũng cung cấp quyền kiểm soát chi tiết đối với các đối tượng biểu đồ, bố cục slide và thuộc tính tài liệu, rất phù hợp cho việc tạo bản trình bày cấp doanh nghiệp.

## Yêu cầu trước
- **Java Development Kit (JDK):** 8 trở lên  
- **IDE:** IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo Java nào tương thích  
- **Công cụ xây dựng:** Maven hoặc Gradle (không bắt buộc nhưng khuyến nghị)  
- **Kiến thức Java cơ bản** – bạn nên quen thuộc với lớp và phương thức  

## Cài đặt Aspose.Slides cho Java
Để bắt đầu, thêm thư viện Aspose.Slides vào dự án của bạn.

### Aspose Slides Maven Dependency
Thêm đoạn sau vào `pom.xml` (đây là **aspose slides maven dependency** bạn cần):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Thay thế Gradle
Nếu bạn thích Gradle, bao gồm dòng này trong `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải xuống trực tiếp
Hoặc tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Nhận giấy phép
Bạn có thể bắt đầu với bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides. Để loại bỏ các hạn chế đánh giá, hãy cân nhắc mua hoặc nhận giấy phép tạm thời.

- **Dùng thử miễn phí:** Truy cập các tính năng giới hạn mà không tốn chi phí ngay lập tức.  
- **Giấy phép tạm thời:** Yêu cầu qua [trang của Aspose](https://purchase.aspose.com/temporary-license/).  
- **Mua bản quyền:** Truy cập trang mua để có đầy đủ quyền truy cập.

### Khởi tạo cơ bản
`Presentation` là lớp cốt lõi của Aspose.Slides đại diện cho một tệp PowerPoint trong bộ nhớ. Đoạn mã tối thiểu sau cho thấy cách tạo một đối tượng `Presentation`:

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

## Hướng dẫn triển khai

### Tạo bản trình bày và Thêm slide
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

### Thêm biểu đồ Cột chồng phần trăm vào Slide
**Tổng quan:**  
Bây giờ chúng ta sẽ đặt **biểu đồ cột chồng phần trăm** lên slide đầu tiên.

`ChartType.PercentsStackedColumn` chỉ định loại biểu đồ cột chồng phần trăm.

#### Bước 1: Khởi tạo và Truy cập Slide
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

### Tùy chỉnh định dạng số trục biểu đồ
**Tổng quan:**  
Để dễ đọc hơn, chúng ta sẽ **thay đổi định dạng trục tung** để hiển thị phần trăm.

`IAxis` là giao diện đại diện cho một trục biểu đồ, cho phép điều chỉnh định dạng và tỉ lệ.

#### Bước 1: Thêm và Truy cập biểu đồ
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
Chúng ta sẽ đưa dữ liệu mẫu vào biểu đồ.

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

### Định dạng màu nền chuỗi
**Tổng quan:**  
Đặt mỗi chuỗi một màu riêng để biểu đồ dễ đọc hơn.

#### Bước 1: Khởi tạo và Truy cập biểu đồ
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
Bây giờ chúng ta sẽ **định dạng nhãn dữ liệu biểu đồ** để chúng hiển thị văn bản tùy chỉnh.

`IChartDataPoint` đại diện cho một điểm dữ liệu cá nhân trong một chuỗi biểu đồ, và `ITextFrame` chứa văn bản nhãn.

#### Bước 1: Truy cập chuỗi biểu đồ và điểm dữ liệu
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
- **Biểu đồ hiển thị trống:** Đảm bảo bạn đã thêm ít nhất một chuỗi dữ liệu và điểm dữ liệu trước khi lưu.  
- **Số trên trục không hiển thị phần trăm:** Nhớ đặt `verticalAxis.setNumberFormatLinkedToSource(false)`; nếu không, định dạng tùy chỉnh sẽ bị bỏ qua.  
- **Thông báo bản quyền đánh giá:** Áp dụng tệp giấy phép hợp lệ trước khi tạo đối tượng `Presentation` để loại bỏ banner đánh giá.

## Câu hỏi thường gặp

**H: Tôi có thể dùng mã này với Java 11 hoặc mới hơn không?**  
Đ: Có. Thư viện hỗ trợ JDK 8+; chỉ cần dùng classifier phù hợp (ví dụ, `jdk16` cho JDK 16 trở lên).

**H: Làm sao xuất biểu đồ dưới dạng hình ảnh thay vì PPTX?**  
Đ: Sử dụng `chart.getImage().save("chart.png", ImageFormat.Png);` sau khi đã thêm biểu đồ vào slide.

**H: Có thể thêm chú giải (legend) vào biểu đồ cột chồng không?**  
Đ: Chắc chắn. Gọi `chart.getChartTitle().addTextFrameForOverriding("My Chart");` và cấu hình `chart.getLegend()` theo nhu cầu.

**H: Nếu cần cập nhật dữ liệu sau khi bản trình bày đã được tạo thì sao?**  
Đ: Bạn có thể sửa các ô trong `ChartDataWorkbook` rồi gọi `chart.refresh();` để phản ánh thay đổi.

**H: Aspose.Slides có hoạt động trên máy chủ Linux không?**  
Đ: Có. Thư viện thuần Java và chạy trên bất kỳ hệ điều hành nào có JRE tương thích.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách **tạo một biểu đồ cột chồng** trong Java bằng **phụ thuộc Aspose Slides Maven**, từ thiết lập môi trường đến tùy chỉnh phong cách trực quan. Hãy thử nghiệm với các bộ dữ liệu, màu sắc và định dạng nhãn khác nhau để làm cho báo cáo của bạn thực sự nổi bật.

---

**Cập nhật lần cuối:** 2026-07-22  
**Kiểm tra với:** Aspose.Slides 25.4 (jdk16 classifier)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Cách Đặt Định Dạng Số cho Các Điểm Dữ Liệu Biểu Đồ Sử Dụng Aspose.Slides cho Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Cách Thêm và Cấu Hình Biểu Đồ trong Bản Trình Bày Sử Dụng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}