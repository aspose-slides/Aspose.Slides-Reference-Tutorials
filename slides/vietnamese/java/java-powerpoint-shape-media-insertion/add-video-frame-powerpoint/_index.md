---
title: Thêm khung video trong PowerPoint
linktitle: Thêm khung video trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tích hợp liền mạch nội dung video vào bản trình bày PowerPoint bằng Aspose.Slides cho Java. Các trang trình bày của bạn có các yếu tố đa phương tiện để thu hút khán giả.
weight: 17
url: /vi/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm khung video vào bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bằng cách làm theo các hướng dẫn từng bước này, bạn sẽ có thể tích hợp liền mạch nội dung video vào bản trình bày của mình một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn
- Thư viện Aspose.Slides for Java được tải xuống và thiết lập trong dự án Java của bạn
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để sử dụng các chức năng Aspose.Slides trong mã Java của mình. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Bước 1: Thiết lập thư mục tài liệu
Đảm bảo bạn đã thiết lập một thư mục để lưu trữ các tệp PowerPoint của mình.
```java
String dataDir = "Your Document Directory";
```
## Bước 2: Tạo đối tượng trình bày
 Khởi tạo`Presentation` class để thể hiện tệp PowerPoint.
```java
Presentation pres = new Presentation();
```
## Bước 3: Thêm khung hình video vào slide
Lấy slide đầu tiên và thêm khung video vào đó.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## Bước 4: Đặt chế độ phát và âm lượng
Đặt chế độ phát và âm lượng của khung hình video.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Bước 5: Lưu bài thuyết trình
Lưu tệp PowerPoint đã sửa đổi vào đĩa.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm khung video vào bản trình bày PowerPoint bằng Aspose.Slides cho Java. Nâng cao bài thuyết trình của bạn bằng cách kết hợp các yếu tố đa phương tiện để thu hút khán giả một cách hiệu quả.
## Câu hỏi thường gặp
### Tôi có thể thêm video ở bất kỳ định dạng nào vào bản trình bày PowerPoint không?
Aspose.Slides hỗ trợ nhiều định dạng video khác nhau như AVI, WMV, MP4, v.v. Đảm bảo định dạng tương thích với PowerPoint.
### Aspose.Slides có tương thích với các phiên bản Java khác nhau không?
Có, Aspose.Slides cho Java tương thích với JDK phiên bản 6 trở lên.
### Làm cách nào để điều chỉnh kích thước và vị trí của khung hình video?
 Bạn có thể tùy chỉnh kích thước và tọa độ của khung hình video bằng cách sửa đổi các tham số trong`addVideoFrame` phương pháp.
### Tôi có thể kiểm soát cài đặt phát lại của video không?
Có, bạn có thể đặt chế độ phát và âm lượng của khung hình video theo sở thích của mình.
### Tôi có thể tìm thêm hỗ trợ và tài nguyên cho Aspose.Slides ở đâu?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được hỗ trợ, tài liệu và hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
