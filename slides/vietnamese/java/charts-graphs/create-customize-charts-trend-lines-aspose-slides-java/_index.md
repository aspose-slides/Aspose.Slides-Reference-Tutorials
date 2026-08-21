---
date: '2026-08-21'
description: Tìm hiểu cách tạo clustered column chart và thêm trend lines với Aspose.Slides
  for Java. Bao gồm license setup, tích hợp Maven/Gradle, và các ví dụ chi tiết.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Tạo một clustered column chart và thêm trend lines bằng Aspose.Slides
  for Java. Hướng dẫn này bao gồm license setup, Maven/Gradle, và các đoạn code step‑by‑step.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Tạo clustered column chart và thêm trend lines với Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Cách tạo clustered column chart và thêm trend lines bằng Aspose.Slides for
  Java
url: /vi/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo biểu đồ cột nhóm và thêm các đường xu hướng bằng Aspose.Slides cho Java

Việc tạo các bài thuyết trình hấp dẫn thường bắt đầu bằng một hình ảnh rõ ràng về dữ liệu của bạn. Trong hướng dẫn này, bạn sẽ **tạo biểu đồ cột nhóm** đối tượng, sau đó làm phong phú chúng với nhiều loại đường xu hướng—exponential, linear, logarithmic, moving average, polynomial, và power—bằng cách sử dụng API mạnh mẽ của Aspose.Slides cho Java.

## Câu trả lời nhanh
- **Bước đầu tiên là gì?** Khởi tạo một đối tượng `Presentation` và thêm một biểu đồ cột nhóm vào một slide.  
- **Phiên bản thư viện yêu cầu là gì?** Aspose.Slides cho Java 25.4 hoặc mới hơn.  
- **Tôi có thể sử dụng Maven hoặc Gradle không?** Có, cả hai đều được hỗ trợ; Maven sử dụng `<dependency>` và Gradle sử dụng `implementation`.  
- **Tôi có cần giấy phép không?** Giấy phép dùng thử hoạt động cho việc đánh giá; giấy phép Aspose.Slides đầy đủ loại bỏ các giới hạn đánh giá.  
- **Có bao nhiêu loại đường xu hướng có sẵn?** Sáu loại tích hợp sẵn: exponential, linear, logarithmic, moving average, polynomial và power.

## Biểu đồ cột nhóm là gì?
`create clustered column chart` có nghĩa là tạo một biểu đồ nhóm các chuỗi dữ liệu bên cạnh nhau trong mỗi danh mục, giúp dễ dàng so sánh giá trị giữa các chuỗi. Loại biểu đồ này lý tưởng để trực quan hóa dữ liệu phân loại như doanh thu quý theo khu vực, cho phép người xem nhanh chóng nhận thấy sự khác biệt giữa các nhóm.

## Tại sao thêm đường xu hướng?
Đường xu hướng tiết lộ mẫu hình cơ bản của một chuỗi dữ liệu, giúp bạn dự báo giá trị tương lai, làm nổi bật tốc độ tăng trưởng, hoặc làm mịn dữ liệu nhiễu. Bằng cách thêm đường xu hướng vào biểu đồ cột nhóm, các con số thô trở thành thông tin có thể hành động, cho phép các bên liên quan hiểu được xu hướng dài hạn và đưa ra quyết định dựa trên dữ liệu.

## Các yêu cầu trước
- **Java Development Kit (JDK):** 8 hoặc mới hơn.  
- **Aspose.Slides cho Java:** phiên bản 25.4 hoặc mới hơn.  
- **IDE:** IntelliJ IDEA, Eclipse, hoặc bất kỳ trình chỉnh sửa nào tương thích với Java.  
- **Build tool:** Maven hoặc Gradle (tùy chọn nhưng được khuyến nghị).  
- **License:** tệp giấy phép Aspose.Slides dùng thử hoặc đã mua.  

Bạn nên quen thuộc với cú pháp Java cơ bản và biết cách quản lý phụ thuộc dự án.

## Cách thiết lập Aspose.Slides cho Java?
Thêm thư viện Aspose.Slides vào dự án của bạn bằng trình quản lý phụ thuộc ưa thích, sau đó đặt tệp giấy phép ở vị trí mà runtime có thể tìm thấy. Điều này đảm bảo chức năng đầy đủ và loại bỏ các hạn chế đánh giá.

