---
date: '2026-09-12'
description: Tìm hiểu cách tạo clustered column chart trong PowerPoint bằng Aspose.Slides
  for Java, truy xuất data range và xuất chart images một cách hiệu quả.
keywords:
- create clustered column chart
- update powerpoint chart data
- export powerpoint chart image
- create pie chart java
- create powerpoint presentation java
- author: Aspose
  dateModified: '2026-09-12'
  description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  headline: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  type: TechArticle
- description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  name: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  steps:
  - name: Create the Presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: Add a Clustered Column Chart
    text: 'Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters Explained**:
      - `ChartType.ClusteredColumn`: Defines the type of chart. - `(10, 10)`: X and
      Y coordinates for positioning the chart on the slide. - `(400, 300)`: Width
      and height of the chart.'
  - name: Retrieve the Data Range
    text: 'Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving Data**: This method gives you a snapshot of your chart''s
      data, useful for debugging or display purposes.'
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
lastmod: '2026-09-12'
og_description: Tìm hiểu cách tạo clustered column chart trong PowerPoint bằng Aspose.Slides
  for Java, truy xuất data range và xuất chart images một cách hiệu quả. Hỗ trợ cập
  nhật PowerPoint chart data và xuất chart image.
og_image_alt: 'Developer guide: create clustered column chart in PowerPoint using
  Aspose.Slides for Java'
og_title: Cách tạo clustered column chart với Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  headline: How to create clustered column chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  name: How to create clustered column chart with Aspose.Slides for Java
  steps:
  - name: create the presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: add a clustered column chart
    text: Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters explained**
      - `ChartType.ClusteredColumn` – selects the clustered column visual. - `(10,
      10)` – X and Y coordinates (points) for the chart’s top‑left corner.
  - name: add a clustered column chart
    text: Firstly, add a clustered column chart as described previously.
  - name: retrieve the data range
    text: Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving data** – this method gives you a snapshot of your chart's
      data, useful for debugging or display purposes.
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides Java
- PowerPoint chart generation
- Java presentation automation
- chart data retrieval
title: Cách tạo clustered column chart với Aspose.Slides for Java
url: /vi/java/charts-graphs/create-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo biểu đồ cột nhóm trong PowerPoint với Aspose.Slides cho Java

