---
date: '2026-06-23'
description: Tìm hiểu cách tạo bảng trong PowerPoint, thêm văn bản vào các ô bảng,
  vẽ khung quanh văn bản và lưu bản trình chiếu dưới dạng pptx bằng cách sử dụng Aspose.Slides
  for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Cách tạo bảng trong PowerPoint và vẽ khung với Aspose.Slides for Java
url: /vi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo bảng trong PowerPoint và vẽ khung với Aspose.Slides cho Java

## Giới thiệu

Việc tạo **create table in PowerPoint** một cách lập trình có thể tiết kiệm cho bạn hàng giờ định dạng thủ công, đặc biệt khi bạn cần làm nổi bật các số liệu quan trọng hoặc thêm ghi chú giải thích. Trong hướng dẫn này, bạn sẽ khám phá cách thêm văn bản vào các ô bảng, vẽ khung quanh các đoạn văn cụ thể, thiết lập căn chỉnh văn bản chính xác, và cuối cùng **save presentation as pptx** – tất cả đều sử dụng API mạnh mẽ của Aspose.Slides cho Java. Khi kết thúc, bạn sẽ có một slide trông chuyên nghiệp, dễ đọc và ngay lập tức thu hút sự chú ý của khán giả tới dữ liệu quan trọng nhất.

