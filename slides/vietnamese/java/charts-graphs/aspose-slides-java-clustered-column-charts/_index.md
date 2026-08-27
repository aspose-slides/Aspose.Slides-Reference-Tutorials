---
date: '2026-08-27'
description: Tìm hiểu cách tạo biểu đồ cột nhóm trong Java bằng Aspose.Slides, thêm
  biểu đồ, thiết lập màu tự động cho các chuỗi, và lưu bản trình chiếu dưới dạng PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Tìm hiểu cách tạo biểu đồ cột nhóm trong Java bằng Aspose.Slides,
  thêm biểu đồ, thiết lập màu tự động cho các chuỗi, và lưu bản trình chiếu dưới dạng
  PPTX—tất cả với hướng dẫn chi tiết từng bước.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Tạo biểu đồ cột nhóm trong Java với Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides

## Giới thiệu
Việc tạo biểu đồ cột nhóm bằng chương trình giúp bạn tiết kiệm hàng giờ định dạng thủ công và đảm bảo tính nhất quán trên nhiều bản trình bày. Trong hướng dẫn này, bạn sẽ học **cách tạo biểu đồ cột nhóm** trong Java với Aspose.Slides, **cách thêm biểu đồ**, **cách đặt màu**, và **cách lưu bản trình bày dưới dạng PPTX**. Chúng tôi sẽ bao phủ mọi thứ từ cài đặt thư viện đến tùy chỉnh màu nền cho series và lưu file, để bạn có thể nhúng các hình ảnh dữ liệu phong phú vào bất kỳ bộ PowerPoint nào.

## Câu trả lời nhanh
- **Lớp chính để làm việc với bản trình bày là gì?** `Presentation` từ gói `com.aspose.slides`.  
- **Làm thế nào để thêm biểu đồ cột nhóm?** Gọi `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **Có thể đặt màu cho series tự động không?** Có—bật `setAutomaticSeriesColor(true)` trên mỗi series.  
- **Định dạng nào nên dùng để lưu file?** `SaveFormat.Pptx` tạo ra một file PowerPoint tiêu chuẩn.  
- **Có cần giấy phép cho môi trường sản xuất không?** Bản dùng thử hoạt động cho phát triển; giấy phép đầy đủ cần thiết cho việc thương mại.

## Biểu đồ cột nhóm là gì?
Biểu đồ cột nhóm hiển thị nhiều series dữ liệu cạnh nhau cho mỗi danh mục, giúp dễ dàng so sánh các giá trị giữa các nhóm. Aspose.Slides hỗ trợ loại biểu đồ này ngay từ đầu và cho phép bạn kiểm soát mọi khía cạnh hình ảnh bằng chương trình.

## Tại sao tạo biểu đồ cột nhóm với Aspose.Slides?
Aspose.Slides có thể xử lý **hơn 50 định dạng đầu vào và đầu ra** và xử lý các bản trình bày với **hàng trăm slide** mà không cần tải toàn bộ file vào bộ nhớ. Hiệu suất này cho phép bạn tạo các bộ slide lớn trong môi trường máy chủ với mức tiêu thụ tài nguyên tối thiểu.

## Yêu cầu trước
- **Java Development Kit** 16 hoặc mới hơn.  
- **Maven** hoặc **Gradle** để quản lý phụ thuộc.  
- Kiến thức cơ bản về cú pháp Java và các khái niệm hướng đối tượng.  

### Thư viện và phụ thuộc cần thiết
Bạn cần thư viện Aspose.Slides cho Java (phiên bản 25.4 trở lên). Thư viện này hoàn toàn tương thích với JDK 16 và cung cấp một API phong phú để thao tác biểu đồ.

### Yêu cầu thiết lập môi trường
IDE của bạn (IntelliJ IDEA, Eclipse, VS Code) phải được cấu hình để biên dịch mã Java 16 và giải quyết các phụ thuộc Maven/Gradle.

### Kiến thức cần thiết
Hiểu cấu trúc slide PowerPoint và thuật ngữ cơ bản của biểu đồ (series, categories, data points) sẽ giúp bạn theo dõi các ví dụ nhanh hơn.

## Cài đặt Aspose.Slides cho Java
Tích hợp thư viện vào dự án của bạn bằng một trong các phương pháp sau.

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

**Direct download** – tải JAR từ trang phát hành chính thức: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Các bước lấy giấy phép
- **Free trial** – đăng ký trên trang Aspose để nhận file giấy phép tạm thời.  
- **Temporary license** – yêu cầu giấy phép 30 ngày cho các bộ kiểm thử lớn hơn.  
- **Full license** – mua để sử dụng không giới hạn trong môi trường sản xuất.

**Khởi tạo và thiết lập cơ bản**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Cách thêm biểu đồ cột nhóm?
`Presentation` đại diện cho một file PowerPoint trong bộ nhớ.  

**Câu trả lời trực tiếp:**  
Tạo một đối tượng `Presentation`, đại diện cho một file PowerPoint trong bộ nhớ, lấy slide đầu tiên, và gọi `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. Lệnh duy nhất này chèn một biểu đồ cột nhóm đầy đủ chức năng, sẵn sàng cho việc nạp dữ liệu, và đặt nó tại tọa độ đã chỉ định trên slide.