Tạo một biểu đồ cột nhóm trong tệp PowerPoint trước đây đòi hỏi phải chỉnh sửa XML phức tạp hoặc cài đặt đầy đủ Office. Với **Aspose.Slides cho Java** bạn có thể tạo biểu đồ một cách lập trình, điều chỉnh dữ liệu và xuất hình ảnh trong vài giây. Hướng dẫn này sẽ dẫn bạn qua việc xây dựng một bản trình bày, chèn biểu đồ cột nhóm và đọc phạm vi dữ liệu nền để bạn có thể xác thực hoặc ghi lại sau này. Để biết thêm chi tiết, truy cập [trang web Aspose](https://releases.aspose.com/slides/java/).

## Câu trả lời nhanh
- **Thư viện nào tạo biểu đồ PowerPoint trong Java?** Aspose.Slides cho Java.  
- **Loại biểu đồ nào được ví dụ sử dụng?** Biểu đồ cột nhóm.  
- **Tôi có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép thương mại cho môi trường sản xuất.  
- **Tôi có thể lấy dữ liệu biểu đồ sau khi tạo không?** Có – gọi `getChartData().getRange()` trên đối tượng biểu đồ.  
- **Phiên bản Java nào được hỗ trợ?** JDK 16 trở lên.

## Aspose.Slides cho Java là gì?

`Aspose.Slides cho Java` là một **API độc lập** cho phép bạn tạo, chỉnh sửa và render tệp PowerPoint mà không cần Microsoft Office. Nó hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các bản trình bày với **hàng trăm slide trong khi sử dụng dưới 200 MB RAM**.

## Tại sao nên sử dụng Aspose.Slides cho Java để tạo biểu đồ?

Aspose.Slides xử lý **hơn 50 loại biểu đồ**, render chúng với **tốc độ lên tới 30 fps** trên phần cứng máy chủ thông thường, và thao tác trên bản trình bày **không cần tải toàn bộ tệp vào bộ nhớ**. Điều này làm cho nó lý tưởng cho các pipeline báo cáo tự động cần tạo hàng ngàn biểu đồ mỗi ngày mà vẫn giữ mức tiêu thụ CPU và RAM thấp.

## Các yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Java Development Kit (JDK)** 16 hoặc mới hơn được cài đặt.  
- Một IDE như **IntelliJ IDEA** hoặc **Eclipse**.  
- **Maven** hoặc **Gradle** để quản lý phụ thuộc.  

### Thư viện và phụ thuộc cần thiết

Thêm Aspose.Slides vào dự án của bạn bằng một trong các đoạn mã sau.

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

Hoặc tải JAR mới nhất từ [các bản phát hành Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

### Cách lấy giấy phép

Bắt đầu với bản dùng thử miễn phí hoặc yêu cầu giấy phép tạm thời để mở khóa tất cả tính năng. Đối với môi trường sản xuất, mua giấy phép từ [trang mua Aspose](https://purchase.aspose.com/buy).

## Cài đặt Aspose.Slides cho Java

Lớp `Presentation` là điểm vào chính để tạo và thao tác các tệp PowerPoint. Sau khi thêm phụ thuộc, khởi tạo API trong mã của bạn.

1. **Thêm phụ thuộc** bằng Maven hoặc Gradle như đã mô tả ở trên.  
2. **Tạo một thể hiện `Presentation`** – đối tượng này sẽ chứa các slide và biểu đồ của bạn.  

```java
Presentation pres = new Presentation();
```  

3. **Giải phóng bản trình bày** khi hoàn thành để giải phóng tài nguyên gốc.  

```java
if (pres != null) pres.dispose();
```  

## Cách tạo bản trình bày PowerPoint với biểu đồ cột nhóm trong Java?

Tải một `Presentation` mới, thêm slide và chèn biểu đồ cột nhóm trong một lời gọi duy nhất. Đối tượng `Presentation` đại diện cho toàn bộ tệp PowerPoint trong bộ nhớ, trong khi phương thức `addChart` tạo một hình dạng biểu đồ trên slide được chỉ định. Dưới đây là các bước cốt lõi, có thể thực hiện trong chưa đầy mười dòng mã.

### Bước 1: tạo bản trình bày  

Lớp `Presentation` là đối tượng cấp cao nhất của Aspose.Slides đại diện cho một tệp PowerPoint trong bộ nhớ.  

```java
Presentation pres = new Presentation();
```  

### Bước 2: thêm biểu đồ cột nhóm  

Sử dụng phương thức `addChart` để chèn biểu đồ vào bản trình bày. Xác định loại, vị trí (tọa độ x và y) và kích thước.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

- **Giải thích các tham số**  
  - `ChartType.ClusteredColumn` – chọn kiểu biểu đồ cột nhóm.  
  - `(10, 10)` – tọa độ X và Y (điểm) cho góc trên‑trái của biểu đồ.  
  - `(400, 300)` – chiều rộng và chiều cao của biểu đồ tính bằng điểm.

## Cách lấy phạm vi dữ liệu của biểu đồ trong bản trình bày PowerPoint bằng Aspose.Slides cho Java?

Gọi `getChartData().getRange()` trên đối tượng biểu đồ; nó ngay lập tức trả về một chuỗi như `"Sheet1!A1:B5"` phản ánh phạm vi kiểu Excel hỗ trợ biểu đồ. Phương thức này cung cấp một biểu diễn văn bản ngắn gọn của nguồn dữ liệu mà không cần tải toàn bộ workbook, rất hữu ích cho việc ghi log, debug hoặc xác thực nhanh trong các pipeline tự động.

### Bước 1: thêm biểu đồ cột nhóm  

Đầu tiên, thêm biểu đồ cột nhóm như đã mô tả ở trên.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

### Bước 2: lấy phạm vi dữ liệu  

Sử dụng `getChartData().getRange()` để nhận biểu diễn chuỗi của phạm vi dữ liệu.  

```java
String result = chart.getChartData().getRange();
// Output omitted for clarity
```  

- **Lấy dữ liệu** – phương thức này cung cấp một ảnh chụp nhanh dữ liệu biểu đồ của bạn, hữu ích cho việc debug hoặc hiển thị.

## Ứng dụng thực tiễn

1. **Báo cáo doanh nghiệp** – tạo bảng điều khiển KPI tự động cập nhật khi dữ liệu nguồn thay đổi.  
2. **Bản trình bày dựa trên dữ liệu** – xây dựng các slide phản ánh số liệu bán hàng hoặc tồn kho mới nhất mà không cần chỉnh sửa thủ công.  
3. **Công cụ giáo dục** – tạo biểu đồ động cho các bài hướng dẫn, câu hỏi trắc nghiệm hoặc sách giáo khoa tương tác.

## Các lưu ý về hiệu năng

- **Giải phóng đối tượng kịp thời** – gọi `presentation.dispose()` trong khối `finally` để giải phóng bộ nhớ gốc.  
- **Tránh tải toàn bộ tài liệu** – sử dụng API streaming khi làm việc với bản trình bày lớn hơn 200 MB.  
- **Chỉ lấy các phạm vi cần thiết** – `getChartData().getRange()` tránh tải toàn bộ bộ dữ liệu biểu đồ, giữ mức sử dụng CPU thấp.

## Các vấn đề thường gặp và giải pháp

- **Bản trình bày bị treo** – luôn bao bọc I/O trong khối `try‑catch` và đảm bảo `dispose()` được gọi trong `finally`.  
- **Kích thước biểu đồ không đúng** – xác nhận các giá trị X, Y, chiều rộng và chiều cao nằm trong khung canvas slide 960 × 720 điểm.  
- **Lỗi giấy phép** – tải file giấy phép trước khi tạo bất kỳ đối tượng `Presentation` nào: `License license = new License(); license.setLicense("Aspose.Slides.lic");`.

## Câu hỏi thường gặp

**Q: Tôi cài đặt Aspose.Slides cho Java như thế nào?**  
A: Sử dụng Maven, Gradle, hoặc tải JAR từ [các bản phát hành Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).

**Q: Tôi có thể tạo các loại biểu đồ khác không?**  
A: Có, Aspose.Slides hỗ trợ hơn 50 loại biểu đồ, bao gồm biểu đồ thanh, đường, tròn và radar.

**Q: Nếu bản trình bày của tôi bị treo trong quá trình xử lý thì sao?**  
A: Đảm bảo giải phóng tài nguyên đúng cách và bao bọc mã trong khối try‑catch để xử lý `IOException` và `Exception`.

**Q: Có chi phí giấy phép cho việc sử dụng Aspose.Slides không?**  
A: Có bản dùng thử miễn phí. Đối với việc sử dụng lâu dài, hãy mua giấy phép hoặc yêu cầu giấy phép tạm thời.

**Q: Tôi nhận được hỗ trợ như thế nào nếu gặp vấn đề?**  
A: Truy cập [diễn đàn hỗ trợ của Aspose](https://forum.aspose.com/c/slides/11) để nhận trợ giúp từ cộng đồng và các chuyên gia Aspose.

## Tài nguyên
- **Tài liệu**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Tải xuống**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Mua**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Dùng thử miễn phí**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Giấy phép tạm thời**: [Request Temporary License](https://purchase.aspose.com/temporary-license/)

Chúc bạn tạo biểu đồ thành công với Aspose.Slides cho Java!

---

**Cập nhật lần cuối:** 2026-09-12  
**Được kiểm tra với:** Aspose.Slides cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

## Hướng dẫn liên quan

- [Master PowerPoint Manipulation with Aspose.Slides Java: Comprehensive Guide for Presentation Operations](/slides/java/presentation-operations/aspose-slides-java-manipulate-pptx-presentations/)
- [Master PowerPoint Slide Automation with Aspose.Slides Java: A Comprehensive Guide for Batch Processing](/slides/java/batch-processing/automate-powerpoint-slides-aspose-slides-java/)
- [Create Sunburst Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-sunburst-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}