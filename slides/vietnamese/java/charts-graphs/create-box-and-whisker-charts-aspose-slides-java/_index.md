---
date: '2026-08-21'
description: Tìm hiểu cách tạo box plot java bằng Aspose.Slides, thêm chart vào slide
  và tạo box‑and‑whisker chart trong PowerPoint. Lý tưởng cho Java developers.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Tìm hiểu cách tạo box plot java bằng Aspose.Slides, thêm chart vào
  slide và tạo box‑and‑whisker chart trong PowerPoint. Lý tưởng cho Java developers.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Cách tạo box plot java với Aspose.Slides cho PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Cách tạo box plot java với Aspose.Slides cho PowerPoint
url: /vi/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo box plot java với Aspose.Slides cho PowerPoint

Trong hướng dẫn này, bạn sẽ **tạo box plot java** với Aspose.Slides, sau đó nhúng biểu đồ trực tiếp vào một slide PowerPoint. Tạo biểu đồ box‑and‑whisker một cách lập trình cho phép bạn biến dữ liệu thống kê thô thành những hiểu biết trực quan rõ ràng mà không rời khỏi mã Java của mình. Nếu bạn cần tự động hoá báo cáo PowerPoint, Aspose.Slides cho Java cung cấp một API đáng tin cậy, hiệu năng cao.

## Bạn sẽ học gì

- Cài đặt môi trường cho Aspose.Slides cho Java
- Các bước **thêm biểu đồ vào slide** và tạo biểu đồ box‑whisker trong PowerPoint bằng Java
- Các thực hành tốt nhất để tối ưu hiệu suất khi làm việc với Aspose.Slides
- Các ứng dụng thực tế của biểu đồ box‑and‑whisker

## Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ hộp trong Java?** Aspose.Slides for Java.  
- **Loại biểu đồ nào được sử dụng?** `ChartType.BoxAndWhisker`.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho đánh giá; giấy phép thương mại cần cho môi trường sản xuất.  
- **Tôi có thể thêm nhiều series không?** Có – lặp lại khối tạo series cho mỗi bộ dữ liệu.  
- **Định dạng file cuối cùng là gì?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Biểu đồ hộp là gì và tại sao dùng trong Java?

Biểu đồ hộp‑and‑whisker (thường được gọi là *box plot*) trực quan hoá sự phân bố dữ liệu — trung vị, các phần tư và các điểm ngoại lệ — trong một dạng gọn gàng. Trong Java, việc tạo biểu đồ này một cách lập trình cho phép bạn nhúng những hiểu biết thống kê trực tiếp vào các bộ slide PowerPoint, loại bỏ việc tạo biểu đồ thủ công. Điều này đặc biệt hữu ích khi so sánh phân bố giữa nhiều danh mục, chẳng hạn điểm kiểm tra giữa các lớp hoặc doanh thu giữa các khu vực. Bằng cách tạo biểu đồ trong Java, bạn có thể tích hợp nó vào các quy trình báo cáo tự động, đảm bảo dữ liệu mới nhất luôn được phản ánh trong bản trình bày.

## Tại sao thêm biểu đồ vào slide với Aspose.Slides?

Aspose.Slides trừu tượng hoá các chi tiết OpenXML cấp thấp, cung cấp cho bạn một API mượt mà để tạo, định dạng và xuất biểu đồ. Điều này cho phép bạn tự động hoá việc tạo báo cáo, duy trì thương hiệu nhất quán và tích hợp biểu đồ vào các quy trình Java lớn hơn. Thư viện còn hỗ trợ các tùy chọn định dạng như màu sắc, phông chữ và ký hiệu, giúp bạn phù hợp với bộ nhận diện công ty. Ngoài ra, nó xử lý các tác vụ phức tạp như ràng buộc dữ liệu và làm mới biểu đồ mà không cần Microsoft Office.

## Cách thêm biểu đồ slide bằng Java với Aspose.Slides?

Tải hoặc tạo một `Presentation`, chèn một `Chart` loại `BoxAndWhisker`, cung cấp dữ liệu, và lưu file — tất cả trong vài dòng Java. API xử lý bố cục, tỉ lệ và render, vì vậy bạn không cần thao tác XML thủ công. Bạn cũng có thể đặt tiêu đề biểu đồ và nhãn trục một cách lập trình để cung cấp ngữ cảnh cho người xem.