## Câu trả lời nhanh
- **What does “add text to table” mean?** Nó có nghĩa là chèn hoặc cập nhật nội dung văn bản của các ô bảng riêng lẻ một cách lập trình.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – bước **save presentation as pptx** này hoàn thiện các thay đổi của bạn.  
- **How can I align text inside a shape?** Sử dụng `TextAlignment.Left` (hoặc Center/Right) thông qua `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Có – lặp qua các đoạn văn, lấy hình chữ nhật bao quanh của chúng, và thêm một `IAutoShape` không nền và đường viền màu đen.  
- **Do I need a license?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  

## Tại sao lại vẽ khung quanh văn bản?

Việc vẽ một khung (hoặc hình chữ nhật) quanh một đoạn văn hoặc một phần cụ thể—chẳng hạn như bất kỳ văn bản nào chứa ký tự **'0'**—ngay lập tức thu hút sự chú ý của khán giả tới nội dung đó. Nó cung cấp một dấu hiệu trực quan rõ ràng mà không làm thay đổi văn bản gốc, rất phù hợp để làm nổi bật các số liệu quan trọng, cảnh báo, hoặc tách các phần trong một slide.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn có những thứ sau:

### Thư viện cần thiết
Bạn sẽ cần Aspose.Slides cho Java. Đây là cách đưa nó vào dự án bằng Maven hoặc Gradle:

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

### Cấu hình môi trường
Đảm bảo bạn đã cài đặt Java Development Kit (JDK), tốt nhất là JDK 16 hoặc mới hơn, vì ví dụ này sử dụng bộ phân loại `jdk16`.

### Kiến thức nền tảng
- Hiểu biết cơ bản về lập trình Java.  
- Quen thuộc với phần mềm trình chiếu như PowerPoint.  
- Kinh nghiệm sử dụng môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

## Cài đặt Aspose.Slides cho Java

`Presentation` là lớp cốt lõi của Aspose.Slides đại diện cho tệp PowerPoint trong bộ nhớ và cung cấp quyền truy cập vào các slide, shape và table. Để bắt đầu sử dụng Aspose.Slides, thực hiện các bước sau:

1. **Install the Library**: Sử dụng Maven hoặc Gradle để quản lý các phụ thuộc, hoặc tải trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Bắt đầu với bản dùng thử miễn phí bằng cách tải giấy phép tạm thời từ [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Để có quyền truy cập đầy đủ, hãy cân nhắc mua giấy phép tại [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:  
   Khởi tạo môi trường trình chiếu của bạn với đoạn mã sau:  
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

Tải một `Presentation` mới, tạo một bảng tại tọa độ mong muốn, điền các ô bằng các đối tượng `TextFrame`, và cuối cùng gọi `pres.save("output.pptx", SaveFormat.Pptx)`. Quy trình này tạo một **create table in PowerPoint**, chèn văn bản tùy chỉnh vào mỗi ô, và ghi kết quả vào tệp PPTX trong một luồng công việc duy nhất và hiệu quả.

### Tính năng 1: Tạo bảng và thêm văn bản vào các ô

#### Tổng quan
Tính năng này minh họa cách **create table**, sau đó **add text to table** vào các ô và cuối cùng **save presentation as pptx**.

#### Các bước

**1. Tạo bảng**  
Đầu tiên, khởi tạo presentation của bạn và thêm một bảng tại vị trí (50, 50) với độ rộng cột và chiều cao hàng được chỉ định.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Thêm văn bản vào các ô**  
Tạo các đoạn văn với các phần văn bản và thêm chúng vào một ô cụ thể.  
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

**3. Lưu bản trình chiếu**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Tính năng 2: Thêm TextFrame vào AutoShape và thiết lập căn chỉnh

#### Tổng quan
Tìm hiểu cách thêm một khung văn bản với căn chỉnh cụ thể vào một auto shape—một ví dụ của **set text alignment java**.

#### Các bước

AutoShape là một shape có thể chứa văn bản và đồ họa.

**1. Thêm AutoShape**  
Thêm một hình chữ nhật làm AutoShape tại vị trí (400, 100) với kích thước được chỉ định.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum định nghĩa các tùy chọn căn chỉnh ngang cho văn bản trong một shape.

**2. Thiết lập căn chỉnh văn bản**  
Đặt văn bản thành “Text in shape” và căn chỉnh nó sang trái.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Lưu bản trình chiếu**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Tính năng 3: Vẽ khung quanh các đoạn văn và phần trong các ô bảng

#### Tổng quan
Tính năng này tập trung vào **draw frames around text** và thậm chí **draw rectangle around paragraph** cho các phần chứa ký tự ‘0’.

#### Các bước

`IAutoShape` đại diện cho một đối tượng shape có thể được vẽ trên slide, chẳng hạn như các hình chữ nhật dùng làm khung.

**1. Tạo bảng**  
Tái sử dụng mã từ “Create Table and Add Text to Cells” cho thiết lập ban đầu.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Thêm các đoạn văn**  
Tái sử dụng mã tạo đoạn văn từ tính năng trước.  
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

**3. Vẽ khung**  
Lặp qua các đoạn văn và phần để vẽ khung quanh chúng.  
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

**4. Lưu bản trình chiếu**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Những lỗi thường gặp & Mẹo

- **Null checks** – Luôn bao bọc việc sử dụng `Presentation` của bạn trong một khối try‑finally để đảm bảo `pres.dispose()` được gọi và giải phóng tài nguyên gốc.  
- **Bounding rectangle accuracy** – Hình chữ nhật trả về bởi `para.getRect()` phản ánh bố cục hiện tại; nếu bạn thay đổi kích thước phông chữ hoặc lề, hãy tính lại hình chữ nhật trước khi vẽ khung.  
- **Performance** – Khi làm việc với các bảng rất lớn, hãy cân nhắc ghép nhóm các shape hoặc tái sử dụng một đối tượng `IAutoShape` duy nhất với hình học được cập nhật để giảm tải bộ nhớ.  

## Câu hỏi thường gặp

**Q: Can I use these APIs with older JDK versions?**  
A: Thư viện hỗ trợ JDK 8 trở lên, nhưng bộ phân loại `jdk16` mang lại hiệu năng tốt nhất trên các runtime mới hơn.

**Q: How do I change the frame color?**  
A: Thay đổi màu nền của đường viền, ví dụ, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Có—sử dụng `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` và sau đó lưu mảng byte.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Lặp qua `cell.getTextFrame().getParagraphs()`, tìm phần chứa “Total”, và vẽ một hình chữ nhật quanh hộp bao của phần đó.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API truyền dữ liệu theo luồng và giải phóng tài nguyên khi gọi `pres.dispose()`, giúp quản lý bộ nhớ hiệu quả cho các tệp lớn.

---

**Cập nhật lần cuối:** 2026-06-23  
**Đã kiểm tra với:** Aspose.Slides for Java 25.4 (jdk16)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Aspose.Slides for Java&#58; Làm chủ Bảng PPTX & Thao tác Văn bản trong PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Cách tạo khung văn bản động trong PowerPoint bằng Aspose.Slides cho Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Thêm cột trong Text Frame bằng Aspose.Slides cho Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}