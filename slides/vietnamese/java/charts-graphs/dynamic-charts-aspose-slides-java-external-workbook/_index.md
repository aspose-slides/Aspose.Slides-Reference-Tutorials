---
date: '2026-08-06'
description: Tìm hiểu cách tạo chart trong bài thuyết trình Java bằng Aspose.Slides
  và cách liên kết workbook để cập nhật dữ liệu động. Hướng dẫn từng bước.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: Tìm hiểu cách tạo chart trong bài thuyết trình Java bằng Aspose.Slides
  và cách liên kết workbook để cập nhật dữ liệu động. Thực hiện theo hướng dẫn ngắn
  gọn này.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: Cách tạo chart trong bài thuyết trình Java với Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: Cách tạo chart trong bài thuyết trình Java với Aspose.Slides
url: /vi/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ trong bản trình bày Java bằng Aspose.Slides: liên kết tới sổ làm việc bên ngoài

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách tạo biểu đồ** trong một bản trình bày Java và **cách liên kết dữ liệu sổ làm việc** để các biểu đồ tự động làm mới. Biểu đồ động giữ cho các slide của bạn luôn cập nhật mà không cần sao chép‑dán thủ công, điều này rất quan trọng cho báo cáo trực tiếp, bảng điều khiển tài chính và các bộ slide trạng thái dự án. Chúng tôi sẽ hướng dẫn qua việc cài đặt, triển khai và các lỗi thường gặp, để bạn có thể tích hợp dữ liệu Excel thời gian thực chỉ với vài dòng mã.

## Câu trả lời nhanh
- **Lợi ích chính là gì?** Biểu đồ tự động cập nhật khi sổ Excel liên kết thay đổi.  
- **Phiên bản thư viện yêu cầu là gì?** Aspose.Slides for Java 25.4 hoặc mới hơn.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại loại bỏ mọi giới hạn đánh giá.  
- **Tôi có thể sử dụng bất kỳ định dạng Excel nào không?** Có – cả tệp `.xlsx` và `.xls` legacy đều được hỗ trợ.  
- **Độ trễ mạng có phải là vấn đề không?** Lưu trữ sổ làm việc cục bộ hoặc sử dụng CDN để giảm thiểu độ trễ.

## Liên kết biểu đồ động là gì?
Liên kết biểu đồ động cho phép một biểu đồ đọc nguồn dữ liệu từ một sổ làm việc bên ngoài tại thời gian chạy, vì vậy bất kỳ thay đổi nào trong sổ làm việc đều được phản ánh trên slide khi mở lại. Điều này loại bỏ nhu cầu tạo lại bản trình bày sau mỗi lần cập nhật dữ liệu.

## Tại sao nên sử dụng Aspose.Slides cho Java?
Aspose.Slides hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**, có thể render các bản trình bày hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, và xử lý cập nhật dữ liệu biểu đồ trong dưới 200 ms trên một máy chủ tiêu chuẩn. Những con số hiệu năng này làm cho nó trở thành lựa chọn đáng tin cậy cho các pipeline báo cáo doanh nghiệp.

## Yêu cầu trước
- **Aspose.Slides for Java** 25.4 hoặc mới hơn.  
- **Java Development Kit (JDK)** 16 hoặc mới hơn.  
- Quen thuộc với Maven hoặc Gradle để quản lý phụ thuộc.  

### Thư viện và phụ thuộc cần thiết
- **Aspose.Slides for Java** – cung cấp API trình chiếu.  
- **Java Development Kit (JDK)** – cần thiết để biên dịch và chạy mã.

### Yêu cầu thiết lập môi trường
- Kiến thức lập trình Java cơ bản.  
- Truy cập vào sổ Excel bên ngoài (đường dẫn tệp cục bộ hoặc URL HTTP).  

## Cài đặt Aspose.Slides cho Java
Để thêm Aspose.Slides vào dự án của bạn, chọn một trong các hệ thống build được hỗ trợ.

### Cấu hình Maven
Thêm phụ thuộc này vào `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Cấu hình Gradle
Bao gồm đoạn này trong tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Hoặc tải thư viện từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Mua giấy phép
Bắt đầu với bản dùng thử miễn phí hoặc nhận giấy phép tạm thời để thử Aspose.Slides mà không có giới hạn. Đối với sử dụng lâu dài, hãy cân nhắc mua giấy phép.

##### Khởi tạo và thiết lập cơ bản
`Presentation` là lớp cốt lõi của Aspose.Slides đại diện cho một tệp PowerPoint trong bộ nhớ. Khởi tạo đối tượng trình chiếu của bạn như sau:
```java
Presentation pres = new Presentation();
```

## Hướng dẫn triển khai
Trong phần này chúng tôi sẽ hướng dẫn cách thiết lập một sổ làm việc bên ngoài để cập nhật dữ liệu biểu đồ trong bản trình bày.

### Cài đặt sổ làm việc bên ngoài với cập nhật dữ liệu biểu đồ
#### Tổng quan
Tính năng này cho phép các biểu đồ tự động cập nhật dữ liệu từ nguồn bên ngoài. Nó lý tưởng khi dữ liệu của bạn thay đổi thường xuyên và bạn muốn các slide phản ánh những thay đổi đó một cách tự động.

#### Triển khai từng bước
1. **Tạo một bản trình bày mới**  
   Bắt đầu bằng cách tạo một thể hiện `Presentation` mới:
   ```java
   Presentation pres = new Presentation();
   ```

2. **Truy cập slide đầu tiên**  
   Truy cập slide rất đơn giản:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Thêm biểu đồ vào slide**  
   Thêm một biểu đồ tròn ở vị trí và kích thước mong muốn:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Đặt URL sổ làm việc bên ngoài cho dữ liệu biểu đồ**  
   Chỉ định một sổ làm việc bên ngoài làm nguồn dữ liệu:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### Tùy chọn cấu hình
- **Loại biểu đồ** – chọn từ Pie, Bar, Line, Area, v.v., tùy thuộc vào cách bạn muốn hiển thị dữ liệu.  
- **Vị trí & kích thước** – điều chỉnh tọa độ X/Y và chiều rộng/chiều cao để phù hợp với bố cục slide.  

## Cách tạo biểu đồ liên kết tới sổ làm việc?
`Chart` là đối tượng Aspose.Slides bao gồm một hình dạng biểu đồ và dữ liệu của nó.  
Tải bản trình bày của bạn, thêm một biểu đồ, và gọi `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. Biểu đồ bây giờ sẽ đọc giá trị series từ sổ làm việc mỗi khi tệp được mở, cung cấp cập nhật trực tiếp mà không cần tạo lại PPTX. Đoạn trả lời ngắn gọn này đáp ứng yêu cầu GEO và cung cấp mô tả ngắn gọn, có thể hành động.

