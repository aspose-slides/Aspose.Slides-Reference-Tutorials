---
title: Tạo hình thu nhỏ ghi chú con SmartArt
linktitle: Tạo hình thu nhỏ ghi chú con SmartArt
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo hình thu nhỏ ghi chú con SmartArt trong Java bằng Aspose.Slides, cải thiện bản trình bày PowerPoint của bạn một cách dễ dàng.
weight: 15
url: /vi/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách tạo hình thu nhỏ ghi chú con SmartArt trong Java bằng Aspose.Slides. Aspose.Slides là một API Java mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint theo chương trình, cho phép họ tạo, sửa đổi và thao tác các trang chiếu một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2.  Thư viện Aspose.Slides cho Java được tải xuống và định cấu hình trong dự án của bạn. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/slides/java/).

## Gói nhập khẩu
Đảm bảo nhập các gói cần thiết trong lớp Java của bạn:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Bước 1: Thiết lập dự án của bạn
Đảm bảo bạn đã thiết lập và định cấu hình dự án Java bằng thư viện Aspose.Slides.
## Bước 2: Tạo bản trình bày
 Khởi tạo`Presentation` lớp để thể hiện tệp PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Bước 3: Thêm SmartArt
Thêm SmartArt vào slide thuyết trình của bạn:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Bước 4: Lấy tham chiếu nút
Lấy tham chiếu của một nút bằng cách sử dụng chỉ mục của nó:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Bước 5: Nhận hình thu nhỏ
Truy xuất hình ảnh thu nhỏ của nút SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Bước 6: Lưu hình thu nhỏ
Lưu hình ảnh thu nhỏ vào một tập tin:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Lặp lại các bước này cho từng nút SmartArt nếu cần trong bản trình bày của bạn.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo hình thu nhỏ ghi chú con SmartArt trong Java bằng Aspose.Slides. Với kiến thức này, bạn có thể nâng cao bản trình bày PowerPoint của mình theo chương trình, thêm các yếu tố trực quan hấp dẫn một cách dễ dàng.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides để thao tác với các tệp PowerPoint hiện có không?
Có, Aspose.Slides cho phép bạn sửa đổi các tệp PowerPoint hiện có, bao gồm thêm, xóa hoặc chỉnh sửa các trang chiếu cũng như nội dung của chúng.
### Aspose.Slides có hỗ trợ xuất slide sang các định dạng tệp khác nhau không?
Tuyệt đối! Aspose.Slides hỗ trợ xuất các slide sang nhiều định dạng khác nhau, bao gồm PDF, hình ảnh và HTML, cùng nhiều định dạng khác.
### Aspose.Slides có phù hợp với việc tự động hóa PowerPoint cấp doanh nghiệp không?
Có, Aspose.Slides được thiết kế để xử lý các tác vụ tự động hóa PowerPoint cấp doanh nghiệp một cách hiệu quả và đáng tin cậy.
### Tôi có thể tạo sơ đồ SmartArt phức tạp theo chương trình bằng Aspose.Slides không?
Chắc chắn! Aspose.Slides cung cấp hỗ trợ toàn diện để tạo và thao tác các sơ đồ SmartArt có độ phức tạp khác nhau.
### Aspose.Slides có cung cấp hỗ trợ kỹ thuật cho nhà phát triển không?
 Có, Aspose.Slides cung cấp hỗ trợ kỹ thuật chuyên dụng cho các nhà phát triển thông qua[diễn đàn](https://forum.aspose.com/c/slides/11) và các kênh khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
