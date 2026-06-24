---
date: '2026-05-23'
description: Tìm hiểu cách thêm chart vào PowerPoint với Aspose.Slides for Java, điều
  chỉnh chart axis labels, và thêm pie chart trong Java – cài đặt đầy đủ, code walk‑through,
  và performance tips.
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'Cách Thêm Chart Vào PowerPoint Sử Dụng Aspose.Slides for Java: Hướng Dẫn Từng
  Bước'
url: /vi/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Thêm Biểu Đồ vào PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước

## Giới Thiệu
Nếu bạn cần **thêm biểu đồ vào PowerPoint** một cách lập trình, Aspose.Slides cho Java cung cấp cho bạn một cách sạch sẽ, không cần giấy phép để nhúng biểu đồ cột, đường, tròn, hoặc bất kỳ trong hơn 150 loại biểu đồ trực tiếp vào tệp PPTX. Trong hướng dẫn này, bạn sẽ thấy chính xác cách tạo một bản trình chiếu, chèn biểu đồ, điều chỉnh nhãn trục, và lưu kết quả — tất cả bằng mã Java ngắn gọn mà bạn có thể sao chép‑dán.  

**Bạn Sẽ Học**
- Cách tạo và khởi tạo một `Presentation`.
- Cách thêm các loại biểu đồ khác nhau, bao gồm biểu đồ tròn trong Java.
- Cách **điều chỉnh nhãn trục biểu đồ** để đọc dễ dàng.
- Cách lưu tệp cuối cùng vào đĩa.

Trước khi bắt đầu, hãy chắc chắn môi trường của bạn đáp ứng các yêu cầu trước được liệt kê bên dưới.

## Câu Trả Lời Nhanh
- **Tôi có thể thêm biểu đồ vào PPTX hiện có không?** Có – tải tệp bằng `new Presentation("path.pptx")` và chỉnh sửa nó.  
- **Các loại biểu đồ nào được hỗ trợ?** Hơn 150 loại, từ cột nhóm đến tròn 3‑D.  
- **Tôi có cần giấy phép để phát triển không?** Bản dùng thử miễn phí hoạt động cho tất cả tính năng; giấy phép vĩnh viễn loại bỏ giới hạn đánh giá.  
- **Làm thế nào để thay đổi khoảng cách nhãn trục?** Đặt `chart.getAxes().getCategoryAxis().setLabelOffset(value)`.  
- **Aspose.Slides Java có tương thích với Maven và Gradle không?** Chắc chắn – cả hai công cụ xây dựng đều được hỗ trợ.

## “Thêm biểu đồ vào PowerPoint” là gì?
*“Thêm biểu đồ vào PowerPoint”* đề cập đến việc chèn một chuỗi dữ liệu trực quan vào slide bằng API, thay vì thiết kế thủ công trong giao diện người dùng. Kỹ thuật này cho phép tạo báo cáo tự động, cập nhật dữ liệu động, và xử lý hàng loạt các bản trình chiếu mà không cần Microsoft Office trên máy chủ, rất thích hợp cho quy trình làm việc quy mô doanh nghiệp.

## Tại sao nên sử dụng Aspose.Slides cho Java?
Aspose.Slides có thể xử lý các bản trình chiếu chứa **lên tới 10.000 slide** và **hàng trăm megabyte** mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại **tốc độ render nhanh hơn tới 40 %** so với nhiều đối thủ. Nó cũng hỗ trợ **hơn 150 loại biểu đồ**, **hơn 50 định dạng ảnh**, và **tương thích đầy đủ PPTX/ODP**, làm cho nó trở thành thư viện đa năng nhất cho việc tạo slide tự động.

## Yêu Cầu Trước
- **Java Development Kit (JDK)** 8 hoặc mới hơn.  
- **Aspose.Slides cho Java** – thêm qua Maven, Gradle, hoặc tải trực tiếp.  
- Kiến thức cơ bản về Java và một IDE như IntelliJ IDEA hoặc Eclipse.

### Cài Đặt Aspose.Slides cho Java