### Tính năng 1: tạo biểu đồ cột nhóm
Lớp `Presentation` đại diện cho một file PowerPoint trong bộ nhớ và cung cấp quyền truy cập vào các slide, shape và đối tượng biểu đồ.

**Bước 1: khởi tạo presentation**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Bước 2: thêm biểu đồ cột nhóm**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Bước 3: giải phóng tài nguyên**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Cách đặt màu cho biểu đồ?
`Series` đại diện cho một tập hợp các điểm dữ liệu trong một biểu đồ.  

**Câu trả lời trực tiếp:**  
Sau khi biểu đồ được tạo, lấy dữ liệu biểu đồ qua `chart.getChartData()` và lặp qua mỗi đối tượng `Series`. Đối với mỗi series, gọi `setAutomaticSeriesColor(true)` trên series cha. Aspose.Slides sau đó tự động gán một màu sắc riêng biệt, tương phản từ bảng màu của nó cho mỗi series, đảm bảo độ rõ nét mà không cần chọn màu thủ công.

### Tính năng 2: đặt màu nền tự động cho series
`IChart` là giao diện đại diện cho một shape biểu đồ; nó cung cấp `getChartData()` để thao tác series.

**Bước 1: truy cập biểu đồ và lặp qua series**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Bước 2: quản lý tài nguyên**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Cách lưu bản trình bày dưới dạng PPTX?
`save` ghi bản trình bày vào một file ở định dạng đã chọn.  

**Câu trả lời trực tiếp:**  
Chỉ định đường dẫn file đầu ra như `"output/ClusteredColumnChart.pptx"` và gọi `presentation.save(outputPath, SaveFormat.Pptx)`. Phương thức `save` tuần tự hoá toàn bộ bộ slide, bao gồm tất cả shape, biểu đồ và tài nguyên, thành một file PPTX tiêu chuẩn có thể mở bằng PowerPoint 2010 trở lên, cũng như nhiều trình xem trực tuyến.

### Tính năng 3: lưu bản trình bày vào đĩa
Lưu bằng `SaveFormat.Pptx` tạo ra một file tương thích với PowerPoint 2010 trở lên, cũng như hầu hết các trình xem trực tuyến.

**Bước 1: xác định đường dẫn đầu ra**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Bước 2: lưu bản trình bày**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Ứng dụng thực tiễn
- **Financial reporting** – so sánh doanh thu quý theo các dòng sản phẩm.  
- **Marketing analytics** – trực quan hoá hiệu suất chiến dịch theo khu vực.  
- **Project management** – hiển thị tốc độ sprint hoặc phân bổ nguồn lực giữa các đội.  

## Các lưu ý về hiệu năng
- Giải phóng các đối tượng `Presentation` kịp thời để giải phóng tài nguyên gốc.  
- Sử dụng `presentation.getSlides().removeUnusedResources()` trước khi lưu để giảm kích thước file.  
- Điền dữ liệu cho series biểu đồ bằng các collection nhẹ (ví dụ, `ArrayList<Double>`) để giữ mức sử dụng bộ nhớ thấp.

## Kết luận
Bây giờ bạn đã biết cách **tạo biểu đồ cột nhóm**, tự động **đặt màu**, và **lưu bản trình bày dưới dạng PPTX** bằng Aspose.Slides cho Java. Những bước này cho phép bạn tạo các slide dựa trên dữ liệu một cách lập trình, loại bỏ công việc thủ công lặp đi lặp lại và đảm bảo tính nhất quán về hình ảnh trong toàn tổ chức.

**Bước tiếp theo:**  
Khám phá các tùy chỉnh nâng cao như nhãn dữ liệu, định dạng trục, và ràng buộc dữ liệu động từ cơ sở dữ liệu hoặc file CSV để làm phong phú hơn các bản trình bày của bạn.

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng mã này trong ứng dụng web không?**  
A: Có—Aspose.Slides không phụ thuộc vào nền tảng và hoạt động trong bất kỳ môi trường máy chủ dựa trên Java nào, bao gồm Spring Boot và Jakarta EE.

**Q: Thư viện có hỗ trợ các loại biểu đồ khác không?**  
A: Chắc chắn. Enum `ChartType` bao gồm Pie, Bar, Line, Area, Radar và nhiều loại khác.

**Q: Nếu thư mục đầu ra không tồn tại thì sao?**  
A: Đảm bảo thư mục được tạo trước hoặc sử dụng `Files.createDirectories(Paths.get(folder))` để tránh `FileNotFoundException`.

**Q: Làm thế nào để xử lý bộ dữ liệu lớn (hàng nghìn điểm)?**  
A: Điền series bằng các API streaming hoặc chèn theo batch, và cân nhắc tắt hoạt ảnh biểu đồ để cải thiện tốc độ render.

**Q: Tôi có thể tìm thêm mẫu mã ở đâu?**  
A: Tham khảo tài liệu chính thức và kho mẫu: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Tài nguyên
- **Documentation:** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Reference:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download:** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Purchase:** [Buy a License](https://purchase.aspose.com/buy)  
- **Free trial:** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license:** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Cập nhật lần cuối:** 2026-08-27  
**Kiểm tra với:** Aspose.Slides 25.4 (JDK 16)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo biểu đồ PowerPoint Java – Lưu bản trình bày với biểu đồ bằng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven dependency: Thêm và cấu hình biểu đồ trong bản trình bày bằng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Thêm hoạt ảnh cho biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng dẫn từng bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}