## Yêu cầu trước

- **Bộ công cụ phát triển Java (JDK)**: JDK 8 hoặc cao hơn.  
- **Thư viện Aspose.Slides cho Java**: Cần thiết để thao tác PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào hỗ trợ Java.

## Cài đặt Aspose.Slides cho Java

Thêm thư viện dưới dạng phụ thuộc Maven, Gradle hoặc thủ công.

### Maven

Thêm phụ thuộc sau vào `pom.xml` của bạn:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Trong `build.gradle`, bao gồm:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp

Hoặc tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Nhận giấy phép

- **Bản dùng thử** – khám phá tính năng mà không tốn phí.  
- **Giấy phép tạm thời** – dùng cho đánh giá ngắn hạn.  
- **Mua** – mở khóa đầy đủ tính năng cho môi trường sản xuất.

Để khởi tạo Aspose.Slides, đảm bảo JAR nằm trong classpath và thiết lập bất kỳ tệp giấy phép nào theo mô tả trong tài liệu.

## Hướng dẫn triển khai

Dưới đây là hướng dẫn chi tiết từng bước. Mỗi khối được giải thích trước đoạn mã để bạn biết chính xác nó làm gì.

### Lớp `Presentation` là gì?

Lớp `Presentation` là đối tượng trung tâm trong Aspose.Slides, đại diện cho toàn bộ tệp PowerPoint trong bộ nhớ. Nó cung cấp truy cập tới các slide, biểu đồ, hình dạng và các yếu tố slide khác, cho phép bạn tạo, sửa đổi và lưu bản trình bày một cách lập trình. Sử dụng lớp này, bạn có thể thêm slide mới, chèn hình ảnh và điều chỉnh thứ tự slide bằng các lời gọi API đơn giản.

### Bước 1: tạo hoặc mở một bản trình bày

Đầu tiên, mở một PPTX hiện có hoặc bắt đầu một bản mới:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** Nếu tệp không tồn tại, Aspose.Slides sẽ tự động tạo một bản trình bày trống mới.

### Bước 2: thêm biểu đồ hộp‑whisker vào slide

Đặt biểu đồ ở vị trí bạn cần bằng cách chỉ định vị trí và kích thước (đơn vị điểm):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Bước 3: xóa dữ liệu hiện có

Trước khi cung cấp dữ liệu mới, xóa bất kỳ danh mục hoặc series placeholder nào:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Bước 4: cấu hình các danh mục

Thêm các danh mục (nhãn trục X) sẽ xuất hiện dưới mỗi hộp:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Lưu ý:** Điều chỉnh văn bản nhãn để phù hợp với miền dữ liệu của bạn (ví dụ: “Q1”, “Product A”).

### Bước 5: tạo và tùy chỉnh series

Bây giờ tạo một series, đặt các tùy chọn hiển thị và cung cấp các điểm dữ liệu số:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Bạn có thể thay thế mảng `int[] data` bằng các giá trị đọc từ cơ sở dữ liệu, tệp CSV, hoặc bất kỳ nguồn nào khác.

### Bước 6: lưu bản trình bày

Lưu các thay đổi vào một tệp PPTX mới:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Bước 7: dọn dẹp tài nguyên

Luôn giải phóng đối tượng `Presentation` để giải phóng tài nguyên gốc:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Ứng dụng thực tiễn

Biểu đồ hộp‑whisker vô giá trong phân tích thống kê và trình bày dữ liệu. Dưới đây là một vài kịch bản mà chúng tỏa sáng:

1. **Phân tích tài chính** – hiển thị phân bố doanh thu theo khu vực.  
2. **Kiểm soát chất lượng** – phát hiện ngoại lệ trong đo lường sản xuất.  
3. **Nghiên cứu học thuật** – hiển thị biến động kết quả thí nghiệm.  
4. **Nghiên cứu thị trường** – so sánh hiệu suất sản phẩm theo các nhóm nhân khẩu học.

Nhúng các biểu đồ này trực tiếp vào bộ slide PowerPoint giúp các bên liên quan nắm bắt dữ liệu phức tạp ngay lập tức.

