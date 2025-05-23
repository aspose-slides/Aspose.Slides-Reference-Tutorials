---
"date": "2025-04-18"
"description": "Tìm hiểu cách nâng cao bài thuyết trình của bạn bằng cách thành thạo thao tác bảng và khung với Aspose.Slides for Java. Hướng dẫn này bao gồm cách tạo bảng, thêm khung văn bản và vẽ khung xung quanh nội dung cụ thể."
"title": "Aspose.Slides for Java&#58; Làm chủ việc thao tác bảng và khung trong bài thuyết trình"
"url": "/vi/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Làm chủ thao tác bảng và khung trong bài thuyết trình với Aspose.Slides cho Java

## Giới thiệu

Trình bày dữ liệu hiệu quả có thể là một thách thức trong PowerPoint. Cho dù bạn là nhà phát triển phần mềm hay nhà thiết kế bài thuyết trình, việc sử dụng các bảng hấp dẫn về mặt thị giác và thêm khung văn bản có thể khiến các slide của bạn hấp dẫn hơn. Hướng dẫn này khám phá cách sử dụng Aspose.Slides for Java để thêm văn bản vào các ô bảng và vẽ khung xung quanh các đoạn văn và phần chứa các ký tự cụ thể như '0'. Bằng cách thành thạo các kỹ thuật này, bạn sẽ nâng cao bài thuyết trình của mình với độ chính xác và phong cách.

### Những gì bạn sẽ học được:
- Tạo bảng trong slide và điền văn bản vào đó.
- Căn chỉnh văn bản trong hình dạng tự động để trình bày tốt hơn.
- Vẽ khung xung quanh đoạn văn và các phần để nhấn mạnh nội dung.
- Ứng dụng thực tế của những tính năng này trong các tình huống thực tế.

Bạn đã sẵn sàng để thay đổi bài thuyết trình của mình chưa? Hãy bắt đầu thôi!

## Điều kiện tiên quyết

Trước khi tìm hiểu mã, hãy đảm bảo bạn có những điều sau:

### Thư viện bắt buộc
Bạn sẽ cần Aspose.Slides for Java. Sau đây là cách đưa nó vào bằng Maven hoặc Gradle:

**Chuyên gia:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cấp độ:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Thiết lập môi trường
Đảm bảo bạn đã cài đặt Java Development Kit (JDK), tốt nhất là JDK 16 trở lên, vì ví dụ này sử dụng `jdk16` bộ phân loại.

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình Java.
- Quen thuộc với phần mềm trình bày như PowerPoint.
- Kinh nghiệm sử dụng Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

## Thiết lập Aspose.Slides cho Java

Để bắt đầu sử dụng Aspose.Slides, hãy làm theo các bước sau:

1. **Cài đặt Thư viện**: Sử dụng Maven hoặc Gradle để quản lý các phụ thuộc hoặc tải xuống trực tiếp từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

2. **Mua lại giấy phép**:
   - Bắt đầu với bản dùng thử miễn phí bằng cách tải xuống giấy phép tạm thời từ [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
   - Để có quyền truy cập đầy đủ, hãy cân nhắc mua giấy phép tại [Mua Aspose.Slides](https://purchase.aspose.com/buy).

3. **Khởi tạo cơ bản**:
Khởi tạo môi trường trình bày của bạn bằng đoạn mã sau:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Mã của bạn ở đây
} finally {
    if (pres != null) pres.dispose();
}
```

## Hướng dẫn thực hiện

Phần này đề cập đến các tính năng khác nhau mà bạn có thể triển khai bằng Aspose.Slides cho Java.

### Tính năng 1: Tạo bảng và thêm văn bản vào ô

#### Tổng quan
Tính năng này hướng dẫn cách tạo bảng trên trang chiếu đầu tiên và điền văn bản vào các ô cụ thể. 

##### Các bước thực hiện:
**1. Tạo một bảng**
Đầu tiên, hãy khởi tạo bản trình bày của bạn và thêm một bảng ở vị trí (50, 50) với chiều rộng cột và chiều cao hàng được chỉ định.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. Thêm văn bản vào ô**
Tạo đoạn văn có các phần văn bản và thêm chúng vào một ô cụ thể.
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
**3. Lưu bài thuyết trình**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Tính năng 2: Thêm TextFrame vào AutoShape và Thiết lập Căn chỉnh

#### Tổng quan
Tìm hiểu cách thêm khung văn bản có căn chỉnh cụ thể vào hình dạng tự động.

##### Các bước thực hiện:
**1. Thêm một AutoShape**
Thêm một hình chữ nhật dưới dạng AutoShape tại vị trí (400, 100) với các kích thước được chỉ định.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. Thiết lập căn chỉnh văn bản**
Đặt văn bản thành "Văn bản trong hình dạng" và căn chỉnh sang bên trái.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. Lưu bài thuyết trình**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Tính năng 3: Vẽ Khung xung quanh Đoạn văn và Phần trong Ô Bảng

#### Tổng quan
Tính năng này tập trung vào việc vẽ khung xung quanh các đoạn văn và phần chứa số '0' trong các ô của bảng.

##### Các bước thực hiện:
**1. Tạo một bảng**
Sử dụng lại mã từ "Tạo bảng và thêm văn bản vào ô" cho thiết lập ban đầu.
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
Lặp lại các đoạn văn và các phần để vẽ khung xung quanh chúng.
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
**4. Lưu bài thuyết trình**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn có thể cải thiện hiệu quả bài thuyết trình của mình bằng Aspose.Slides for Java. Việc thành thạo thao tác bảng và khung cho phép bạn tạo các slide hấp dẫn và bắt mắt hơn. Để khám phá thêm, hãy cân nhắc tìm hiểu thêm các tính năng bổ sung của Aspose.Slides hoặc tích hợp nó với các ứng dụng Java khác.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}