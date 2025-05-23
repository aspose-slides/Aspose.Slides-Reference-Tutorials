---
"description": "Tìm hiểu cách tạo hình thu nhỏ hệ số tỷ lệ trong Java bằng Aspose.Slides for Java. Hướng dẫn dễ làm theo với hướng dẫn từng bước."
"linktitle": "Tạo hình thu nhỏ hệ số tỷ lệ"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tạo hình thu nhỏ hệ số tỷ lệ"
"url": "/vi/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình thu nhỏ hệ số tỷ lệ

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình thu nhỏ hệ số tỷ lệ bằng Aspose.Slides for Java. Thực hiện theo các hướng dẫn từng bước sau để đạt được kết quả mong muốn.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có đủ các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides cho Java đã được tải xuống và thiết lập trong dự án Java của bạn.
- Hiểu biết cơ bản về ngôn ngữ lập trình Java.

## Nhập gói
Đầu tiên, hãy nhập các gói cần thiết để làm việc với Aspose.Slides vào mã Java của bạn. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Bây giờ, chúng ta hãy chia nhỏ ví dụ được cung cấp thành nhiều bước:
## Bước 1: Thiết lập thư mục tài liệu
Xác định đường dẫn đến thư mục tài liệu nơi lưu trữ tệp bản trình bày PowerPoint.
```java
String dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` với đường dẫn đến thư mục tài liệu thực tế của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
Tạo một thể hiện của lớp Presentation để biểu diễn tệp bản trình bày PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Đảm bảo thay thế `"HelloWorld.pptx"` bằng tên tệp bản trình bày PowerPoint của bạn.
## Bước 3: Tạo hình ảnh toàn màn hình
Tạo hình ảnh toàn cảnh của slide mong muốn trong bản trình bày.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Mã này lấy hình thu nhỏ của hình dạng đầu tiên trên trang chiếu đầu tiên của bản trình bày.
## Bước 4: Lưu hình ảnh
Lưu hình ảnh đã tạo vào đĩa ở định dạng PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Đảm bảo thay thế `"Scaling Factor Thumbnail_out.png"` với tên tập tin đầu ra mong muốn.

## Phần kết luận
Tóm lại, bạn đã tạo thành công hình thu nhỏ hệ số tỷ lệ bằng Aspose.Slides for Java. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng tích hợp chức năng này vào các ứng dụng Java của mình.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE Java nào không?
Có, Aspose.Slides for Java có thể được sử dụng với bất kỳ Môi trường phát triển tích hợp (IDE) Java nào như Eclipse, IntelliJ IDEA hoặc NetBeans.
### Có bản dùng thử miễn phí Aspose.Slides cho Java không?
Có, bạn có thể dùng thử miễn phí Aspose.Slides cho Java bằng cách truy cập [trang web](https://releases.aspose.com/).
### Tôi có thể tìm thấy hỗ trợ cho Aspose.Slides cho Java ở đâu?
Bạn có thể tìm thấy hỗ trợ cho Aspose.Slides cho Java trên [Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Làm thế nào tôi có thể mua Aspose.Slides cho Java?
Bạn có thể mua Aspose.Slides cho Java từ [trang mua hàng](https://purchase.aspose.com/buy).
### Tôi có cần giấy phép tạm thời để sử dụng Aspose.Slides cho Java không?
Có, bạn có thể xin giấy phép tạm thời từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}