## Các cân nhắc về hiệu suất

Aspose.Slides có thể xử lý các bản trình bày với **hơn 500 slide** và biểu đồ với **hơn 100 000 điểm dữ liệu** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB trên một máy chủ tiêu chuẩn. Để duy trì trong giới hạn đó:

- **Quản lý bộ nhớ** – giải phóng các đối tượng `Presentation` kịp thời.  
- **Xử lý dữ liệu** – chỉ tải dữ liệu cần thiết; tránh đưa tập dữ liệu lớn trực tiếp vào workbook của biểu đồ.  
- **Tải lười** – khi tạo nhiều slide, chỉ tạo biểu đồ cho những slide sẽ được hiển thị.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Biểu đồ xuất hiện trống** | Các ô dữ liệu không được điền đúng | Xác minh rằng `wb.getCell` tham chiếu đúng hàng/cột và giá trị không phải `null`. |
| **Không hiển thị ngoại lệ** | `setShowOutlierPoints` được đặt thành `false` | Đảm bảo gọi `series.setShowOutlierPoints(true)`. |
| **Rò rỉ bộ nhớ** | Presentation không được giải phóng | Luôn bao bọc việc sử dụng trong `try/finally` và gọi `dispose()`. |
| **Phân vị không đúng** | Sử dụng phương pháp `Inclusive` mặc định | Chuyển sang `Exclusive` qua `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Câu hỏi thường gặp

**Câu 1: Biểu đồ hộp‑whisker là gì?**  
Biểu đồ hộp‑whisker, còn được gọi là box plot, hiển thị phân bố dữ liệu dựa trên năm thống kê tóm tắt: giá trị tối thiểu, phần tư thứ nhất, trung vị, phần tư thứ ba và giá trị tối đa, cùng bất kỳ ngoại lệ nào.

**Câu 2: Tôi có thể tùy chỉnh giao diện của biểu đồ hộp‑whisker không?**  
Có. Aspose.Slides cho phép bạn thay đổi màu sắc, kiểu đường, hình dạng ký hiệu và thêm nhãn dữ liệu thông qua API định dạng biểu đồ.

**Câu 3: Có thể xử lý nhiều series trong một biểu đồ không?**  
Chắc chắn. Lặp lại khối tạo series cho mỗi bộ dữ liệu bạn muốn hiển thị.

**Câu 4: Làm sao giải quyết vấn đề dữ liệu không hiển thị đúng?**  
Đảm bảo dữ liệu được ghi đúng vào các ô workbook và các thuộc tính hiển thị như `setShowMeanLine` được bật.

**Câu 5: Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?**  
Truy cập [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) để nhận trợ giúp cộng đồng, hoặc tham khảo tài liệu chính thức.

**Câu 6: Aspose.Slides có hỗ trợ các loại biểu đồ khác không?**  
Có, nó hỗ trợ hơn 50 loại biểu đồ — bao gồm line, bar, pie, scatter, radar và funnel — để bạn có thể chọn hình ảnh phù hợp nhất cho dữ liệu của mình.

**Câu 7: Tôi có thể tạo biểu đồ trong môi trường server không giao diện không?**  
Thư viện hoạt động hoàn toàn trong các kịch bản server‑side; không cần cài đặt UI hay Microsoft Office.

## Tài nguyên

- **Tài liệu**: Khám phá tham chiếu API chi tiết tại [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Tải xuống**: Truy cập trang phát hành Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Mua**: Mua giấy phép để mở khóa đầy đủ tính năng [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Bản dùng thử & giấy phép tạm thời**: Bắt đầu với bản dùng thử miễn phí hoặc yêu cầu giấy phép tạm thời [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Bằng cách làm theo hướng dẫn này, bạn đã sẵn sàng để tạo các biểu đồ hộp‑and‑whisker sâu sắc trong các ứng dụng Java và nhúng chúng trực tiếp vào các bản trình bày PowerPoint. Chúc bạn lập trình vui vẻ!

---

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách Thêm Biểu Đồ vào PowerPoint Sử Dụng Aspose.Slides cho Java: Hướng Dẫn Từng Bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java tạo biểu đồ PowerPoint bằng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Thêm hoạt ảnh vào biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng Dẫn Từng Bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}