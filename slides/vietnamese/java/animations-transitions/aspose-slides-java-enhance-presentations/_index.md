---
date: '2026-02-09'
description: Học cách vẽ khung quanh văn bản và thêm văn bản vào các ô bảng trong
  PowerPoint bằng Aspose.Slides cho Java. Bài hướng dẫn này bao gồm việc tạo bảng,
  thiết lập căn chỉnh văn bản và lưu bản trình chiếu dưới dạng pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Cách vẽ khung và thêm văn bản vào bảng với Aspose.Slides cho Java
url: /vi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Vẽ Khung và Thêm Văn Bản vào Bảng trong Bản Trình Chiếu với Aspose.Slides cho Java

## Giới thiệu

Một cách rõ ràng để xóa dữ liệu được hiển thị trong PowerPoint có thể là một thực thi công thức, đặc biệt khi bạn cần **thêm văn bản vào bảng** vào các bảng ô và làm nổi bật các quan trọng giá trị bằng dấu hiệu trực tiếp. Trong hướng dẫn này, bạn sẽ học **cách vẽ khung** xung quanh các đoạn văn cụ thể, thiết lập căn chỉnh văn bản bên trong các dạng hình và cuối cùng **lưu bản trình bày dưới dạng pptx**—tất cả đều sử dụng Aspose.Slides cho Java. Khi hoàn thành, bạn sẽ có một bộ slide được chỉnh sửa tinh tế, thu hút ánh mắt giả tưởng đúng nơi bạn mong muốn.

Bạn có sẵn sàng làm slide nổi bật không? Hãy cùng thực hiện quy trình từng bước.

## Trả lời nhanh
- **“Thêm văn bản vào bảng” nghĩa là gì?** Nó có nghĩa là chèn hoặc cập nhật nội dung văn bản của từng ô trong bảng theo chương trình.
- **Phương pháp nào lưu tập tin?** `pres.save("output.pptx", SaveFormat.Pptx)` – bước **lưu bản trình bày dưới dạng pptx** này sẽ hoàn tất các thay đổi của bạn.