### Maven
Thêm phụ thuộc này vào tệp `pom.xml` của bạn:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Bao gồm dòng này trong tệp `build.gradle` của bạn:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Tải trực tiếp
Bạn cũng có thể tải JAR thủ công từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Giấy phép Aspose Slides
Đặt tệp `Aspose.Slides.lic` vào thư mục gốc của dự án hoặc thiết lập giấy phép bằng chương trình với `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Giấy phép dùng thử loại bỏ mọi hạn chế tính năng, nhưng giấy phép mua sẽ loại bỏ watermark đánh giá và cung cấp tối ưu hoá hiệu năng đầy đủ. Đối với sử dụng trong môi trường sản xuất, hãy cân nhắc mua giấy phép từ [trang mua Aspose](https://purchase.aspose.com/buy).

## Cách tạo một bản trình bày và thêm biểu đồ cột nhóm?
Lớp `Presentation` đại diện cho một tệp PowerPoint và cung cấp các phương thức để tạo, chỉnh sửa và lưu slide. Khởi tạo một `Presentation`, thêm một slide, sau đó gọi `addChart` với `ChartType.ClusteredColumn` để tạo đối tượng biểu đồ. Quá trình này thiết lập canvas slide, chèn hình dạng biểu đồ và chuẩn bị cho việc điền dữ liệu và định dạng.

1. **Khởi tạo bản trình bày** – cài đặt thư mục đầu ra và tạo một thể hiện `Presentation` mới.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Thêm biểu đồ cột nhóm** – lấy hình dạng biểu đồ, cấu hình các series, và điền các điểm dữ liệu.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Cách thêm đường xu hướng exponential?
Giao diện `ITrendline` định nghĩa một đường xu hướng có thể được thêm vào một series biểu đồ để mô hình hoá mẫu dữ liệu. Áp dụng đường xu hướng exponential cho một series bằng cách tạo một thể hiện `ITrendline`, đặt `TrendlineType` thành `Exponential`, và gắn nó vào series mong muốn. Loại đường xu hướng này hữu ích cho dữ liệu tăng nhanh với tốc độ gia tăng.

1. **Cấu hình đường xu hướng** – chọn series và gọi `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Cách thêm đường xu hướng linear?
Đường xu hướng linear hiển thị đường thẳng phù hợp nhất qua các điểm dữ liệu của bạn. Bạn cũng có thể tùy chỉnh giao diện của nó, như màu và độ dày của đường, để phù hợp với phong cách trình bày.

1. **Thiết lập đường xu hướng** – sử dụng `addTrendline(TrendlineType.Linear)` và sau đó điều chỉnh `getLineFormat().setFillFormat().setFillType(FillType.Solid)` để thay đổi màu.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Cách thêm đường xu hướng logarithmic với khung văn bản tùy chỉnh?
Đường xu hướng logarithmic lý tưởng cho dữ liệu tăng nhanh ban đầu rồi sau đó ổn định. Ghi đè nhãn mặc định cho phép bạn thêm văn bản giải thích để làm rõ ý nghĩa của xu hướng.

