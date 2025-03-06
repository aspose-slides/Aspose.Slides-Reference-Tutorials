---
title: Lấy phần hình chữ nhật trong PowerPoint bằng Java
linktitle: Lấy phần hình chữ nhật trong PowerPoint bằng Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách lấy phần hình chữ nhật trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước chi tiết này. Hoàn hảo cho các nhà phát triển Java.
weight: 12
url: /vi/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Tạo bản trình bày động trong Java thật dễ dàng với Aspose.Slides cho Java. Trong hướng dẫn này, chúng ta sẽ đi sâu vào chi tiết cơ bản về cách lấy phần hình chữ nhật trong PowerPoint bằng Aspose.Slides. Chúng tôi sẽ đề cập đến mọi thứ từ việc thiết lập môi trường của bạn đến chia nhỏ mã theo từng bước. Vậy hãy bắt đầu!
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu viết mã, hãy đảm bảo bạn có mọi thứ bạn cần để thực hiện suôn sẻ:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK 8 trở lên trên máy của mình.
2.  Aspose.Slides cho Java: Tải xuống phiên bản mới nhất từ[đây](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Eclipse, IntelliJ IDEA hoặc bất kỳ IDE Java nào khác mà bạn chọn.
4. Kiến thức cơ bản về Java: Hiểu biết về lập trình Java là điều cần thiết.
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết. Điều này sẽ bao gồm Aspose.Slides và một số thứ khác để xử lý công việc của chúng tôi một cách hiệu quả.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Bước 1: Thiết lập bài thuyết trình
Bước đầu tiên là tạo một bản trình bày mới. Đây sẽ là canvas của chúng tôi để làm việc.
```java
Presentation pres = new Presentation();
```
## Bước 2: Tạo bảng
Bây giờ, hãy thêm một bảng vào slide đầu tiên của bài thuyết trình. Bảng này sẽ chứa các ô mà chúng ta sẽ thêm văn bản vào.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Bước 3: Thêm đoạn văn vào ô
Tiếp theo, chúng ta sẽ tạo các đoạn văn và thêm chúng vào một ô cụ thể trong bảng. Điều này liên quan đến việc xóa mọi văn bản hiện có và sau đó thêm các đoạn văn mới.
```java
// Tạo đoạn văn
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Thêm văn bản vào ô bảng
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Bước 4: Thêm khung văn bản vào hình tự động
Để làm cho bản trình bày của chúng ta sinh động hơn, chúng ta sẽ thêm khung văn bản vào Hình tự động và căn chỉnh nó.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Bước 5: Tính tọa độ
Chúng ta cần lấy tọa độ của góc trên bên trái của ô trong bảng. Điều này sẽ giúp chúng ta đặt các hình dạng một cách chính xác.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Bước 6: Thêm khung vào đoạn văn và phần
 Sử dụng`IParagraph.getRect()` Và`IPortion.getRect()`phương pháp này, chúng ta có thể thêm khung vào các đoạn văn và các phần của mình. Điều này liên quan đến việc lặp lại các đoạn văn và các phần, tạo các hình dạng xung quanh chúng và tùy chỉnh hình thức của chúng.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Bước 7: Thêm khung vào đoạn văn hình tự động
Tương tự, chúng tôi sẽ thêm khung vào các đoạn văn trong Hình tự động, nâng cao sức hấp dẫn trực quan của bản trình bày.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Bước 8: Lưu bài thuyết trình
Cuối cùng, chúng ta sẽ lưu bản trình bày của mình vào một đường dẫn cụ thể.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Bước 9: Dọn dẹp
Cách tốt nhất là loại bỏ đối tượng trình bày để giải phóng tài nguyên.
```java
if (pres != null) pres.dispose();
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách lấy phần hình chữ nhật trong PowerPoint bằng Aspose.Slides cho Java. Thư viện mạnh mẽ này mở ra nhiều khả năng để tạo các bản trình bày năng động và hấp dẫn về mặt hình ảnh theo chương trình. Tìm hiểu sâu hơn về Aspose.Slides và khám phá nhiều tính năng hơn để nâng cao hơn nữa bản trình bày của bạn.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và thao tác với các bản trình bày PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides cho Java trong các dự án thương mại không?
 Có, Aspose.Slides for Java có thể được sử dụng trong các dự án thương mại. Bạn có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí cho Aspose.Slides cho Java không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Slides cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/slides/java/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho Java?
 Bạn có thể nhận được hỗ trợ từ diễn đàn Aspose[đây](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
