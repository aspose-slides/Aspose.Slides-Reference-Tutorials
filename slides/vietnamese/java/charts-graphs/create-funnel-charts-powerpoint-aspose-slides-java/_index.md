---
date: '2026-09-02'
description: Tìm hiểu cách tạo funnel chart trong PowerPoint bằng cách sử dụng Aspose.Slides
  for Java. Hướng dẫn step‑by‑step này bao gồm việc thiết lập chart data, tùy chỉnh
  màu sắc và xuất presentation.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Tìm hiểu cách tạo funnel chart trong PowerPoint bằng cách sử dụng
  Aspose.Slides for Java. Hướng dẫn này sẽ đưa bạn qua data setup, color customization
  và xuất final presentation.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Tạo funnel chart trong PowerPoint bằng Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Tạo funnel chart trong PowerPoint bằng Aspose.Slides for Java
url: /vi/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thành thạo việc tạo biểu đồ phễu trong PowerPoint với Aspose.Slides cho Java

## Giới thiệu
Tạo các bài thuyết trình hấp dẫn là một nghệ thuật kết hợp trực quan dữ liệu, thiết kế và kể chuyện. Một hình ảnh mạnh mẽ ngay lập tức làm rõ quy trình đa giai đoạn là biểu đồ phễu. Dù bạn cần minh họa quy trình bán hàng, luồng chuyển đổi, hay nút thắt sản xuất, một biểu đồ phễu được thiết kế tốt sẽ biến các con số thô thành một câu chuyện trực quan. Trong hướng dẫn này, bạn sẽ học cách **tạo biểu đồ phễu** trong PowerPoint một cách lập trình bằng Aspose.Slides cho Java, cấu hình dữ liệu, tùy chỉnh màu sắc cho từng đoạn và xuất bản trình chiếu hoàn chỉnh.

**Bạn sẽ học được**
- Cách thêm Aspose.Slides cho Java vào dự án Maven hoặc Gradle  
- Cách khởi tạo đối tượng `Presentation` và truy cập các slide của nó  
- Cách chèn biểu đồ phễu, định nghĩa các danh mục và điền dữ liệu cho series  
- Cách tạo kiểu cho mỗi lát phễu bằng màu nền đặc hoặc màu thương hiệu  
- Cách lưu bản trình chiếu dưới dạng tệp PPTX hoặc xuất slide dưới dạng hình ảnh  

## Câu trả lời nhanh
- **Thư viện chính cho việc trực quan dữ liệu java là gì?** Aspose.Slides cho Java.  
- **Làm thế nào để tạo biểu đồ phễu trong PowerPoint?** Gọi `slide.addChart(ChartType.Funnel, …)` trên slide mục tiêu.  
- **API nào thiết lập nguồn dữ liệu cho biểu đồ?** Sử dụng `IChartDataWorkbook` cùng với `chart.getChartData()`.  
- **Có thể tùy chỉnh màu cho từng đoạn phễu không?** Có—đặt `FillFormat.setFillType(FillType.Solid)` và gán một `java.awt.Color`.  
- **Có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép Aspose.Slides mua bản quyền cho các triển khai thương mại.

## Java trực quan dữ liệu là gì?
Java trực quan dữ liệu là thực hành chuyển đổi dữ liệu thô thành biểu đồ, đồ thị hoặc đồ họa tương tác trực tiếp từ các ứng dụng Java. Aspose.Slides cho Java là thư viện hàng đầu cho phép nhà phát triển tạo hơn 100 loại biểu đồ—bao gồm cả biểu đồ phễu—mà không cần khởi động PowerPoint thủ công, hỗ trợ các bản trình chiếu lên tới 500 slide trong khi vẫn giữ mức sử dụng bộ nhớ thấp.

## Tại sao sử dụng biểu đồ phễu trong PowerPoint?
Biểu đồ phễu ngay lập tức hiển thị tỷ lệ giảm sút qua các giai đoạn liên tiếp, khiến chúng trở nên lý tưởng cho các pipeline bán hàng, phân tích chuyển đổi hoặc đánh giá hiệu quả quy trình. Aspose.Slides cung cấp kiểm soát pixel‑perfect về bố cục, màu sắc các đoạn và nhãn dữ liệu, giúp bạn duy trì tính nhất quán thương hiệu và tránh công sức thủ công chỉnh sửa biểu đồ trong giao diện PowerPoint.

