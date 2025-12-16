---
date: '2025-12-10'
description: Tìm hiểu cách thêm văn bản vào bảng và vẽ khung quanh văn bản trong PowerPoint
  bằng Aspose.Slides cho Java. Hướng dẫn này bao gồm việc tạo bảng, thiết lập căn
  chỉnh văn bản và tạo khung cho nội dung.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides cho Java – thêm văn bản vào bảng & thao tác khung
url: /vi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Thành thạo việc thao tác Bảng và Khung trong Bài thuyết trình với Aspose.Slides cho Java

## Giới thiệu

Trình bày dữ liệu một cách hiệu quả có thể là thách thức trong PowerPoint. Dù bạn là nhà phát triển phần mềm hay nhà thiết kế bài thuyết trình, **add text to table** các ô và vẽ khung quanh các đoạn văn quan trọng để làm cho slide của bạn nổi bật. Trong hướng dẫn này, bạn sẽ thấy chính xác cách thêm văn bản vào bảng, căn chỉnh nó, và vẽ khung quanh văn bản — tất cả đều với Aspose.Slides cho Java. Khi hoàn thành, bạn sẽ có thể tạo ra những bộ slide được chỉnh chu, làm nổi bật thông tin đúng lúc, đúng chỗ.

Sẵn sàng biến đổi các bài thuyết trình của bạn? Hãy bắt đầu!

## Câu trả lời nhanh
- **What does “add text to table” mean?** Điều này có nghĩa là chèn hoặc cập nhật nội dung văn bản của các ô bảng riêng lẻ một cách lập trình.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – bước **save presentation as pptx** này hoàn thiện các thay đổi của bạn.  
- **How can I align text inside a shape?** Sử dụng `TextAlignment.Left` (hoặc Center/Right) thông qua `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Có – lặp qua các đoạn văn, lấy hình chữ nhật bao quanh chúng, và thêm một `IAutoShape` không nền và đường viền màu đen.  
- **Do I need a license?** Giấy phép tạm thời hoạt động cho mục đích đánh giá; giấy phép đầy đủ là cần thiết cho việc sử dụng trong môi trường sản xuất.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có những thứ sau:

### Thư viện cần thiết
Bạn sẽ cần Aspose.Slides cho Java. Dưới đây là cách đưa nó vào dự án bằng Maven hoặc Gradle:

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
Đảm bảo bạn đã cài đặt Java Development Kit (JDK), ưu tiên JDK 16 hoặc mới hơn, vì ví dụ này sử dụng bộ phân loại `jdk16`.

### Kiến thức yêu cầu
- Hiểu biết cơ bản về lập trình Java.  
- Quen thuộc với phần mềm trình chiếu như PowerPoint.  
- Kinh nghiệm sử dụng môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

## Cài đặt Aspose.Slides cho Java

Để bắt đầu sử dụng Aspose.Slides, hãy thực hiện các bước sau:

1. **Install the Library**: Sử dụng Maven hoặc Gradle để quản lý các phụ thuộc, hoặc tải trực tiếp từ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Bắt đầu với bản dùng thử miễn phí bằng cách tải giấy phép tạm thời từ [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Để có quyền truy cập đầy đủ, hãy cân nhắc mua giấy phép tại [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Khởi tạo môi trường bài thuyết trình của bạn với đoạn mã sau:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Tại sao cần thêm văn bản vào bảng và vẽ khung?

Thêm văn bản vào bảng cho phép bạn trình bày dữ liệu có cấu trúc một cách rõ ràng, trong khi vẽ khung quanh các đoạn văn hoặc các phần cụ thể (ví dụ: những phần chứa ký tự **'0'**) sẽ thu hút ánh mắt người xem tới các giá trị quan trọng. Sự kết hợp này hoàn hảo cho báo cáo tài chính, bảng điều khiển, hoặc bất kỳ slide nào mà bạn cần làm nổi bật các con số then chốt mà không gây rối mắt.

## Cách thêm văn bản vào bảng trong Aspose.Slides cho Java

### Tính năng 1: Tạo bảng và thêm văn bản vào các ô

#### Tổng quan
Tính năng này minh họa cách **how to create table**, sau đó **add text to table** các ô và cuối cùng **save presentation as pptx**.

#### Các bước

**1. Create a Table**  
Đầu tiên, khởi tạo bài thuyết trình và thêm một bảng tại vị trí (50, 50) với độ rộng cột và chiều cao hàng được chỉ định.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Tính năng 2: Thêm TextFrame vào AutoShape và thiết lập căn chỉnh

#### Tổng quan
Học cách thêm một khung văn bản với căn chỉnh cụ thể vào một auto shape—ví dụ của **set text alignment java**.

#### Các bước

**1. Add an AutoShape**  
Thêm một hình chữ nhật làm AutoShape tại vị trí (400, 100) với kích thước được chỉ định.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Đặt văn bản thành “Text in shape” và căn chỉnh nó sang trái.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
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

**1. Create a Table**  
Tái sử dụng mã từ “Create Table and Add Text to Cells” để thiết lập ban đầu.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
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

**3. Draw Frames**  
Lặp qua các đoạn văn và các phần để vẽ khung quanh chúng.
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn có thể **add text to table**, căn chỉnh văn bản bên trong các shape, và **draw frames around text** để nhấn mạnh thông tin quan trọng. Thành thạo những kỹ thuật này cho phép bạn tạo ra các bài thuyết trình dữ liệu‑được‑điều khiển rất chuyên nghiệp với Aspose.Slides cho Java. Để khám phá sâu hơn, hãy thử kết hợp các tính năng này với biểu đồ, hoạt ảnh, hoặc xuất ra PDF.

## Câu hỏi thường gặp

**Q: Can I use these APIs with older JDK versions?**  
A: Thư viện hỗ trợ JDK 8 trở lên, nhưng bộ phân loại `jdk16` mang lại hiệu năng tốt nhất trên các runtime mới hơn.

**Q: How do I change the frame color?**  
A: Thay đổi màu nền của định dạng đường viền, ví dụ, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Có—sử dụng `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` và sau đó lưu mảng byte.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Lặp qua `cell.getTextFrame().getParagraphs()`, tìm phần chứa “Total”, và vẽ một hình chữ nhật quanh hộp bao của phần đó.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API truyền dữ liệu theo luồng và giải phóng tài nguyên khi gọi `pres.dispose()`, giúp quản lý bộ nhớ tốt hơn cho các tệp lớn.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}