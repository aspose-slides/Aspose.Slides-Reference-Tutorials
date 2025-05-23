---
"description": "Tìm hiểu cách thiết lập định dạng bullet fill trong SmartArt bằng Java với Aspose.Slides. Hướng dẫn từng bước để thao tác trình bày hiệu quả."
"linktitle": "Đặt định dạng Bullet Fill trong SmartArt bằng Java"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Đặt định dạng Bullet Fill trong SmartArt bằng Java"
"url": "/vi/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Đặt định dạng Bullet Fill trong SmartArt bằng Java

## Giới thiệu
Trong lĩnh vực lập trình Java, việc thao tác hiệu quả các bài thuyết trình là một yêu cầu chung, đặc biệt là khi xử lý các thành phần SmartArt. Aspose.Slides for Java nổi lên như một công cụ mạnh mẽ cho các tác vụ như vậy, cung cấp một loạt các chức năng để xử lý các bài thuyết trình theo chương trình. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình thiết lập định dạng bullet fill trong SmartArt bằng Java với Aspose.Slides, từng bước một.
## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
### Bộ phát triển Java (JDK)
Bạn cần phải cài đặt JDK trên hệ thống của bạn. Bạn có thể tải xuống từ [trang web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) và làm theo hướng dẫn cài đặt.
### Aspose.Slides cho Java
Tải xuống và cài đặt Aspose.Slides cho Java từ [liên kết tải xuống](https://releases.aspose.com/slides/java/). Thực hiện theo hướng dẫn cài đặt được cung cấp trong tài liệu dành cho hệ điều hành cụ thể của bạn.

## Nhập gói
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn về cách thiết lập định dạng dấu đầu dòng trong SmartArt bằng Java với Aspose.Slides.
## Bước 1: Tạo đối tượng trình bày
```java
Presentation presentation = new Presentation();
```
Đầu tiên, hãy tạo một phiên bản mới của lớp Presentation, biểu diễn một bản trình bày trên PowerPoint.
## Bước 2: Thêm SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Tiếp theo, thêm hình dạng SmartArt vào slide. Dòng mã này khởi tạo hình dạng SmartArt mới với kích thước và bố cục được chỉ định.
## Bước 3: Truy cập SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Bây giờ, hãy truy cập vào nút đầu tiên (hoặc bất kỳ nút mong muốn nào) trong hình SmartArt để sửa đổi các thuộc tính của nó.
## Bước 4: Thiết lập định dạng Bullet Fill
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Ở đây, chúng tôi kiểm tra xem định dạng bullet fill có được hỗ trợ không. Nếu có, chúng tôi tải tệp hình ảnh và đặt tệp đó làm bullet fill cho nút SmartArt.
## Bước 5: Lưu bài thuyết trình
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Cuối cùng, lưu bản trình bày đã sửa đổi vào một vị trí đã chỉ định.

## Phần kết luận
Xin chúc mừng! Bạn đã học thành công cách thiết lập định dạng bullet fill trong SmartArt bằng Java với Aspose.Slides. Khả năng này mở ra một thế giới khả năng cho các bài thuyết trình năng động và hấp dẫn về mặt hình ảnh trong các ứng dụng Java.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides for Java để tạo bài thuyết trình từ đầu không?
Chắc chắn rồi! Aspose.Slides cung cấp các API toàn diện để tạo, sửa đổi và thao tác các bài thuyết trình hoàn toàn thông qua mã.
### Aspose.Slides có tương thích với các phiên bản PowerPoint khác nhau không?
Có, Aspose.Slides đảm bảo khả năng tương thích với nhiều phiên bản Microsoft PowerPoint khác nhau, cho phép tích hợp liền mạch vào quy trình làm việc của bạn.
### Tôi có thể tùy chỉnh các thành phần SmartArt ngoài định dạng dấu đầu dòng không?
Thật vậy, Aspose.Slides cho phép bạn tùy chỉnh mọi khía cạnh của hình dạng SmartArt, bao gồm bố cục, kiểu dáng, nội dung, v.v.
### Có phiên bản dùng thử nào cho Aspose.Slides dành cho Java không?
Có, bạn có thể khám phá các tính năng của Aspose.Slides với bản dùng thử miễn phí. Chỉ cần tải xuống từ [trang web](https://releases.aspose.com/slides/java/) và bắt đầu khám phá.
### Tôi có thể tìm thấy hỗ trợ cho Aspose.Slides cho Java ở đâu?
Đối với bất kỳ thắc mắc hoặc hỗ trợ nào, bạn có thể truy cập diễn đàn Aspose.Slides tại [liên kết này](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}