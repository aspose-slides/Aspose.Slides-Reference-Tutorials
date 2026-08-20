---
date: '2026-08-06'
description: Tìm hiểu cách thay đổi màu font color của legend và chỉnh sửa văn bản
  legend của chart bằng Aspose.Slides for Java. Thực hiện các hướng dẫn step‑by‑step
  để customize chart legends nhanh chóng.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Tìm hiểu cách thay đổi màu font color của legend và chỉnh sửa văn
  bản legend của chart với Aspose.Slides for Java. Hướng dẫn này cho bạn các bước
  chính xác và best practices.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Cách thay đổi màu font color của legend trong Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Cách thay đổi màu font color của legend trong Aspose.Slides for Java
url: /vi/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thay đổi màu phông chữ chú giải trong Aspose.Slides cho Java

## Giới thiệu
Nếu bạn cần **thay đổi màu phông chữ chú giải** trong một biểu đồ, Aspose.Slides cho Java cung cấp cho bạn quyền kiểm soát đầy đủ đối với mỗi mục chú giải. Hướng dẫn này sẽ chỉ cho bạn cách tùy chỉnh kiểu chữ của chú giải, áp dụng phông chữ in đậm hoặc nghiêng, và đặt màu nền đặc để biểu đồ của bạn trông chính xác như mong muốn. Khi kết thúc hướng dẫn, bạn sẽ có thể sửa đổi văn bản chú giải biểu đồ một cách tự tin và tích hợp các thay đổi vào bất kỳ bản trình bày hiện có nào.

**Bạn sẽ học**
- Cách **thay đổi màu phông chữ chú giải** bằng lập trình.
- Các cách **sửa đổi văn bản chú giải biểu đồ** như in đậm, nghiêng và kích thước.
- Mẹo áp dụng các thay đổi cho nhiều biểu đồ trong một bản trình bày.
- Cách tích hợp các bước này vào quy trình tự động hoá lớn hơn.

## Câu trả lời nhanh
- **Tôi có thể thay đổi màu của một mục chú giải duy nhất không?** Có – truy cập mục qua chỉ mục của nó và đặt định dạng tô màu thành màu đặc.  
- **Tôi có cần giấy phép để sử dụng các API này không?** Cần giấy phép tạm thời hoặc trả phí cho môi trường sản xuất; bản dùng thử miễn phí hoạt động cho việc đánh giá.  
- **Phiên bản Java nào được hỗ trợ?** Aspose.Slides cho Java 25.4+ hoạt động với JDK 16 và các phiên bản mới hơn.  
- **Các thay đổi có ảnh hưởng tới các thành phần khác của biểu đồ không?** Không, định dạng chú giải được tách biệt khỏi kiểu dáng chuỗi dữ liệu.  
- **Có thể xử lý hàng loạt không?** Chắc chắn – lặp qua các slide và biểu đồ để áp dụng cùng cài đặt chú giải cho toàn bộ bộ trình chiếu.

## Thay đổi màu phông chữ chú giải là gì?
`change legend font color` đề cập đến thao tác lập trình thiết lập màu văn bản của các mục chú giải trong biểu đồ bằng API Aspose.Slides. Thao tác này cập nhật giao diện hiển thị của chú giải mà không thay đổi dữ liệu nền.

## Tại sao tùy chỉnh chú giải biểu đồ?
Aspose.Slides hỗ trợ **hơn 50 định dạng đầu vào và đầu ra** và có thể xử lý các bản trình bày với **hơn 500 slide** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB. Việc tùy chỉnh chú giải cải thiện khả năng đọc, củng cố màu sắc thương hiệu, và đảm bảo các điểm dữ liệu quan trọng nổi bật — đặc biệt trong các bộ trình chiếu kinh doanh hoặc giáo dục, nơi độ rõ ràng về hình ảnh thúc đẩy quyết định.

## Yêu cầu trước
- **Thư viện Aspose.Slides cho Java** (Phiên bản 25.4 trở lên).  
- Java Development Kit (JDK) 16 hoặc cao hơn.  
- Một IDE như IntelliJ IDEA, Eclipse, hoặc NetBeans.  
- Maven hoặc Gradle để quản lý phụ thuộc.  
- Kiến thức lập trình Java cơ bản.

