---
"description": "Tìm hiểu cách tạo hình thu nhỏ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Có hướng dẫn từng bước."
"linktitle": "Tạo hình thu nhỏ trong PowerPoint"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Tạo hình thu nhỏ trong PowerPoint"
"url": "/vi/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình thu nhỏ trong PowerPoint

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc tạo hình thu nhỏ trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PowerPoint theo chương trình, cho phép tự động hóa nhiều tác vụ khác nhau, bao gồm cả việc tạo hình thu nhỏ.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng đủ các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides for Java đã được tải xuống và thiết lập trong dự án của bạn. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

## Nhập gói
Trước tiên, bạn cần nhập các gói cần thiết vào mã Java của mình để sử dụng các chức năng của Aspose.Slides. Bao gồm các câu lệnh nhập sau vào đầu tệp Java của bạn:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Bước 1: Xác định thư mục tài liệu
```java
String dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` với đường dẫn đến thư mục chứa tệp PowerPoint của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Tạo một phiên bản mới của `Presentation` lớp, truyền đường dẫn đến tệp PowerPoint của bạn dưới dạng tham số.
## Bước 3: Tạo hình thu nhỏ
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Lấy hình thu nhỏ của hình dạng mong muốn từ trang chiếu đầu tiên của bản trình bày.
## Bước 4: Lưu hình ảnh thu nhỏ
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Lưu hình ảnh thu nhỏ đã tạo vào đĩa ở định dạng PNG với tên tệp đã chỉ định.

## Phần kết luận
Tóm lại, hướng dẫn này đã trình bày cách tạo hình thu nhỏ hình dạng trong bản trình bày PowerPoint bằng Aspose.Slides for Java. Bằng cách làm theo hướng dẫn từng bước và sử dụng các đoạn mã được cung cấp, bạn có thể tạo hình thu nhỏ hình dạng một cách hiệu quả theo chương trình.

## Câu hỏi thường gặp
### Tôi có thể tạo hình thu nhỏ cho các hình dạng trên bất kỳ trang chiếu nào trong bản trình bày không?
Có, bạn có thể sửa đổi mã để nhắm mục tiêu vào hình dạng trên bất kỳ slide nào bằng cách điều chỉnh chỉ mục slide cho phù hợp.
### Aspose.Slides có hỗ trợ các định dạng hình ảnh khác để lưu hình thu nhỏ không?
Có, bên cạnh PNG, Aspose.Slides còn hỗ trợ lưu hình thu nhỏ ở nhiều định dạng hình ảnh khác nhau như JPEG, GIF và BMP.
### Aspose.Slides có phù hợp để sử dụng cho mục đích thương mại không?
Có, Aspose.Slides cung cấp giấy phép thương mại cho các doanh nghiệp và tổ chức. Bạn có thể mua giấy phép từ [đây](https://purchase.aspose.com/buy).
### Tôi có thể dùng thử Aspose.Slides trước khi mua không?
Chắc chắn rồi! Bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Slides từ [đây](https://releases.aspose.com/) để đánh giá các tính năng và khả năng của nó.
### Tôi có thể tìm hỗ trợ cho Aspose.Slides ở đâu?
Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ với Aspose.Slides, bạn có thể truy cập [Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được hỗ trợ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}