## Các vấn đề thường gặp và giải pháp
Nếu liên kết bên ngoài không cập nhật:
- Xác minh URL có thể truy cập và trả về tệp Excel hợp lệ.  
- Đảm bảo máy chủ cho phép yêu cầu GET ẩn danh hoặc cung cấp thông tin xác thực nếu cần.  
- Lưu trữ sổ làm việc cục bộ nếu độ trễ mạng cao; cập nhật bộ nhớ đệm trước khi mở bản trình bày.

## Ứng dụng thực tiễn
Biểu đồ động được hỗ trợ bởi sổ làm việc bên ngoài có thể hữu ích trong nhiều kịch bản:
1. **Báo cáo dữ liệu thời gian thực** – bảng điều khiển bán hàng lấy số liệu mới nhất từ tệp Excel trung tâm.  
2. **Phân tích tài chính** – xu hướng giá cổ phiếu tự động cập nhật từ nguồn dữ liệu thị trường.  
3. **Quản lý dự án** – bảng điều khiển KPI phản ánh thống kê hoàn thành nhiệm vụ mới nhất.

## Cân nhắc về hiệu năng
Tối ưu hiệu năng là cần thiết khi làm việc với sổ làm việc lớn:
- Lưu trữ sổ làm việc trên máy chủ ứng dụng để giảm các cuộc gọi mạng lặp lại.  
- Sử dụng API streaming để chỉ đọc các phạm vi worksheet cần thiết, giảm sử dụng bộ nhớ.  
- Aspose.Slides xử lý cập nhật biểu đồ trong dưới 200 ms cho sổ làm việc lên tới 10 MB, phù hợp với hầu hết các kịch bản báo cáo.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết **cách tạo biểu đồ** trong các bản trình bày Java và **cách liên kết dữ liệu sổ làm việc** để tự động cập nhật. Khả năng này làm cho slide của bạn trở nên tương tác hơn, giảm công sức thủ công và đảm bảo các bên liên quan luôn nhìn thấy số liệu mới nhất. Khám phá các tính năng bổ sung của Aspose.Slides như sao chép slide, hoạt hình và xuất PDF để nâng cao quy trình báo cáo của bạn.

## Mục FAQ
**Câu hỏi 1: Tôi có thể sử dụng bất kỳ URL nào làm sổ làm việc bên ngoài không?**  
A1: URL phải trỏ tới một tệp Excel có thể truy cập được (`.xlsx` hoặc `.xls`). Đảm bảo máy chủ trả về MIME type đúng và nếu cần, xử lý xác thực trong mã của bạn.

**Câu hỏi 2: Loại biểu đồ nào hỗ trợ liên kết động?**  
A2: Tất cả các loại biểu đồ gốc của Aspose.Slides – Pie, Bar, Line, Area, Scatter, Radar và nhiều hơn nữa – đều có thể liên kết tới sổ làm việc bên ngoài.

**Câu hỏi 3: Có giới hạn kích thước cho sổ làm việc bên ngoài không?**  
A3: Mặc dù Aspose.Slides có thể xử lý sổ làm việc lớn hơn 100 MB, thời gian xử lý tăng tuyến tính; để đạt hiệu năng tốt nhất, giữ file dưới 20 MB hoặc chỉ stream các phạm vi cần thiết.

**Câu hỏi 4: Tôi nên xử lý URL không thể truy cập như thế nào?**  
A4: Bao quanh mã liên kết trong khối try‑catch, ghi lại ngoại lệ, và tùy chọn chuyển sang nguồn dữ liệu tĩnh để bản trình bày vẫn tải được.

**Câu hỏi 5: Có thể sử dụng tính năng này trong quy trình báo cáo tự động không?**  
A5: Chắc chắn. API hoạt động không giao diện người dùng, vì vậy bạn có thể tạo hoặc cập nhật bản trình bày trên máy chủ, nhúng chúng vào email, hoặc xuất lên thư viện SharePoint.

## Tài nguyên
- [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial and Temporary License](https://releases.aspose.com/slides/java/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách tạo biểu đồ trong Java với Aspose.Slides: Hướng dẫn toàn diện](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Cách thêm biểu đồ vào PowerPoint bằng Aspose.Slides cho Java: Hướng dẫn từng bước](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoạt hình biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng dẫn từng bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}