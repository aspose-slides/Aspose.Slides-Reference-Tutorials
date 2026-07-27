---
date: '2026-07-27'
description: Tìm hiểu cách tạo doughnut chart Java bằng Aspose.Slides – hướng dẫn
  nhanh để thiết lập thư viện, thêm doughnut chart có thể tùy chỉnh, điều chỉnh kích
  thước lỗ, và lưu bản trình chiếu.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Tìm hiểu cách tạo doughnut chart Java bằng Aspose.Slides – hướng dẫn
  nhanh để thiết lập thư viện, thêm doughnut chart có thể tùy chỉnh, điều chỉnh kích
  thước lỗ, và lưu bản trình chiếu.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Tạo Doughnut Chart Java – Hướng dẫn từng bước với Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Tạo Doughnut Chart Java – Hướng dẫn từng bước với Aspose.Slides
url: /vi/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Tạo Biểu Đồ Doughnut trong Java Sử Dụng Aspose.Slides cho Bài Thuyết Trình

## Giới thiệu
Việc tạo các bài thuyết trình hấp dẫn về mặt hình ảnh là điều cần thiết để truyền đạt thông tin một cách hiệu quả. **Create doughnut chart java** là một yêu cầu phổ biến khi bạn cần minh họa dữ liệu tỷ lệ với giao diện hiện đại. Trong hướng dẫn này, bạn sẽ học cách thiết lập Aspose.Slides cho Java, xây dựng một biểu đồ doughnut, tùy chỉnh kích thước lỗ và màu sắc, và cuối cùng lưu tệp bài thuyết trình. Khi hoàn thành, bạn sẽ có một mẫu có thể tái sử dụng trong bất kỳ dự án Java nào tạo ra các bộ PowerPoint một cách tự động.

**Bạn sẽ học:**
- Cài đặt Aspose.Slides cho Java
- Tạo và cấu hình biểu đồ doughnut trong bài thuyết trình
- Điều chỉnh thẩm mỹ biểu đồ như kích thước lỗ
- Lưu bài thuyết trình với biểu đồ mới của bạn

Hãy bắt đầu bằng cách thiết lập môi trường!

## Câu trả lời nhanh
- **Thư viện nào tạo doughnut chart java?** Aspose.Slides cho Java.
- **Cần bao nhiêu dòng mã cho một doughnut chart cơ bản?** Khoảng 8–10 dòng sau khi khởi tạo presentation.
- **Có thể thay đổi kích thước lỗ không?** Có, phương thức `setHoleSize(double)` chấp nhận giá trị từ 0 % đến 100 %.
- **Các định dạng đầu ra nào được hỗ trợ?** PPTX, PDF, XPS, PNG, JPEG và một số khác (hơn 50 tổng cộng).
- **Cần giấy phép cho môi trường production không?** Cần giấy phép thương mại để sử dụng không giới hạn; bản dùng thử miễn phí đủ cho việc đánh giá.

## Aspose.Slides cho Java là gì?
**Aspose.Slides cho Java** là một API được quản lý hoàn toàn, cho phép các nhà phát triển tạo, sửa đổi, chuyển đổi và render các tệp PowerPoint mà không cần Microsoft Office. Nó hỗ trợ hơn 50 định dạng tệp và có thể xử lý các bài thuyết trình có hàng ngàn slide trong khi giữ mức sử dụng bộ nhớ thấp.

## Tại sao nên dùng doughnut chart trong bài thuyết trình?
Biểu đồ doughnut hiển thị mối quan hệ phần‑với‑toàn trong khi để trống không gian ở trung tâm cho nhãn hoặc hình ảnh. Aspose.Slides có thể render doughnut chart lên tới **500 slide mỗi phút** trên một máy chủ 2.5 GHz tiêu chuẩn, và nó xử lý **bài thuyết trình hàng trăm trang** mà không cần tải toàn bộ tệp vào bộ nhớ, rất phù hợp cho các giải pháp báo cáo quy mô lớn.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã đáp ứng các yêu cầu sau:

### Thư viện và Phiên bản cần thiết
Để làm việc với Aspose.Slides cho Java, hãy thêm nó vào dự án qua Maven hoặc Gradle, hoặc tải trực tiếp.

#### Yêu cầu thiết lập môi trường
- JDK (Java Development Kit) đang hoạt động, ưu tiên phiên bản 8 trở lên.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

### Kiến thức nền tảng
Hiểu biết về Java và các khái niệm lập trình cơ bản là hữu ích. Kiến thức cơ bản về Maven hoặc Gradle sẽ giúp quá trình thiết lập nhanh hơn.

## Cài đặt Aspose.Slides cho Java
Việc tích hợp Aspose.Slides vào dự án có thể thực hiện theo nhiều cách:

**Maven:**  
Thêm phụ thuộc này vào tệp `pom.xml` của bạn:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Thêm đoạn này vào tệp `build.gradle` của bạn:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp:**  
Hoặc tải phiên bản mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Mua giấy phép
- **Bản dùng thử:** Bắt đầu bằng cách tải phiên bản dùng thử để khám phá các tính năng của Aspose.Slides.  
- **Giấy phép tạm thời:** Nhận giấy phép tạm thời để sử dụng đầy đủ chức năng mà không bị giới hạn.  
- **Mua bản quyền:** Đối với việc sử dụng lâu dài, cần mua giấy phép.

Sau khi đã thiết lập thư viện và môi trường, chúng ta sẽ tiến tới triển khai doughnut chart.

