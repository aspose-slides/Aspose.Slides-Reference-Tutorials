---
title: Đặt định dạng điền dấu đầu dòng trong SmartArt bằng Java
linktitle: Đặt định dạng điền dấu đầu dòng trong SmartArt bằng Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt định dạng điền dấu đầu dòng trong SmartArt bằng Java với Aspose.Slides. Hướng dẫn từng bước để thao tác trình bày hiệu quả.
type: docs
weight: 18
url: /vi/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Giới thiệu
Trong lĩnh vực lập trình Java, việc thao tác hiệu quả các bản trình bày là một yêu cầu phổ biến, đặc biệt là khi xử lý các phần tử SmartArt. Aspose.Slides for Java nổi lên như một công cụ mạnh mẽ cho những tác vụ như vậy, cung cấp một loạt chức năng để xử lý các bài thuyết trình theo chương trình. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình thiết lập định dạng điền dấu đầu dòng trong SmartArt bằng cách sử dụng Java với Aspose.Slides, từng bước một.
## Điều kiện tiên quyết
Trước khi chúng ta bắt tay vào hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### Bộ công cụ phát triển Java (JDK)
 Bạn cần cài đặt JDK trên hệ thống của mình. Bạn có thể tải nó xuống từ[trang mạng](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) và làm theo hướng dẫn cài đặt.
### Aspose.Slides cho Java
 Tải xuống và cài đặt Aspose.Slides cho Java từ[Liên kết tải xuống](https://releases.aspose.com/slides/java/). Làm theo hướng dẫn cài đặt được cung cấp trong tài liệu dành cho hệ điều hành cụ thể của bạn.

## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu rõ về cách đặt định dạng điền dấu đầu dòng trong SmartArt bằng cách sử dụng Java với Aspose.Slides.
## Bước 1: Tạo đối tượng trình bày
```java
Presentation presentation = new Presentation();
```
Đầu tiên, tạo một phiên bản mới của lớp Trình bày, đại diện cho bản trình bày PowerPoint.
## Bước 2: Thêm SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Tiếp theo, thêm hình SmartArt vào slide. Dòng mã này khởi tạo hình SmartArt mới với các kích thước và bố cục được chỉ định.
## Bước 3: Truy cập nút SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Bây giờ, hãy truy cập nút đầu tiên (hoặc bất kỳ nút nào bạn muốn) trong hình dạng SmartArt để sửa đổi các thuộc tính của nó.
## Bước 4: Đặt định dạng điền dấu đầu dòng
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Ở đây, chúng tôi kiểm tra xem định dạng điền dấu đầu dòng có được hỗ trợ hay không. Nếu đúng như vậy, chúng tôi tải một tệp hình ảnh và đặt nó làm dấu đầu dòng cho nút SmartArt.
## Bước 5: Lưu bài thuyết trình
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Cuối cùng, lưu bản trình bày đã sửa đổi vào một vị trí được chỉ định.

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách đặt định dạng điền dấu đầu dòng trong SmartArt bằng Java với Aspose.Slides. Khả năng này mở ra vô số khả năng cho các bài thuyết trình năng động và hấp dẫn về mặt hình ảnh trong các ứng dụng Java.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho Java để tạo bản trình bày từ đầu không?
Tuyệt đối! Aspose.Slides cung cấp các API toàn diện để tạo, sửa đổi và thao tác các bản trình bày hoàn toàn thông qua mã.
### Aspose.Slides có tương thích với các phiên bản PowerPoint khác nhau không?
Có, Aspose.Slides đảm bảo khả năng tương thích với nhiều phiên bản Microsoft PowerPoint khác nhau, cho phép tích hợp liền mạch vào quy trình làm việc của bạn.
### Tôi có thể tùy chỉnh các phần tử SmartArt ngoài định dạng điền dấu đầu dòng không?
Thật vậy, Aspose.Slides cho phép bạn tùy chỉnh mọi khía cạnh của hình dạng SmartArt, bao gồm bố cục, kiểu dáng, nội dung, v.v.
### Có phiên bản dùng thử nào cho Aspose.Slides cho Java không?
 Có, bạn có thể khám phá các tính năng của Aspose.Slides bằng bản dùng thử miễn phí. Chỉ cần tải xuống từ[trang mạng](https://releases.aspose.com/slides/java/) và bắt đầu khám phá.
### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Nếu có bất kỳ thắc mắc hoặc hỗ trợ nào, bạn có thể truy cập diễn đàn Aspose.Slides tại[liên kết này](https://forum.aspose.com/c/slides/11).