#### Phụ Thuộc Maven
Thêm đoạn sau vào file `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Phụ Thuộc Gradle
Thêm đoạn sau vào file `build.gradle` của bạn:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Tải Trực Tiếp
Hoặc tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

Để bắt đầu sử dụng Aspose.Slides, hãy mua giấy phép:
- **Dùng Thử Miễn Phí** – đầy đủ tính năng, không giới hạn thời gian.  
- **Giấy phép Tạm Thời** – yêu cầu qua [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/).  
- **Mua** – nhận giấy phép vĩnh viễn từ [trang mua của Aspose](https://purchase.aspose.com/buy).

Khởi tạo thư viện bằng cách tạo một thể hiện của `Presentation`.

## Cách Thêm Biểu Đồ vào PowerPoint bằng Aspose.Slides cho Java?

Tải hoặc tạo một đối tượng `Presentation`, lấy một slide, gọi `addChart` với `ChartType` mong muốn, cung cấp dữ liệu, và cuối cùng gọi `save`. Quy trình này chỉ mất vài dòng Java và hoạt động trên bất kỳ nền tảng nào chạy JRE.

### Bước 1: Tạo hoặc Tải Một Presentation
`Presentation` là lớp cấp cao nhất đại diện cho một tệp PowerPoint trong bộ nhớ.

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Mẹo chuyên nghiệp:** Luôn gọi `presentation.dispose()` sau khi hoàn thành để giải phóng tài nguyên gốc.

### Bước 2: Lấy Slide Mục Tiêu
`ISlide` đại diện cho một slide trong một presentation.  
Slide đầu tiên có thể truy cập qua phương thức `getSlides().get_Item(0)`. Điều này trả về một đối tượng `ISlide` hoạt động như một container cho các shape, bao gồm cả biểu đồ.

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### Bước 3: Thêm Biểu Đồ Cột Nhóm
`ChartType` là một enum liệt kê tất cả các loại biểu đồ được hỗ trợ.  
`ChartType.ClusteredColumn` tạo một biểu đồ cột cổ điển. Bạn có thể thay thế bằng bất kỳ giá trị enum nào khác, chẳng hạn `ChartType.Pie` để thêm biểu đồ tròn.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### Bước 4: Điều Chỉnh Nhãn Trục Biểu Đồ
`CategoryAxis` điều khiển các nhãn ngang của biểu đồ.  
Trục **category** điều khiển các nhãn ngang. Cài đặt offset nhãn giúp cải thiện khả năng đọc khi nhãn dài hoặc xoay.

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **Tại sao cần điều chỉnh nhãn trục?** Khoảng cách hợp lý ngăn ngừa văn bản chồng lên nhau, đặc biệt trên các bản trình bày kích thước di động.

### Bước 5: Lưu Presentation
Xác định đường dẫn đầu ra và ghi tệp ở định dạng PPTX. Aspose.Slides cũng hỗ trợ lưu thành PDF, ODP, và HTML nếu cần.

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Cách Thêm Biểu Đồ Tròn trong Java bằng Aspose.Slides?

Tạo một biểu đồ mới với `ChartType.Pie`, điền một series với các giá trị, và tùy chọn bật các lát cắt nổ để nhấn mạnh. Biểu đồ tròn tự động kế thừa theme của slide, nhưng bạn có thể tùy chỉnh hoàn toàn màu sắc, chú giải, và nhãn dữ liệu. Bạn cũng có thể đặt góc bắt đầu và offset nổ để làm nổi bật các lát cắt cụ thể.

> **Câu trả lời trực tiếp (40‑70 từ):**  
Khởi tạo `Presentation`, lấy một slide, gọi `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`, sau đó dùng `chart.getChartData().getSeries().add(...)` để cung cấp giá trị số. Cuối cùng, gọi `presentation.save("pieChart.pptx", SaveFormat.Pptx)`. Điều này tạo một biểu đồ tròn đầy đủ chức năng trong chưa đầy mười dòng mã.

## Ứng Dụng Thực Tế
Aspose.Slides cho Java tỏa sáng trong các quy trình báo cáo tự động:

- **Báo cáo Kinh doanh** – Tự động tạo biểu đồ tài chính hàng quý.  
- **Bài thuyết trình Học thuật** – Chuyển đổi dữ liệu CSV thành các đồ thị chuyên nghiệp.  
- **Bộ tài liệu Marketing** – Cập nhật hình ảnh phễu bán hàng hàng ngày mà không cần chỉnh sửa thủ công.

## Cân Nhắc Hiệu Suất
Khi xử lý các bộ slide lớn:

- Giữ mảng dữ liệu biểu đồ dưới 10 000 điểm để tránh tăng đột biến bộ nhớ.  
- Gọi `presentation.dispose()` kịp thời.  
- Sử dụng xử lý batch (các đối tượng `Presentation` trong vòng lặp) để tận dụng việc thu gom rác của JVM một cách hiệu quả.

## Vấn Đề Thường Gặp và Giải Pháp
- **Rò rỉ bộ nhớ** – Quên gọi `dispose()` dẫn đến tích tụ bộ nhớ gốc.  
- **Thang đo trục không đúng** – Đảm bảo bạn đặt `chart.getAxes().getValueAxis().setAutomaticScale(true)`.  
- **Không tìm thấy giấy phép** – Đặt file giấy phép vào classpath hoặc thiết lập bằng mã: `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");`.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể thêm biểu đồ vào tệp PowerPoint hiện có không?**  
A: Có – tải tệp bằng `new Presentation("existing.pptx")`, chỉnh sửa các slide và lưu lại.

**Q: Làm thế nào để thay đổi loại biểu đồ sau khi đã thêm?**  
A: Truy cập đối tượng `Chart` và đặt `chart.getChartData().setChartType(ChartType.Pie)` để chuyển loại ngay lập tức.

**Q: Aspose.Slides có tương thích với tất cả các IDE Java chính không?**  
A: Chắc chắn – nó hoạt động với IntelliJ IDEA, Eclipse, NetBeans và thậm chí các bản dựng dòng lệnh.

**Q: Những khó khăn thường gặp khi cấu hình nhãn trục là gì?**  
A: Sử dụng offset âm hoặc quên bật `setAutomaticScale(true)` có thể khiến nhãn biến mất hoặc chồng lên nhau.

**Q: Làm sao cải thiện tốc độ render cho các bộ slide khổng lồ?**  
A: Giới hạn số điểm dữ liệu mỗi biểu đồ, tái sử dụng các đối tượng `Presentation` khi có thể, và bật tùy chọn `setCacheSize` cho các hình ảnh lớn.

## Tài Nguyên
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-05-23  
**Kiểm tra với:** Aspose.Slides cho Java 24.11  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng Dẫn Liên Quan

- [Cách Xoay Tiêu Đề Trục Biểu Đồ trong PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [Hoạt Họa Biểu Đồ PowerPoint Sử Dụng Aspose.Slides cho Java – Hướng Dẫn Từng Bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Cách Tùy Chỉnh Màu Sắc Biểu Đồ Tròn trong Java với Aspose.Slides – Hướng Dẫn Đầy Đủ](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}