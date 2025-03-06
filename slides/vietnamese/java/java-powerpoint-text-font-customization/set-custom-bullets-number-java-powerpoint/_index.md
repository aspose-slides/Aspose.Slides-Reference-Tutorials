---
title: Đặt số đầu dòng tùy chỉnh trong Java PowerPoint
linktitle: Đặt số đầu dòng tùy chỉnh trong Java PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt số dấu đầu dòng tùy chỉnh trong Java PowerPoint bằng Aspose.Slides, nâng cao tính rõ ràng và cấu trúc của bản trình bày theo chương trình.
weight: 15
url: /vi/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt số đầu dòng tùy chỉnh trong Java PowerPoint

## Giới thiệu
Trong thời đại kỹ thuật số ngày nay, việc tạo ra các bài thuyết trình sinh động là rất quan trọng để truyền đạt ý tưởng và dữ liệu một cách hiệu quả. Aspose.Slides for Java cung cấp bộ công cụ mạnh mẽ để thao tác các bản trình bày PowerPoint theo chương trình, cung cấp các tính năng mở rộng để nâng cao quá trình xây dựng bản trình bày của bạn. Bài viết này đi sâu vào việc đặt số dấu đầu dòng tùy chỉnh trong bản trình bày Java PowerPoint bằng Aspose.Slides. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới, hướng dẫn này sẽ hướng dẫn bạn từng bước trong quy trình, đảm bảo bạn có thể tận dụng khả năng này một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau trên môi trường phát triển của mình:
- Đã cài đặt Bộ công cụ phát triển Java (JDK)
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/)
- Hiểu biết cơ bản về ngôn ngữ lập trình Java và các khái niệm hướng đối tượng

## Gói nhập khẩu
Đầu tiên, nhập các lớp Aspose.Slides cần thiết và các thư viện chuẩn Java khác:
```java
import com.aspose.slides.*;
```
## Bước 1: Tạo đối tượng trình bày
Bắt đầu bằng cách tạo bản trình bày PowerPoint mới bằng Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Bước 2: Thêm hình tự động bằng văn bản
Chèn Hình tự động (Hình chữ nhật) trên trang chiếu và truy cập khung văn bản của nó.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Bước 3: Xóa đoạn mặc định
Xóa đoạn văn hiện có mặc định khỏi khung văn bản.
```java
textFrame.getParagraphs().removeAt(0);
```
## Bước 4: Thêm dấu đầu dòng được đánh số
Thêm đoạn văn có dấu đầu dòng được đánh số tùy chỉnh bắt đầu từ những con số cụ thể.
```java
// Đoạn ví dụ có dấu đầu dòng bắt đầu từ 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Đoạn ví dụ có dấu đầu dòng bắt đầu từ 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Đoạn ví dụ có dấu đầu dòng bắt đầu từ 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Bước 5: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày đã sửa đổi vào vị trí bạn mong muốn.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Tóm lại, Aspose.Slides cho Java đơn giản hóa quá trình đặt số dấu đầu dòng tùy chỉnh trong bản trình bày PowerPoint theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể nâng cao độ rõ ràng trực quan và cấu trúc của bản trình bày của mình một cách hiệu quả.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh thêm hình thức của viên đạn không?
Có, Aspose.Slides cung cấp các tùy chọn mở rộng để tùy chỉnh loại dấu đầu dòng, kích thước, màu sắc, v.v.
### Aspose.Slides có tương thích với tất cả các phiên bản PowerPoint không?
Aspose.Slides hỗ trợ các định dạng PowerPoint từ 97-2003 đến các phiên bản mới nhất.
### Làm cách nào tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Slides?
 Thăm nom[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được hỗ trợ kỹ thuật.
### Tôi có thể dùng thử Aspose.Slides trước khi mua không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể mua Aspose.Slides ở đâu?
 Bạn có thể mua Aspose.Slides từ[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
