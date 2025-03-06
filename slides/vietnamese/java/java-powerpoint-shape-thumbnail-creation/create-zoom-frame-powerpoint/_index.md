---
title: Tạo khung thu phóng trong PowerPoint
linktitle: Tạo khung thu phóng trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Khung thu phóng hấp dẫn trong PowerPoint bằng Aspose.Slides cho Java. Hãy làm theo hướng dẫn của chúng tôi để thêm các yếu tố tương tác vào bản trình bày của bạn.
weight: 17
url: /vi/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo khung thu phóng trong PowerPoint

## Giới thiệu
Tạo bản trình bày PowerPoint hấp dẫn là một nghệ thuật và đôi khi, những bổ sung nhỏ nhất cũng có thể tạo ra sự khác biệt rất lớn. Một tính năng như vậy là Khung thu phóng, cho phép bạn phóng to các trang chiếu hoặc hình ảnh cụ thể, tạo ra một bản trình bày năng động và tương tác. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Khung thu phóng trong PowerPoint bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.
- Kiến thức cơ bản về lập trình Java.
## Gói nhập khẩu
Để bắt đầu, bạn cần nhập các gói cần thiết vào dự án Java của mình. Những lần nhập này sẽ cung cấp quyền truy cập vào các chức năng Aspose.Slides cần thiết cho hướng dẫn này.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Bước 1: Thiết lập bài thuyết trình
Đầu tiên, chúng ta cần tạo một bài thuyết trình mới và thêm một vài slide vào đó.
```java
// Tên tệp xuất ra
String resultPath = "ZoomFramePresentation.pptx";
// Đường dẫn đến hình ảnh nguồn
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // Thêm slide mới vào bài thuyết trình
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## Bước 2: Tùy chỉnh hình nền slide
Chúng tôi muốn làm cho các trang chiếu của mình trở nên khác biệt về mặt hình ảnh bằng cách thêm màu nền.
### Đặt nền cho slide thứ hai
```java
    // Tạo nền cho slide thứ hai
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // Tạo hộp văn bản cho slide thứ hai
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### Đặt nền cho slide thứ ba
```java
    // Tạo nền cho slide thứ ba
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // Tạo hộp văn bản cho slide thứ ba
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## Bước 3: Thêm khung thu phóng
Bây giờ, hãy thêm Khung thu phóng vào bản trình bày. Chúng tôi sẽ thêm một Khung thu phóng có bản xem trước trang chiếu và một Khung khác có hình ảnh tùy chỉnh.
### Thêm khung thu phóng với bản xem trước slide
```java
    // Thêm đối tượng ZoomFrame với bản xem trước slide
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### Thêm khung thu phóng bằng hình ảnh tùy chỉnh
```java
    // Thêm đối tượng ZoomFrame bằng hình ảnh tùy chỉnh
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## Bước 4: Tùy chỉnh khung thu phóng
Để làm cho Khung thu phóng của chúng tôi nổi bật, chúng tôi sẽ tùy chỉnh giao diện của chúng.
### Tùy chỉnh khung thu phóng thứ hai
```java
    // Đặt định dạng khung thu phóng cho đối tượng zoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### Ẩn nền cho khung thu phóng đầu tiên
```java
    // Không hiển thị nền cho đối tượng zoomFrame1
    zoomFrame1.setShowBackground(false);
```
## Bước 5: Lưu bài thuyết trình
Cuối cùng, chúng tôi lưu bản trình bày của mình vào đường dẫn đã chỉ định.
```java
    // Lưu bài thuyết trình
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Phần kết luận
Tạo Khung thu phóng trong PowerPoint bằng Aspose.Slides cho Java có thể nâng cao đáng kể tính tương tác và mức độ tương tác của bản trình bày của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng thêm cả bản xem trước trang chiếu và hình ảnh tùy chỉnh làm Khung thu phóng, tùy chỉnh chúng để phù hợp với chủ đề bản trình bày của bạn. Chúc bạn trình bày vui vẻ!
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ để tạo và thao tác các bản trình bày PowerPoint theo chương trình.
### Làm cách nào để cài đặt Aspose.Slides cho Java?
 Bạn có thể tải xuống Aspose.Slides cho Java từ[trang mạng](https://releases.aspose.com/slides/java/) và thêm nó vào phần phụ thuộc của dự án của bạn.
### Tôi có thể tùy chỉnh giao diện của Khung thu phóng không?
Có, Aspose.Slides cho phép bạn tùy chỉnh các thuộc tính khác nhau của Khung thu phóng, chẳng hạn như kiểu đường, màu sắc và khả năng hiển thị nền.
### Có thể thêm hình ảnh vào Khung thu phóng không?
Tuyệt đối! Bạn có thể thêm hình ảnh tùy chỉnh vào Khung thu phóng bằng cách đọc tệp hình ảnh và thêm chúng vào bản trình bày.
### Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?
 Bạn có thể tìm thấy tài liệu và ví dụ toàn diện về[Trang tài liệu Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