## Cách tạo doughnut chart trong Java?
Tải một đối tượng `Presentation` mới, thêm doughnut chart vào slide, đặt kích thước lỗ, và lưu tệp – tất cả chỉ trong vài lệnh API đơn giản. Cách tiếp cận này cho phép bạn kiểm soát toàn bộ dữ liệu biểu đồ, giao diện và định dạng xuất, đồng thời không cần cài đặt Microsoft PowerPoint trên máy chủ.

### Khởi tạo đối tượng Presentation
Lớp `Presentation` là đối tượng cấp cao nhất của Aspose.Slides, đại diện cho một tệp PowerPoint trong bộ nhớ.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Bước này tạo một bài thuyết trình rỗng, nơi bạn có thể thêm slide, shape và chart.

### Thêm Doughnut Chart vào Slide
`ISlide` là giao diện cho một slide đơn; bạn có thể lấy slide đầu tiên hoặc thêm slide mới.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Phương thức `addChart` tạo một doughnut chart; các tham số xác định vị trí (X, Y) và kích thước (width, height) trên slide.

### Cấu hình kích thước lỗ Doughnut
`Chart` cung cấp phương thức `setHoleSize(double)` để điều chỉnh bán kính trong như phần trăm của bán kính biểu đồ.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Đặt kích thước lỗ thành 90 % khiến biểu đồ gần như thành một vòng tròn đầy, hữu ích khi bạn muốn nhấn mạnh các phần bên ngoài.

### Lưu Presentation
`presentation.save(String, SaveFormat)` ghi tệp ra đĩa ở định dạng đã chọn.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Ví dụ lưu kết quả dưới tên `DoughnutHoleSize_out.pptx`, nhưng bạn cũng có thể chọn PDF, PNG hoặc bất kỳ định dạng nào trong hơn 50 định dạng được hỗ trợ.

### Dọn dẹp tài nguyên
Gọi `presentation.dispose()` giải phóng tài nguyên gốc và ngăn ngừa rò rỉ bộ nhớ, đặc biệt quan trọng trong các ứng dụng server chạy lâu dài.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Ứng dụng thực tiễn
Biểu đồ doughnut rất linh hoạt. Dưới đây là một số kịch bản mà chúng tỏa sáng:
1. **Phân bổ ngân sách:** Hiển thị cách ngân sách được phân phối cho các phòng ban.  
2. **Kết quả khảo sát:** Trực quan hoá câu trả lời cho các câu hỏi có nhiều lựa chọn.  
3. **Nguồn lưu lượng truy cập website:** Cho biết tỷ lệ phần trăm lưu lượng đến từ các kênh khác nhau (organic, paid, referral, …).

## Lưu ý về hiệu năng
Khi làm việc với Aspose.Slides, hãy cân nhắc các mẹo sau để tối ưu hiệu năng:
- Giải phóng đối tượng `Presentation` ngay khi không còn dùng để giải phóng bộ nhớ gốc.  
- Sử dụng stream (`FileInputStream`, `ByteArrayOutputStream`) cho các bộ dữ liệu lớn để tránh tải toàn bộ tệp vào RAM.  
- Tái sử dụng đối tượng chart khi tạo nhiều slide trong vòng lặp để giảm chi phí tạo đối tượng.

## Các vấn đề thường gặp và giải pháp
- **Lỗi khi lưu:** Kiểm tra thư mục đầu ra tồn tại và ứng dụng có quyền ghi.  
- **Thiếu dữ liệu chart:** Đảm bảo bạn đã điền bộ sưu tập `ChartData` của chart trước khi gọi `setHoleSize`.  
- **Tăng đột biến bộ nhớ:** Đối với bài thuyết trình hàng ngàn slide, giảm kích thước slide bằng `Presentation.setSlideSize` và giải phóng các slide trung gian kịp thời.

## Câu hỏi thường gặp

**H: Có thể điều chỉnh màu sắc cho các phần của doughnut chart không?**  
Đ: Có. Sử dụng `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` và sau đó chỉ định màu RGB mong muốn.

**H: Làm sao thêm nhãn dữ liệu vào chart?**  
Đ: Gọi `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` để hiển thị giá trị bên trong mỗi phần.

**H: Có thể lưu chart ở các định dạng khác PPTX không?**  
Đ: Chắc chắn. Aspose.Slides hỗ trợ PDF, XPS, PNG, JPEG, TIFF và nhiều định dạng khác—hơn 50 tổng cộng.

**H: Nếu gặp ngoại lệ khi tải một bài thuyết trình lớn, tôi nên làm gì?**  
Đ: Sử dụng constructor của `Presentation` nhận stream và bật `loadOptions.setLoadFormat(LoadFormat.Pptx)` để stream tệp và giảm tiêu thụ bộ nhớ.

**H: Có thể tự động cập nhật chart với nguồn dữ liệu trực tiếp không?**  
Đ: Có. Lấy dữ liệu từ cơ sở dữ liệu hoặc REST API, cập nhật bộ sưu tập `ChartData`, và gọi `chart.refresh()` trước khi lưu bài thuyết trình.

## Tài nguyên
- **Tài liệu:** Khám phá chi tiết API tại [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Tải xuống:** Nhận phiên bản thư viện mới nhất từ [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Mua bản quyền:** Để có quyền truy cập đầy đủ, mua giấy phép tại [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Bản dùng thử:** Thử nghiệm Aspose.Slides với bản dùng thử miễn phí trên trang tải xuống.  
- **Giấy phép tạm thời:** Nhận giấy phép tạm thời để thử nghiệm mở rộng mà không có giới hạn.  
- **Hỗ trợ:** Có câu hỏi? Truy cập [Aspose Forum](https://forum.aspose.com/c/slides/11) để được trợ giúp.

---

**Cập nhật lần cuối:** 2026-07-27  
**Kiểm thử với:** Aspose.Slides cho Java 24.12  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}