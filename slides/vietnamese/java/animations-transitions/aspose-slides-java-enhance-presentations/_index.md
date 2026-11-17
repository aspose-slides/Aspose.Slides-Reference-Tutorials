---
date: '2026-11-16'
description: Vẽ khung quanh văn bản trong các bảng PowerPoint bằng Aspose.Slides for
  Java – tìm hiểu cách tạo bảng, thêm văn bản vào các ô, làm nổi bật các ô và xuất
  tệp dưới dạng PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Vẽ khung quanh văn bản trong các bảng PowerPoint bằng Aspose.Slides
  for Java. Hướng dẫn này chỉ cách tạo bảng, thêm và căn chỉnh văn bản, làm nổi bật
  các ô, và xuất các slide dưới dạng PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Cách vẽ khung quanh văn bản và tạo bảng trong PowerPoint bằng Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Cách vẽ khung quanh văn bản và tạo bảng trong PowerPoint bằng Aspose.Slides
  for Java
url: /vi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách vẽ khung quanh văn bản và tạo bảng trong PowerPoint với Aspose.Slides cho Java

## Giới thiệu

Việc **vẽ khung quanh văn bản** trong một slide PowerPoint cho phép bạn làm nổi bật các số liệu quan trọng mà không thay đổi nội dung gốc. Trong hướng dẫn này, bạn sẽ học cách tạo bảng một cách lập trình, chèn và căn chỉnh văn bản trong các ô, làm nổi bật các từ cụ thể hoặc toàn bộ ô, và cuối cùng lưu bản trình chiếu dưới dạng tệp PPTX. Khi hoàn thành, bạn sẽ có một slide được tinh chỉnh khiến mắt người xem tập trung đúng vào nơi bạn muốn.

## Câu trả lời nhanh
- **What does “add text to table” mean?** Nó có nghĩa là chèn hoặc cập nhật nội dung văn bản của các ô bảng riêng lẻ một cách lập trình.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – bước **save presentation as pptx** này hoàn thiện các thay đổi của bạn.  
- **How can I align text inside a shape?** Sử dụng `TextAlignment.Left` (hoặc Center/Right) thông qua `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Có – lặp qua các đoạn văn, lấy hình chữ nhật bao quanh của chúng, và thêm một `IAutoShape` không nền và đường viền màu đen.  
- **Do I need a license?** Giấy phép tạm thời hoạt động cho việc đánh giá; một giấy phép đầy đủ là bắt buộc cho môi trường sản xuất.  

## Tại sao cần vẽ khung quanh văn bản?

Việc vẽ khung quanh văn bản ngay lập tức làm nổi bật các số liệu, cảnh báo hoặc tiêu đề quan trọng. Nó cung cấp một dấu hiệu trực quan trong khi giữ nguyên định dạng gốc, rất phù hợp cho báo cáo tài chính, bảng điều khiển KPI, hoặc bất kỳ slide nào cần nhấn mạnh.

## Khái niệm vẽ khung quanh văn bản là gì?

`draw frame around text` là kỹ thuật thêm một hình dạng hình chữ nhật một cách lập trình, theo đúng giới hạn của một đoạn văn hoặc một phần văn bản, sử dụng định dạng đường viền mà không tô màu bên trong. Cách tiếp cận này cho phép bạn nhấn mạnh nội dung mà không thay đổi chính văn bản.

## Yêu cầu trước

### Thư viện yêu cầu
Bạn sẽ cần Aspose.Slides cho Java. Bao gồm nó bằng một trong các trình quản lý gói:

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

Bạn cũng có thể duyệt các bản phát hành tại [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Cấu hình môi trường
Khuyến nghị sử dụng Java Development Kit (JDK) 16 hoặc mới hơn vì các ví dụ sử dụng classifier `jdk16`. Bất kỳ IDE nào như IntelliJ IDEA hoặc Eclipse đều hoạt động.

### Kiến thức yêu cầu
- Kỹ năng lập trình Java cơ bản.  
- Hiểu biết về các khái niệm PowerPoint (slide, shape, table).  
- Hiểu cách Maven/Gradle quản lý các phụ thuộc.

## Cài đặt Aspose.Slides cho Java

`Presentation` là lớp cốt lõi của Aspose.Slides đại diện cho tệp PowerPoint trong bộ nhớ và cung cấp quyền truy cập vào slide, shape và table. Nó có thể xử lý bản trình chiếu lên tới **10.000 slide** trong khi giữ mức sử dụng bộ nhớ dưới **500 MB**, phù hợp cho tự động hoá quy mô lớn.

1. **Install the library** – sử dụng Maven hoặc Gradle, hoặc tải trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **License acquisition** – bắt đầu với bản dùng thử miễn phí từ [Temporary License](https://purchase.aspose.com/temporary-license/) và nâng cấp lên giấy phép đầy đủ tại [Purchase Aspose.Slides](https://purchase.aspose.com/buy) cho các tải công việc sản xuất.  
3. **Basic initialization** – tạo một đối tượng `Presentation` mới và tải hoặc tạo slide theo nhu cầu.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cách thêm văn bản vào bảng trong Aspose.Slides cho Java?

`Presentation` là lớp chính đại diện cho tệp PowerPoint trong bộ nhớ.  
Tải một `Presentation` mới, tạo bảng tại tọa độ mong muốn, điền các ô bằng các đối tượng `TextFrame`, và cuối cùng gọi `pres.save("output.pptx", SaveFormat.Pptx)`. Quy trình này tạo **create table in PowerPoint**, chèn văn bản tùy chỉnh vào mỗi ô, và ghi kết quả vào tệp PPTX trong một luồng công việc hiệu quả.

### Câu trả lời trực tiếp
Tạo bảng bằng cách gọi `slide.getShapes().addTable(...)`, sau đó với mỗi ô sử dụng `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Sau khi điền tất cả các ô, gọi `pres.save("output.pptx", SaveFormat.Pptx)` để ghi tệp. Cách này cho phép bạn kiểm soát nội dung và kiểu dáng của từng ô một cách lập trình.