## Cài đặt Aspose.Slides cho Java
Để bắt đầu tùy chỉnh chú giải biểu đồ, thêm thư viện vào dự án của bạn bằng một trong các phương pháp dưới đây.

### Maven
Thêm phụ thuộc sau vào tệp `pom.xml` của bạn:
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
Bạn cũng có thể tải JAR mới nhất từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Các bước lấy giấy phép
- **Bản dùng thử miễn phí:** Bắt đầu với bản dùng thử miễn phí để khám phá các tính năng của Aspose.Slides.  
- **Giấy phép tạm thời:** Đăng ký giấy phép tạm thời để đánh giá mở rộng.  
- **Mua:** Để có quyền truy cập đầy đủ, cân nhắc mua giấy phép từ [Aspose Purchase](https://purchase.aspose.com/buy).

#### Khởi tạo và cài đặt cơ bản
Sau khi thêm thư viện vào dự án của bạn:
1. Khởi tạo Aspose.Slides trong ứng dụng Java của bạn.  
2. Tải một bản trình bày hiện có hoặc tạo một bản mới.

## Cách thay đổi màu phông chữ chú giải?
Để thay đổi màu phông chữ chú giải, tải bản trình bày, lấy đối tượng biểu đồ, truy cập chú giải của nó, sau đó sửa định dạng văn bản của mỗi mục chú giải bằng cách đặt kiểu tô màu thành đặc và chỉ định màu mong muốn. Thao tác duy nhất này cập nhật màu văn bản chú giải ngay lập tức mà không cần vẽ lại toàn bộ slide. Ví dụ: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Cách tiếp cận này hoạt động với bất kỳ loại biểu đồ nào và không yêu cầu vẽ lại toàn bộ slide.

### Truy cập và sửa đổi thuộc tính văn bản chú giải

#### Định nghĩa anchor
`Giao diện IChart đại diện cho một đối tượng biểu đồ trên slide, và phương thức getLegend() của nó trả về một đối tượng ILegend chứa một tập hợp các mục ILegendEntry.`

#### Thêm biểu đồ vào bản trình bày của bạn
1. **Tải bản trình bày:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Thêm biểu đồ cột nhóm:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Tùy chỉnh thuộc tính phông chữ
3. **Truy cập định dạng văn bản của mục chú giải:**  
   Ở đây, `legendEntry` là một đối tượng `ILegendEntry` đại diện cho một mục duy nhất trong chú giải biểu đồ.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Đặt kiểu in đậm và nghiêng với chiều cao cụ thể:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Thay đổi kiểu tô màu thành màu đặc để tăng độ nhìn rõ:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Lưu bản trình bày
6. **Lưu các thay đổi của bạn:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Những khó khăn thường gặp và khắc phục
- Xác minh chỉ mục mục chú giải khớp với thứ tự chuỗi trong biểu đồ của bạn.  
- Đảm bảo bạn đang sử dụng phiên bản thư viện hỗ trợ `setSolidFillColor` (có sẵn từ phiên bản 20.9).  

## Ứng dụng thực tiễn
Việc tùy chỉnh văn bản chú giải hữu ích trong nhiều tình huống thực tế:

1. **Bản trình bày kinh doanh:** Đồng bộ màu chú giải với thương hiệu công ty để có giao diện chuyên nghiệp.  
2. **Tài liệu giáo dục:** Nhấn mạnh các chuỗi dữ liệu chính bằng cách sử dụng màu chú giải tương phản.  
3. **Bộ trình chiếu marketing:** Nhấn mạnh các chỉ số hiệu suất bằng chú giải in đậm, màu sắc để thu hút sự chú ý của các bên liên quan.  

Bạn cũng có thể tự động cập nhật chú giải bằng cách lấy giá trị màu từ cơ sở dữ liệu hoặc tệp cấu hình.

## Các cân nhắc về hiệu năng
Khi xử lý các bộ trình chiếu lớn, hãy nhớ những mẹo sau:

- **Quản lý bộ nhớ hiệu quả:** Gọi `presentation.dispose()` sau khi lưu để giải phóng tài nguyên gốc.  
- **Chỉ tải các slide cần thiết:** Sử dụng `Presentation.load(String path, LoadOptions options)` cùng `LoadOptions.setLoadOnlySlideIds()` nếu bạn chỉ cần một phần.  
- **Xử lý hàng loạt:** Nhóm cập nhật chú giải theo slide để giảm số lần gọi API và tăng thông lượng.

## Kết luận
Bạn hiện đã biết cách **thay đổi màu phông chữ chú giải** và **sửa đổi văn bản chú giải biểu đồ** bằng Aspose.Slides cho Java. Những tùy chỉnh này nâng cao độ rõ ràng về hình ảnh và giúp bạn truyền tải dữ liệu hiệu quả hơn. Hãy thử nghiệm các phông chữ, kích thước và màu sắc khác nhau để phù hợp với hướng dẫn phong cách của bản trình bày, và khám phá các tính năng định dạng biểu đồ khác để tạo ra các bộ trình chiếu thực sự chuyên nghiệp.

**Các bước tiếp theo**
- Thử áp dụng cùng kiểu chú giải cho biểu đồ tròn và đường.  
- Kết hợp tùy chỉnh chú giải với định dạng nhãn dữ liệu để có biểu đồ hoàn toàn mang thương hiệu.  

Sẵn sàng nâng tầm bản trình bày của bạn? Thực hiện các bước trên và ngay lập tức thấy sự khác biệt!

## Phần Câu hỏi thường gặp
1. **Làm thế nào để thay đổi màu văn bản của một mục chú giải?**  
   Sử dụng `getFillFormat().setFillType(FillType.Solid)` rồi `setSolidFillColor(Color.YOUR_COLOR)` trên định dạng văn bản của mục chú giải.  

2. **Tôi có thể áp dụng các thay đổi này cho tất cả các chú giải trong một bản trình bày không?**  
   Có – lặp qua mỗi slide, tìm mỗi biểu đồ, và cập nhật các mục chú giải của nó trong một vòng lặp.  

3. **Có thể điều chỉnh kích thước phông chữ một cách động dựa trên độ dài văn bản không?**  
   Bạn có thể tính kích thước cần thiết bằng `TextFrame.getTextFrameFormat().getFontHeight()` và đặt nó qua `setFontHeight(double)`.  

4. **Nếu tôi gặp vấn đề với việc đánh chỉ mục mục chú giải thì sao?**  
   Kiểm tra lại rằng chỉ mục bạn dùng khớp với thứ tự chuỗi; nhớ rằng chỉ mục bắt đầu từ 0.  

5. **Tôi có thể tìm thêm ví dụ Aspose.Slides ở đâu?**  
   Khám phá [Aspose Documentation](https://reference.aspose.com/slides/java/) để có hướng dẫn chi tiết và tài liệu API.  

**Câu hỏi bổ sung**

**Q: Việc thay đổi màu phông chữ chú giải có ảnh hưởng tới các tệp PDF xuất ra không?**  
A: Không, thay đổi màu được giữ nguyên trong tất cả các định dạng xuất khẩu được Aspose.Slides hỗ trợ, bao gồm PDF và PPTX.  

**Q: Tôi có thể sử dụng gradient thay vì màu đặc không?**  
A: Có – đặt `FillType.Gradient` và cấu hình các điểm dừng gradient qua `getGradientStyle()`.  

**Q: Một biểu đồ có thể có bao nhiêu mục chú giải?**  
A: Một biểu đồ có thể có tối đa 256 mục chú giải, giới hạn chỉ bởi số chuỗi dữ liệu bạn thêm.  

## Tài nguyên
- **Tài liệu:** Hướng dẫn toàn diện về việc sử dụng các tính năng Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Tải xuống:** Truy cập phiên bản mới nhất của Aspose.Slides cho Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Mua:** Mua giấy phép để mở khóa toàn bộ khả năng ([Link](https://purchase.aspose.com/buy)).  
- **Bản dùng thử & giấy phép tạm thời:** Bắt đầu với bản dùng thử miễn phí và đăng ký giấy phép tạm thời ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Hỗ trợ:** Nhận trợ giúp từ cộng đồng trên diễn đàn hỗ trợ của Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Cập nhật lần cuối:** 2026-08-06  
**Kiểm tra với:** Aspose.Slides cho Java 25.4  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Nâng cao biểu đồ PowerPoint: Tùy chỉnh phông chữ & trục với Aspose.Slides cho Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides cho Java: Hướng dẫn khung văn bản động & tùy chỉnh phông chữ](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Hoạt hình biểu đồ PowerPoint bằng Aspose.Slides cho Java – Hướng dẫn từng bước](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}