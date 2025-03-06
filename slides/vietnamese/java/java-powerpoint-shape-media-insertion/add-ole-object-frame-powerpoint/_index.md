---
title: Thêm khung đối tượng OLE trong PowerPoint
linktitle: Thêm khung đối tượng OLE trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tích hợp liền mạch Khung đối tượng OLE vào bản trình bày PowerPoint bằng Aspose.Slides cho Java.
weight: 13
url: /vi/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Việc thêm Khung đối tượng OLE (Liên kết và nhúng đối tượng) vào bản trình bày PowerPoint có thể nâng cao đáng kể sự hấp dẫn trực quan và chức năng của các trang chiếu của bạn. Với Aspose.Slides cho Java, quá trình này trở nên hợp lý và hiệu quả. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước cần thiết để tích hợp liền mạch Khung đối tượng OLE vào bản trình bày PowerPoint của bạn.
### Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình.
2.  Aspose.Slides for Java: Tải xuống và cài đặt Aspose.Slides cho Java từ trang web[đây](https://releases.aspose.com/slides/java/).
3. Hiểu biết cơ bản về lập trình Java: Làm quen với các khái niệm và cú pháp lập trình Java.
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để tận dụng các chức năng của Aspose.Slides cho Java. Đây là cách bạn có thể làm điều đó:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Bước 1: Thiết lập môi trường của bạn
Đảm bảo rằng dự án của bạn được định cấu hình đúng cách và thư viện Aspose.Slides được bao gồm trong đường dẫn lớp của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
Tạo một đối tượng Trình bày để thể hiện tệp PowerPoint bạn đang làm việc:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Khởi tạo lớp Trình bày đại diện cho PPTX
Presentation pres = new Presentation();
```
## Bước 3: Truy cập Slide và tải đối tượng
Truy cập vào slide nơi bạn muốn thêm Khung đối tượng OLE và tải tệp đối tượng:
```java
ISlide sld = pres.getSlides().get_Item(0);
// Tải một tập tin để truyền phát
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## Bước 4: Tạo đối tượng dữ liệu nhúng
Tạo một đối tượng dữ liệu để nhúng tệp:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## Bước 5: Thêm khung đối tượng OLE
Thêm hình dạng Khung đối tượng OLE vào slide:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Bước 6: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào đĩa:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm Khung đối tượng OLE trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Tính năng mạnh mẽ này cho phép bạn nhúng nhiều loại đối tượng khác nhau, nâng cao tính tương tác và sự hấp dẫn trực quan của các trang trình bày của bạn.

## Câu hỏi thường gặp
### Tôi có thể nhúng các đối tượng không phải tệp Excel bằng Aspose.Slides cho Java không?
Có, bạn có thể nhúng nhiều loại đối tượng khác nhau bao gồm tài liệu Word, tệp PDF, v.v.
### Aspose.Slides có tương thích với các phiên bản PowerPoint khác nhau không?
Aspose.Slides cung cấp khả năng tương thích với nhiều phiên bản PowerPoint, đảm bảo tích hợp liền mạch.
### Tôi có thể tùy chỉnh giao diện của Khung đối tượng OLE không?
Tuyệt đối! Aspose.Slides cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện và hoạt động của Khung đối tượng OLE.
### Có phiên bản dùng thử nào cho Aspose.Slides cho Java không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Bạn có thể tìm kiếm sự hỗ trợ và trợ giúp từ diễn đàn Aspose.Slides[đây](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