- **Làm thế nào để căn chỉnh văn bản bên trong một hình dạng?** Sử dụng `TextAlignment.Left` (hoặc Center/Right) thông qua `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.

- **Tôi có thể vẽ một hình chữ nhật xung quanh một đoạn văn không?** Có – lặp qua các đoạn văn, lấy hình chữ nhật bao quanh chúng và thêm một `IAutoShape` không có màu nền và đường viền màu đen.

- **Tôi có cần giấy phép không?** Giấy phép tạm thời có thể dùng để đánh giá; cần có giấy phép đầy đủ để sử dụng trong môi trường sản xuất.

## Tại sao cần vẽ khung xung quanh văn bản?

Vẽ một khung (hoặc hình chữ nhật) xung quanh một đoạn văn hoặc một phần cụ thể (ví dụ, bất kỳ văn bản nào chứa ký tự **'0'**) ngay lập tức thu hút sự chú ý. Kỹ thuật này lý tưởng cho:

- Làm nổi bật các tài nguyên chính quan trọng trong bảng.
- Nhấn mạnh các cảnh báo hoặc ghi chú quan trọng trong slide.
- Tạo các cách phân tích trực tiếp mà không cần thêm các dạng thủ công.

## Điều kiện tiên quyết

Trước khi bắt đầu viết mã, hãy đảm bảo bạn có những thứ sau:

### Thư viện bắt buộc
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

### Thiết lập môi trường
Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK), JDK16 ưu tiên hoặc mới hơn, vì ví dụ này sử dụng trình phân loại `jdk16`.

### Kiến thức tiên quyết
- Biết cơ bản về cài đặt Java.
- Quen thuộc với các phần mềm tham khảo như PowerPoint.
- Kinh nghiệm sử dụng môi trường phát triển hợp nhất (IDE) như IntelliJ IDEA hoặc Eclipse.

## Thiết lập Aspose.Slides cho Java

Để bắt đầu sử dụng Aspose.Slides, hãy thực hiện theo các bước sau:

1. **Cài đặt Thư viện**: Sử dụng Maven hoặc Gradle để quản lý các phần phụ thuộc hoặc tải xuống trực tiếp từ [Bản phát hành Aspose.Slides dành cho Java](https://releases.aspose.com/slides/java/).

2. **Mua Giấy Phép**:

- Bắt đầu với bản dùng thử miễn phí bằng cách tải xuống giấy phép tạm thời từ [Giấy phép Tạm thời](https://purchase.aspose.com/temporary-license/).

- Để có quyền truy cập đầy đủ, hãy cân nhắc mua giấy phép tại [Mua Aspose.Slides](https://purchase.aspose.com/buy).

3. **Khởi tạo Cơ bản**:
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

## Cách Thêm Văn Bản Vào Bảng trong Aspose.Slides for Java

### Tính năng 1: Tạo Bảng và Thêm Văn Bản Vào Ô

#### Tổng quan

Cách làm như sau: **tạo bảng**, sau đó **thêm văn bản vào bảng** vào các ô và cuối cùng **lưu bản trình bày dưới dạng pptx**.

#### Các bước

**1. Tạo Bảng** 
Trước tiên, khởi tạo bản trình bày của bạn và thêm một bảng tại vị trí (50,50) với chiều rộng cột và chiều cao hàng được chỉ định.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Thêm Văn Bản Vào Ô** 
Tạo các đoạn văn bản và thêm chúng vào một ô cụ thể.
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

**3. Lưu Bản Trình bày** 
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Tính năng 2: Thêm TextFrame vào AutoShape và Căn chỉnh

#### Tổng quan
Tìm hiểu cách thêm một bản văn khung với công cụ chỉnh sửa vào một hình dạng tự động—ví dụ về **đặt căn chỉnh văn bản java**.

#### Bước

**1. 1. Thêm hình tự động**
Thêm một hình chữ nhật làm hình tự động tại vị trí (400,100) với kích thước đã chỉ định.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Thiết lập căn chỉnh văn bản**
Đặt văn bản thành “Văn bản trong hình” và căn chỉnh sang trái.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Lưu bản trình bày** 
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Tính năng 3: Vẽ khung xung quanh đoạn văn và phần trong ô bảng

#### Tổng quan

Tính năng này tập trung vào **vẽ khung xung quanh văn bản** và thậm chí **vẽ hình chữ nhật xung quanh đoạn văn** cho các phần chứa ký tự ‘0’.

#### Các bước

**1. Tạo bảng**
Sử dụng lại mã từ “Tạo bảng và thêm văn bản vào ô” để thiết lập ban đầu.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Thêm đoạn văn**
Sử dụng lại mã tạo đoạn văn từ tính năng trước.
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
Lặp lại các đoạn văn và phần để vẽ khung xung quanh chúng.
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

**4. Lưu bản trình bày**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Những Lỗi Thường Gặp & Mẹo

- **Kiểm tra giá trị null** – Luôn luôn đặt việc sử dụng `Presentation` trong khối try-finally để đảm bảo `pres.dispose()` được chạy và giải phóng các tài nguyên gốc.

- **Độ chính xác của hình chữ nhật bao quanh** – Hình chữ nhật được trả về bởi `para.getRect()` phản ánh bố cục hiện tại; nếu bạn thay đổi kích thước phông chữ hoặc lề, hãy tính toán lại hình chữ nhật trước khi vẽ khung.

- **Hiệu suất** – Khi làm việc với các bảng rất lớn, hãy xem xét việc thêm hình dạng theo lô hoặc sử dụng lại một thể hiện `IAutoShape` duy nhất với hình học được cập nhật để giảm chi phí bộ nhớ.

## Câu hỏi thường gặp

**H: Tôi có thể sử dụng các API này với các phiên bản JDK cũ hơn không?**

A: Thư viện hỗ trợ JDK8 trở lên, nhưng bộ phân loại `jdk16` cho hiệu suất tốt nhất trên các runtime mới hơn.

**Hỏi: Làm thế nào để thay đổi màu khung?**
Đáp: Sửa đổi màu nền của định dạng đường kẻ, ví dụ: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Hỏi: Có thể xuất slide cuối cùng dưới dạng hình ảnh không?**
Đáp: Có – hãy sử dụng `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` và sau đó lưu mảng byte.

**Hỏi: Nếu tôi cần chỉ làm nổi bật từ “Total” bên trong một ô thì sao?**
Đáp: Lặp qua `cell.getTextFrame().getParagraphs()`, tìm phần chứa “Total”, và vẽ một hình chữ nhật xung quanh khung bao của phần đó.

**Hỏi: Aspose.Slides có xử lý các bài thuyết trình lớn một cách hiệu quả không?**
Đáp: API truyền dữ liệu và giải phóng tài nguyên khi gọi `pres.dispose()`, điều này giúp quản lý bộ nhớ cho các tệp lớn.

---

**Cập nhật lần cuối:** 09/02/2026
**Đã kiểm thử với:** Aspose.Slides for Java 25.4 (jdk16)
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
