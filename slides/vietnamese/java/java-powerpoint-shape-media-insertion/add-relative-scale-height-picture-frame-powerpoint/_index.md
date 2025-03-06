---
title: Thêm Khung ảnh Chiều cao Tỷ lệ Tương đối trong PowerPoint
linktitle: Thêm Khung ảnh Chiều cao Tỷ lệ Tương đối trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm khung ảnh có chiều cao tỷ lệ tương đối trong bản trình bày PowerPoint bằng Aspose.Slides cho Java, nâng cao nội dung trực quan của bạn.
weight: 15
url: /vi/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Trong hướng dẫn này, bạn sẽ tìm hiểu cách thêm khung ảnh có chiều cao tỷ lệ tương đối trong bản trình bày PowerPoint bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2. Thư viện Aspose.Slides for Java đã được tải xuống và thêm vào dự án Java của bạn.

## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết trong dự án Java của bạn:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Bước 1: Thiết lập dự án của bạn
Trước tiên, hãy đảm bảo bạn đã thiết lập thư mục cho dự án của mình và môi trường Java của bạn được cấu hình đúng.
## Bước 2: Khởi tạo đối tượng trình bày
Tạo một đối tượng trình bày mới bằng Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Bước 3: Tải hình ảnh cần thêm
Tải hình ảnh bạn muốn thêm vào bài thuyết trình:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Bước 4: Thêm khung ảnh vào slide
Thêm khung ảnh vào slide trong bài thuyết trình:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Bước 5: Đặt chiều rộng và chiều cao tỷ lệ tương đối
Đặt chiều rộng và chiều cao tỷ lệ tương đối cho khung ảnh:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Bước 6: Lưu bài thuyết trình
Lưu bài thuyết trình có khung ảnh được thêm vào:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Bằng cách làm theo các bước này, bạn có thể dễ dàng thêm khung ảnh có chiều cao tỷ lệ tương đối trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Thử nghiệm với các giá trị tỷ lệ khác nhau để đạt được diện mạo mong muốn cho hình ảnh của bạn.

## Câu hỏi thường gặp
### Tôi có thể thêm nhiều khung ảnh vào một slide bằng phương pháp này không?
Có, bạn có thể thêm nhiều khung ảnh vào một trang chiếu bằng cách lặp lại quy trình cho từng hình ảnh.
### Aspose.Slides for Java có tương thích với tất cả các phiên bản PowerPoint không?
Aspose.Slides for Java tương thích với nhiều phiên bản PowerPoint khác nhau, đảm bảo tính linh hoạt trong việc tạo bài thuyết trình.
### Tôi có thể tùy chỉnh vị trí và kích thước của khung ảnh không?
 Hoàn toàn có thể điều chỉnh các thông số vị trí và kích thước trong`addPictureFrame` phương pháp phù hợp với yêu cầu của bạn.
### Aspose.Slides cho Java có hỗ trợ các định dạng hình ảnh khác ngoài JPEG không?
Có, Aspose.Slides cho Java hỗ trợ nhiều định dạng hình ảnh khác nhau, bao gồm PNG, GIF, BMP, v.v.
### Có diễn đàn cộng đồng hoặc kênh hỗ trợ nào dành cho người dùng Aspose.Slides không?
Có, bạn có thể truy cập diễn đàn Aspose.Slides nếu có bất kỳ câu hỏi, thảo luận hoặc hỗ trợ nào về thư viện.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