## Yêu cầu trước (H2)

### Thư viện, phiên bản và phụ thuộc cần thiết
Để triển khai Aspose.Slides cho Java trong dự án, bao gồm các tọa độ Maven hoặc Gradle thích hợp. Thư viện hoạt động với Java 8‑21 và không yêu cầu phụ thuộc native bên ngoài.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Bạn cũng có thể tải JAR trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Yêu cầu thiết lập môi trường
Đảm bảo bạn đã cài đặt JDK 8 hoặc mới hơn và `JAVA_HOME` trỏ tới thư mục JDK đúng. Aspose.Slides chạy trên mọi hệ điều hành hỗ trợ JDK, bao gồm Windows, macOS và Linux.

### Kiến thức nền tảng cần có
Hiểu biết cơ bản về cú pháp Java, lập trình hướng đối tượng và khái niệm tệp trình chiếu sẽ hữu ích, nhưng các đoạn mã đều được giải thích chi tiết cho mọi mức độ kinh nghiệm.

## Cài đặt Aspose.Slides cho Java (H2)

1. **Thêm phụ thuộc** – Sử dụng đoạn mã Maven hoặc Gradle ở trên.  
2. **Nhận giấy phép** –  
   - **Dùng thử miễn phí** – Tải giấy phép tạm thời từ [trang web của Aspose](https://purchase.aspose.com/temporary-license/) để đánh giá.  
   - **Giấy phép đầy đủ** – Mua giấy phép sản xuất qua [trang mua hàng](https://purchase.aspose.com/buy).  
3. **Khởi tạo cơ bản** –  

`Presentation` là lớp cốt lõi của Aspose.Slides, đại diện cho một tệp PowerPoint trong bộ nhớ. Nó cung cấp quyền truy cập vào các slide, hình dạng và đối tượng biểu đồ.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Đoạn mã trên tạo một thể hiện `Presentation` mới, sẵn sàng cho việc thao tác slide, và đảm bảo giải phóng tài nguyên bằng `dispose()`.

## Hướng dẫn triển khai

Chúng ta sẽ đi qua từng tính năng cần thiết để xây dựng một biểu đồ phễu hoàn chỉnh, thêm đoạn mô tả ngắn trước mỗi khối mã.

### Tính năng 1: tạo bản trình bày (H2)

#### Tổng quan
Bắt đầu bằng việc tạo một thể hiện của lớp `Presentation`. Đối tượng này là điểm khởi đầu cho mọi thao tác tiếp theo.

`Presentation` là đối tượng cấp cao nhất của Aspose.Slides, chứa bộ sưu tập slide và các cài đặt tài liệu toàn cục.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Đoạn mã mở một bản trình bày trống, bạn có thể lưu lại sau này dưới dạng tệp `.pptx`.

### Tính năng 2: thêm biểu đồ phễu vào slide (H2)

#### Tổng quan
Chèn một biểu đồ phễu vào slide đầu tiên, xác định kích thước và đặt loại biểu đồ.

`ChartType.Funnel` báo cho Aspose.Slides vẽ một biểu đồ dạng phễu thay vì biểu đồ cột hay đường.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Lệnh `addChart` tạo hình dạng biểu đồ, đặt nó tại vị trí `(50, 50)` điểm, và cho chiều rộng `500` và chiều cao `400`.

### Tính năng 3: xóa dữ liệu biểu đồ hiện có (H2)

#### Tổng quan
Trước khi điền dữ liệu vào biểu đồ, hãy xóa bất kỳ danh mục hoặc series placeholder nào mà mẫu có thể chứa.

`chart.getChartData().getCategories().clear()` loại bỏ tất cả các mục danh mục hiện có, trong khi `chart.getChartData().getSeries().clear()` xóa mọi series đã được điền sẵn.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Điều này đảm bảo một bảng trắng sạch sẽ để dữ liệu tùy chỉnh của bạn hiển thị đúng như mong muốn.

### Tính năng 4: thiết lập workbook dữ liệu biểu đồ (H2)

#### Tổng quan
Đối tượng `IChartDataWorkbook` lưu trữ các giá trị thô điều khiển biểu đồ. Khởi tạo nó cho phép bạn ghi dữ liệu trực tiếp vào các ô.

`IChartDataWorkbook` là một bảng tính nhẹ trong bộ nhớ mà Aspose.Slides dùng để cung cấp dữ liệu cho series và danh mục của biểu đồ.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Đoạn mã xóa mọi ô hiện có, chuẩn bị workbook cho các mục nhập mới.

### Tính năng 5: thêm danh mục vào biểu đồ (H2)

#### Tổng quan
Xác định các nhãn văn bản xuất hiện ở phía trái của phễu—đại diện cho mỗi giai đoạn của quy trình.

`chart.getChartData().getCategories().add()` tạo một đối tượng danh mục mới liên kết với một ô workbook cụ thể.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Ở đây chúng ta thêm ba giai đoạn: “Prospects”, “Qualified Leads”, và “Closed Deals”.

### Tính năng 6: thêm series dữ liệu vào biểu đồ (H2)

#### Tổng quan
Điền các giá trị số vào phễu và tùy chọn gán màu riêng cho mỗi lát.

`IDataPoint` đại diện cho một điểm dữ liệu duy nhất trong một series biểu đồ.  

`chart.getChartData().getSeries().add()` tạo một series chứa các điểm dữ liệu; mỗi `IDataPoint` có thể nhận màu nền riêng.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Vòng lặp minh họa cách đặt màu nền đặc cho mỗi điểm, sử dụng hằng số `java.awt.Color` theo thương hiệu hoặc màu ngẫu nhiên để tạo sự đa dạng trực quan.

## Các trường hợp sử dụng phổ biến & mẹo (H2)

- **Báo cáo pipeline bán hàng** – Hiển thị số lượng lead di chuyển từ giai đoạn tiềm năng đến chốt thành công ở mỗi bước.  
- **Phân tích hiệu suất quy trình** – Trực quan hoá mất mát vật liệu hoặc độ trễ thời gian qua các bước sản xuất.  
- **Đánh giá funnel marketing** – So sánh tỷ lệ chuyển đổi giữa các chiến dịch hoặc nguồn lưu lượng truy cập.  

**Mẹo chuyên nghiệp:** Thay vì dùng màu ngẫu nhiên, hãy sử dụng bảng màu thương hiệu của công ty (ví dụ, `new Color(0, 112, 192)`) để giữ cho bản trình chiếu nhất quán với các tài sản marketing khác.

## Câu hỏi thường gặp (H2)

**H: Làm sao để thay đổi hướng của biểu đồ phễu?**  
Đ: Đặt thuộc tính `ChartOrientation` trên đối tượng `IChart` thành `ChartOrientation.Vertical` hoặc `ChartOrientation.Horizontal`.

**H: Tôi có thể xuất slide thành hình ảnh sau khi thêm biểu đồ không?**  
Đ: Có—gọi `pres.getSlides().get_Item(0).getThumbnail(1, 1)` và ghi `java.awt.image.BufferedImage` kết quả ra tệp PNG hoặc JPEG.

**H: Nếu tôi cần hơn ba danh mục thì sao?**  
Đ: Chỉ cần thêm các danh mục bổ sung bằng `chart.getChartData().getCategories().add(...)` và cung cấp các điểm dữ liệu tương ứng cho mỗi danh mục mới.

**H: Có cách nào ẩn legend không?**  
Đ: Sử dụng `chart.getChartTitle().setVisible(false)` và `chart.getLegend().setVisible(false)` để tắt cả tiêu đề và legend khỏi hình ảnh.

**H: Tôi có cần giấy phép cho các bản dựng phát triển không?**  
Đ: Giấy phép tạm thời đủ cho việc đánh giá; giấy phép thương mại đầy đủ là bắt buộc cho triển khai sản xuất.

---

**Cập nhật lần cuối:** 2026-09-02  
**Kiểm thử với:** Aspose.Slides cho Java 25.4 (jdk16)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}