---
title: Thêm khung hình video từ nguồn web trong PowerPoint
linktitle: Thêm khung hình video từ nguồn web trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách nâng cao bản trình bày PowerPoint của bạn bằng cách thêm khung hình video từ các nguồn web bằng Aspose.Slides cho Java.
weight: 18
url: /vi/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm khung video từ nguồn web, chẳng hạn như YouTube, vào bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bằng cách làm theo các hướng dẫn từng bước này, bạn sẽ có thể cải thiện bản trình bày của mình bằng cách kết hợp các yếu tố đa phương tiện hấp dẫn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
- JDK (Bộ công cụ phát triển Java) được cài đặt trên hệ thống của bạn.
-  Thư viện Aspose.Slides for Java đã được tải xuống và thêm vào dự án Java của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Kết nối internet đang hoạt động để truy cập nguồn web (ví dụ: YouTube).

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Bước 1: Tạo đối tượng trình bày PowerPoint
Khởi tạo một đối tượng Trình bày, đại diện cho bản trình bày PowerPoint:
```java
Presentation pres = new Presentation();
```
## Bước 2: Thêm khung video
Bây giờ, hãy thêm khung video vào bài thuyết trình. Khung này sẽ chứa video từ nguồn web. Chúng ta sẽ sử dụng phương thức addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Thay thế "VIDEO_ID" bằng ID của video YouTube mà bạn muốn nhúng.
## Bước 3: Đặt Chế độ phát video
Đặt chế độ phát cho khung hình video. Trong ví dụ này, chúng tôi sẽ đặt nó thành Tự động:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Bước 4: Tải hình thu nhỏ
Để nâng cao sự hấp dẫn về mặt hình ảnh, chúng tôi sẽ tải hình thu nhỏ của video. Bước này liên quan đến việc tìm nạp hình ảnh thu nhỏ từ nguồn web:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Bước 5: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày đã sửa đổi:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Thay thế "YOUR_DIRECTORY" bằng thư mục mà bạn muốn lưu bản trình bày.

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm khung video từ nguồn web trong PowerPoint bằng Aspose.Slides cho Java. Việc kết hợp các yếu tố đa phương tiện như video có thể nâng cao đáng kể tác động và mức độ tương tác của bài thuyết trình của bạn.
## Câu hỏi thường gặp
### Tôi có thể thêm video từ các nguồn khác ngoài YouTube không?
Có, bạn có thể thêm video từ nhiều nguồn web khác nhau miễn là chúng cung cấp liên kết có thể nhúng.
### Tôi có cần kết nối Internet để phát video được nhúng không?
Có, cần có kết nối Internet đang hoạt động để truyền phát video từ nguồn web.
### Tôi có thể tùy chỉnh giao diện của khung video không?
Tuyệt đối! Aspose.Slides cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện và hoạt động của khung hình video.
### Aspose.Slides có tương thích với tất cả các phiên bản PowerPoint không?
Aspose.Slides hỗ trợ nhiều phiên bản PowerPoint, đảm bảo khả năng tương thích trên các nền tảng khác nhau.
### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Slides ở đâu?
 Bạn có thể ghé thăm[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được hỗ trợ, tài liệu và hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
