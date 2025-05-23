---
"description": "Tìm hiểu cách tạo phần hình chữ nhật trong PowerPoint bằng Aspose.Slides for Java với hướng dẫn chi tiết từng bước này. Hoàn hảo cho các nhà phát triển Java."
"linktitle": "Lấy phần hình chữ nhật trong PowerPoint bằng Java"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Lấy phần hình chữ nhật trong PowerPoint bằng Java"
"url": "/vi/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lấy phần hình chữ nhật trong PowerPoint bằng Java

## Giới thiệu
Tạo các bài thuyết trình động trong Java thật dễ dàng với Aspose.Slides for Java. Trong hướng dẫn này, chúng ta sẽ đi sâu vào chi tiết để có được hình chữ nhật phần trong PowerPoint bằng Aspose.Slides. Chúng ta sẽ đề cập đến mọi thứ từ thiết lập môi trường của bạn đến phân tích mã từng bước. Vậy, hãy bắt đầu nào!
## Điều kiện tiên quyết
Trước khi tìm hiểu mã, hãy đảm bảo rằng bạn có mọi thứ cần thiết để theo dõi một cách suôn sẻ:
1. Java Development Kit (JDK): Đảm bảo máy của bạn đã cài đặt JDK 8 trở lên.
2. Aspose.Slides cho Java: Tải xuống phiên bản mới nhất từ [đây](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Eclipse, IntelliJ IDEA hoặc bất kỳ IDE Java nào khác mà bạn chọn.
4. Kiến thức cơ bản về Java: Hiểu biết về lập trình Java là điều cần thiết.
## Nhập gói
Trước tiên, hãy nhập các gói cần thiết. Bao gồm Aspose.Slides và một số gói khác để xử lý tác vụ của chúng ta một cách hiệu quả.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Bước 1: Thiết lập bài thuyết trình
Bước đầu tiên là tạo một bài thuyết trình mới. Đây sẽ là khung làm việc của chúng ta.
```java
Presentation pres = new Presentation();
```
## Bước 2: Tạo bảng
Bây giờ, hãy thêm một bảng vào slide đầu tiên của bài thuyết trình. Bảng này sẽ chứa các ô mà chúng ta sẽ thêm văn bản.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Bước 3: Thêm đoạn văn vào ô
Tiếp theo, chúng ta sẽ tạo các đoạn văn và thêm chúng vào một ô cụ thể trong bảng. Điều này bao gồm việc xóa bất kỳ văn bản hiện có nào và sau đó thêm các đoạn văn mới.
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
## Bước 4: Thêm Khung Văn bản vào Hình dạng Tự động
Để làm cho bài thuyết trình trở nên sinh động hơn, chúng ta sẽ thêm khung văn bản vào AutoShape và thiết lập căn chỉnh cho khung này.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Bước 5: Tính toán tọa độ
Chúng ta cần lấy tọa độ của góc trên bên trái của ô bảng. Điều này sẽ giúp chúng ta đặt các hình dạng chính xác.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Bước 6: Thêm Khung vào Đoạn văn và Phần
Sử dụng `IParagraph.getRect()` Và `IPortion.getRect()` phương pháp, chúng ta có thể thêm khung vào đoạn văn và phần của mình. Điều này bao gồm việc lặp lại các đoạn văn và phần, tạo hình dạng xung quanh chúng và tùy chỉnh giao diện của chúng.
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
## Bước 7: Thêm Khung vào Đoạn văn AutoShape
Tương tự như vậy, chúng ta sẽ thêm khung vào các đoạn văn trong AutoShape, tăng tính hấp dẫn trực quan cho bài thuyết trình.
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
Cuối cùng, chúng ta sẽ lưu bài thuyết trình vào một đường dẫn cụ thể.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Bước 9: Dọn dẹp
Thực hành tốt nhất là loại bỏ đối tượng trình bày để giải phóng tài nguyên.
```java
if (pres != null) pres.dispose();
```
## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách lấy phần hình chữ nhật trong PowerPoint bằng Aspose.Slides for Java. Thư viện mạnh mẽ này mở ra một thế giới khả năng để tạo các bài thuyết trình động và hấp dẫn về mặt hình ảnh theo chương trình. Khám phá sâu hơn vào Aspose.Slides và khám phá thêm nhiều tính năng để nâng cao bài thuyết trình của bạn hơn nữa.
## Câu hỏi thường gặp
### Aspose.Slides for Java là gì?
Aspose.Slides for Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và thao tác các bài thuyết trình PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides cho Java trong các dự án thương mại không?
Có, Aspose.Slides for Java có thể được sử dụng trong các dự án thương mại. Bạn có thể mua giấy phép từ [đây](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí Aspose.Slides cho Java không?
Có, bạn có thể tải xuống bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Slides cho Java ở đâu?
Tài liệu có sẵn [đây](https://reference.aspose.com/slides/java/).
### Tôi có thể nhận được hỗ trợ cho Aspose.Slides cho Java như thế nào?
Bạn có thể nhận được sự hỗ trợ từ diễn đàn Aspose [đây](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}