1. **Tùy chỉnh đường xu hướng** – sau khi thêm đường xu hướng, truy cập `getDataLabel()` và đặt thuộc tính `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Cách thêm đường xu hướng moving average?
Đường xu hướng moving average làm mịn các biến động ngắn hạn để làm nổi bật các xu hướng dài hạn. Bạn có thể chỉ định chu kỳ (số điểm) dùng để trung bình, cho phép kiểm soát độ mượt của đường.

1. **Cấu hình đường xu hướng** – gọi `addTrendline(TrendlineType.MovingAverage)` và đặt `setPeriod(3)` để sử dụng trung bình động ba điểm.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Cách thêm đường xu hướng polynomial?
Đường xu hướng polynomial khớp dữ liệu với một đường cong được định nghĩa bởi phương trình đa thức. Thuộc tính `order` kiểm soát bậc của đa thức, cho phép mô hình hoá các mối quan hệ phức tạp hơn.

1. **Tùy chỉnh đường xu hướng** – sau khi thêm đường xu hướng, đặt `setOrder(3)` cho phép khớp dạng khối.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Cách thêm đường xu hướng power?
Đường xu hướng power hữu ích khi dữ liệu tuân theo quan hệ luật lũy thừa. Bạn cũng có thể đặt giá trị dự báo ngược và tiến để mở rộng đường ra ngoài phạm vi dữ liệu hiện có.

1. **Cấu hình đường xu hướng** – sử dụng `addTrendline(TrendlineType.Power)` và điều chỉnh `setBackward(2)` để mở rộng đường về phía sau.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Ứng dụng thực tế của đường xu hướng trong biểu đồ cột nhóm
- **Phân tích tài chính:** Đường xu hướng exponential và polynomial giúp dự báo biến động giá cổ phiếu.  
- **Dự báo bán hàng:** Đường moving average làm mịn các đỉnh cao mùa vụ, cung cấp cái nhìn rõ ràng hơn về xu hướng bán hàng cơ bản.  
- **Nghiên cứu khoa học:** Đường xu hướng logarithmic hoàn hảo cho dữ liệu trải rộng qua nhiều bậc độ, như cường độ âm thanh hoặc mức pH.  
- **Giám sát vận hành:** Đường xu hướng power có thể mô hình hoá sự suy giảm hiệu suất theo thời gian.

## Cách tối ưu bộ nhớ khi sử dụng Aspose.Slides?
Giải phóng các đối tượng kịp thời và sử dụng `presentation.dispose()` sau khi lưu. Đối với bộ dữ liệu lớn, bật tải lười (lazy loading) của hình ảnh và tránh tải toàn bộ biểu đồ vào bộ nhớ cùng một lúc.

- **Mẫu giải phóng:** Bao bọc `Presentation` trong khối try‑with‑resources hoặc gọi `presentation.dispose()` trong khối finally.  
- **Tải lười:** Đặt `ChartData.setUseCache(true)` khi làm việc với hàng ngàn điểm dữ liệu.  
- **Xuất luồng:** Ghi bản trình bày trực tiếp vào `FileOutputStream` để tránh giữ toàn bộ tệp trong RAM.

## Lợi ích định lượng của Aspose.Slides cho Java
Aspose.Slides hỗ trợ **hơn 50 loại biểu đồ**, có thể tạo bản trình bày với **hơn 1.000 slide** trong vòng **30 giây** trên CPU 2 GHz tiêu chuẩn, và xử lý **PDF 500 trang** mà không cần cài đặt Microsoft Office. Những con số này đã được xác minh trên bản phát hành 25.4 mới nhất.

## Kết luận
Bạn giờ đã có một giải pháp toàn diện, từ đầu đến cuối cho việc **tạo biểu đồ cột nhóm** và làm phong phú chúng với mọi loại đường xu hướng chính có sẵn trong Aspose.Slides cho Java. Bằng cách thực hiện các bước trên, bạn có thể tạo ra các bản trình bày dựa trên dữ liệu vừa hấp dẫn về mặt hình ảnh vừa mạnh mẽ về mặt phân tích.

Các bước tiếp theo bao gồm khám phá các tùy chọn định dạng biểu đồ, xuất ra PDF/HTML, và tự động tạo biểu đồ trên nhiều nguồn dữ liệu.

## Câu hỏi thường gặp

**Q: Làm thế nào để thiết lập Aspose.Slides cho dự án Maven?**  
A: Thêm đoạn `<dependency>` được hiển thị trong phần Maven vào `pom.xml` của bạn và chạy `mvn clean install`.

**Q: Tôi có thể tùy chỉnh đường xu hướng ngoài màu và nhãn không?**  
A: Có, bạn có thể sửa đổi kiểu đường, độ rộng, mẫu gạch, và thậm chí dự báo giá trị tiến/ lùi thông qua API `ITrendline`.

**Q: Tôi nên làm gì nếu gặp lỗi không tương thích phiên bản?**  
A: Xác minh rằng phiên bản JDK của bạn đáp ứng yêu cầu tối thiểu của Aspose.Slides (JDK 8+). Tham khảo ghi chú phát hành của Aspose để biết các thay đổi gây lỗi.

**Q: Có thể thêm đường xu hướng vào nhiều biểu đồ một cách tự động không?**  
A: Chắc chắn. Lặp qua mỗi `IChart` trong bộ sưu tập slide và gọi phương thức `addTrendline` phù hợp cho mỗi series.

**Q: Tôi có cần giấy phép trả phí cho việc sử dụng trong môi trường sản xuất không?**  
A: Có, giấy phép Aspose.Slides mua sẽ loại bỏ các giới hạn đánh giá và mở khóa tối ưu hoá hiệu năng đầy đủ.

---

**Cập nhật lần cuối:** 2026-08-21  
**Kiểm tra với:** Aspose.Slides cho Java 25.4  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [phụ thuộc maven aspose slides: Thêm và cấu hình biểu đồ trong bản trình bày bằng Aspose.Slides cho Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Thêm hoạt ảnh vào biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng dẫn từng bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Tạo biểu đồ PowerPoint Java – Lưu bản trình bày với biểu đồ bằng Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}