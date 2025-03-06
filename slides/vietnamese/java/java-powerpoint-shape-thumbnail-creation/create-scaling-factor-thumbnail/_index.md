---
title: Tạo hình thu nhỏ hệ số tỷ lệ
linktitle: Tạo hình thu nhỏ hệ số tỷ lệ
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo hình thu nhỏ hệ số tỷ lệ trong Java bằng Aspose.Slides cho Java. Hướng dẫn dễ làm theo với hướng dẫn từng bước.
weight: 12
url: /vi/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình thu nhỏ hệ số tỷ lệ

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình thu nhỏ có hệ số tỷ lệ bằng Aspose.Slides cho Java. Thực hiện theo các hướng dẫn từng bước này để đạt được kết quả mong muốn.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides for Java được tải xuống và thiết lập trong dự án Java của bạn.
- Hiểu biết cơ bản về ngôn ngữ lập trình Java.

## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để làm việc với Aspose.Slides trong mã Java của bạn. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước:
## Bước 1: Đặt thư mục tài liệu
Xác định đường dẫn đến thư mục tài liệu của bạn nơi chứa tệp bản trình bày PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu thực tế của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
Tạo một thể hiện của lớp Trình bày để thể hiện tệp bản trình bày PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Đảm bảo thay thế`"HelloWorld.pptx"` với tên của tệp bản trình bày PowerPoint của bạn.
## Bước 3: Tạo hình ảnh tỷ lệ đầy đủ
Tạo hình ảnh có kích thước đầy đủ của slide mong muốn từ bản trình bày.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Mã này truy xuất hình thu nhỏ của hình đầu tiên trên trang chiếu đầu tiên của bản trình bày.
## Bước 4: Lưu hình ảnh
Lưu hình ảnh được tạo vào đĩa ở định dạng PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Đảm bảo thay thế`"Scaling Factor Thumbnail_out.png"` với tên tệp đầu ra mong muốn.

## Phần kết luận
Tóm lại, bạn đã tạo thành công hình thu nhỏ hệ số tỷ lệ bằng Aspose.Slides cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng tích hợp chức năng này vào các ứng dụng Java của mình.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE Java nào không?
Có, Aspose.Slides cho Java có thể được sử dụng với bất kỳ Môi trường phát triển tích hợp Java (IDE) nào như Eclipse, IntelliJ IDEA hoặc NetBeans.
### Có bản dùng thử miễn phí cho Aspose.Slides cho Java không?
 Có, bạn có thể tận dụng bản dùng thử miễn phí Aspose.Slides cho Java bằng cách truy cập[trang mạng](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Bạn có thể tìm thấy hỗ trợ cho Aspose.Slides cho Java trên[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Làm cách nào tôi có thể mua Aspose.Slides cho Java?
 Bạn có thể mua Aspose.Slides cho Java từ[trang mua hàng](https://purchase.aspose.com/buy).
### Tôi có cần giấy phép tạm thời để sử dụng Aspose.Slides cho Java không?
 Có, bạn có thể xin giấy phép tạm thời từ[trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