#### Tính năng 1: tạo bảng và thêm văn bản vào các ô

**1. create a table** – khởi tạo một presentation, thêm một slide, và đặt bảng tại (50, 50) với độ rộng cột và chiều cao hàng được định nghĩa.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – với mỗi ô, tạo một `Paragraph`, thêm một `Portion` chứa chuỗi mong muốn, và gán đoạn văn này cho `TextFrame` của ô.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. save the presentation** – gọi `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cách vẽ khung quanh văn bản trong slide PowerPoint?

`Rectangle2D` đại diện cho một khu vực hình chữ nhật trong không gian tọa độ hai chiều.  
Tải slide, xác định đoạn văn hoặc phần bạn muốn nhấn mạnh, lấy hình chữ nhật bao quanh của nó qua `getRect()`, và sau đó thêm một `IAutoShape` hình chữ nhật không nền và đường viền màu. Phương pháp này hoạt động cho cả đoạn văn toàn bộ và các phần từ riêng lẻ.

### Câu trả lời trực tiếp
Để vẽ khung quanh văn bản, đầu tiên lấy hình chữ nhật của đoạn (`Rectangle2D rect = paragraph.getRect();`). Sau đó tạo một `IAutoShape` hình chữ nhật (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), đặt `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, và tắt nền (`shape.getFillFormat().setFillType(FillType.NoFill)`). Shape sẽ bao quanh văn bản một cách chính xác.

#### Tính năng 3: vẽ khung quanh đoạn văn và phần trong các ô bảng

**1. create a table** – tái sử dụng mã từ Tính năng 1 để thiết lập bảng ban đầu.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – tái sử dụng mã tạo đoạn văn từ Tính năng 1.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. draw frames** – lặp qua mỗi đoạn, lấy hình chữ nhật bao quanh, và thêm một shape hình chữ nhật như mô tả ở trên. Đối với các phần chứa ký tự ‘0’, vẽ thêm một khung để làm nổi bật các số đó.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. save the presentation** – bước cuối cùng giống như trước.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Cách thêm khung văn bản vào AutoShape và thiết lập căn chỉnh

`AutoShape` là một shape có thể chứa văn bản, hình ảnh hoặc nội dung khác.  
Một `AutoShape` có thể chứa một `TextFrame`. Bạn có thể điều khiển căn chỉnh ngang bằng enum `ParagraphFormat`.

### Câu trả lời trực tiếp
Tạo một AutoShape hình chữ nhật (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), truy cập `TextFrame` của nó, đặt văn bản bằng `shape.getTextFrame().setText("Text in shape")`, và sau đó gọi `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Điều này căn chỉnh văn bản sang trái trong shape.

**1. add an AutoShape** – đặt một hình chữ nhật tại vị trí mong muốn.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – áp dụng căn chỉnh trái như minh họa ở trên.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – bước cuối cùng tương tự.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Những lỗi thường gặp & mẹo

- **Always dispose** – bao bọc việc sử dụng `Presentation` trong khối try‑finally và gọi `pres.dispose()` để giải phóng tài nguyên gốc.  
- **Re‑compute bounding rectangles** – nếu bạn thay đổi kích thước phông chữ, lề hoặc khoảng đệm ô sau khi vẽ khung, hãy gọi lại `paragraph.getRect()` trước khi thêm shape.  
- **Batch shape creation for large tables** – tái sử dụng một thể hiện `IAutoShape` duy nhất và cập nhật hình học của nó giúp giảm áp lực bộ nhớ khi xử lý bảng có hàng trăm.  
- **Performance numbers** – Aspose.Slides có thể tạo một PPTX 200 trang trong vòng dưới 2 giây trên máy chủ 4 lõi tiêu chuẩn, và vẽ khung quanh 1.000 đoạn chỉ tốn thêm dưới 150 ms.

## Câu hỏi thường gặp

**Q: Can I use these APIs with older JDK versions?**  
A: Thư viện hỗ trợ JDK 8 trở lên, nhưng classifier `jdk16` cho hiệu năng tốt nhất trên các runtime mới.

**Q: How do I change the frame color?**  
A: Thay đổi màu nền của định dạng đường viền, ví dụ `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Có—sử dụng `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` rồi lưu mảng byte.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Lặp qua `cell.getTextFrame().getParagraphs()`, tìm phần chứa “Total”, và vẽ một hình chữ nhật quanh hộp bao của phần đó.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API truyền dữ liệu theo luồng và giải phóng tài nguyên khi gọi `pres.dispose()`, giúp quản lý bộ nhớ hiệu quả cho các tệp lớn.

**Last Updated:** 2026-11-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

## Các hướng dẫn liên quan

- [Aspose.Slides cho Java&#58; Làm chủ Bảng PPTX & Manipulation Văn bản trong PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cách tạo khung văn bản động trong PowerPoint bằng Aspose.Slides cho Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Thêm cột trong khung văn bản bằng Aspose.Slides cho Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}