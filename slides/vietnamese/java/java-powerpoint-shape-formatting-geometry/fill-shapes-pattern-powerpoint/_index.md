---
title: Tô hình dạng bằng mẫu trong PowerPoint
linktitle: Tô hình dạng bằng mẫu trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tô các hình dạng có mẫu trong PowerPoint bằng Aspose.Slides cho Java. Hãy làm theo hướng dẫn từng bước dễ dàng của chúng tôi để cải thiện bản trình bày của bạn một cách trực quan.
type: docs
weight: 11
url: /vi/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---
## Giới thiệu
Tạo các bài thuyết trình hấp dẫn trực quan là điều cần thiết để thu hút khán giả của bạn. Một cách để cải thiện các trang chiếu PowerPoint của bạn là lấp đầy các hình bằng các mẫu. Trong hướng dẫn này, chúng ta sẽ hướng dẫn các bước để tô các hình bằng các mẫu bằng Aspose.Slides cho Java. Hướng dẫn này được thiết kế riêng cho các nhà phát triển muốn tận dụng các tính năng mạnh mẽ của Aspose.Slides để tạo các bản trình bày ấn tượng theo chương trình.
## Điều kiện tiên quyết
Trước khi đi sâu vào mã, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Kiến thức cơ bản về lập trình Java.
## Gói nhập khẩu
Đầu tiên, hãy nhập các gói cần thiết cho ví dụ của chúng tôi.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Bước 1: Thiết lập dự án của bạn
Trước khi viết mã, hãy đảm bảo dự án của bạn được thiết lập chính xác. Tạo một dự án Java mới trong IDE của bạn và thêm thư viện Aspose.Slides for Java vào các phần phụ thuộc của dự án của bạn.
## Bước 2: Tạo thư mục tài liệu
Để quản lý các tệp của bạn một cách hiệu quả, hãy tạo một thư mục nơi chúng tôi sẽ lưu bản trình bày PowerPoint của mình.
```java
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Đoạn mã này kiểm tra xem thư mục có tồn tại hay không và tạo nó nếu không.
## Bước 3: Khởi tạo lớp trình bày
 Tiếp theo, chúng ta cần tạo một thể hiện của`Presentation` class, đại diện cho tệp PowerPoint của chúng tôi.
```java
Presentation pres = new Presentation();
```
Thao tác này sẽ khởi tạo một đối tượng trình bày mới mà chúng ta sẽ sử dụng để thêm các trang trình bày và hình dạng.
## Bước 4: Truy cập Slide đầu tiên
Để bắt đầu, chúng ta cần truy cập vào slide đầu tiên trong bài thuyết trình của mình. Đây là nơi chúng ta sẽ thêm các hình dạng của mình.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Bước 5: Thêm hình chữ nhật
Hãy thêm một hình chữ nhật vào slide của chúng ta. Hình chữ nhật này sẽ được lấp đầy bằng một mẫu.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Đoạn mã này thêm một hình chữ nhật vào trang chiếu ở vị trí và kích thước được chỉ định.
## Bước 6: Đặt Loại điền thành Mẫu
Bây giờ, chúng ta cần đặt kiểu tô của hình chữ nhật thành kiểu tô mẫu.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Bước 7: Chọn kiểu mẫu
Aspose.Slides cung cấp nhiều kiểu mẫu khác nhau. Trong ví dụ này, chúng tôi sẽ sử dụng mẫu "Trellis".
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Bước 8: Đặt màu mẫu
Chúng tôi có thể tùy chỉnh màu sắc của mẫu của chúng tôi. Hãy đặt màu nền thành màu xám nhạt và màu nền trước thành màu vàng.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Bước 9: Lưu bài thuyết trình
Sau khi thiết lập hình dạng của chúng ta với mẫu mong muốn, chúng ta cần lưu bản trình bày vào một tệp.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Thao tác này sẽ lưu bản trình bày vào thư mục đã chỉ định với tên tệp "RectShpPatt_out.pptx".
## Bước 10: Dọn dẹp tài nguyên
Cách tốt nhất là loại bỏ đối tượng trình bày để giải phóng tài nguyên.
```java
if (pres != null) pres.dispose();
```
## Phần kết luận
Chúc mừng! Bạn đã điền thành công một hình có mẫu trong slide PowerPoint bằng Aspose.Slides cho Java. Thư viện mạnh mẽ này cho phép bạn tạo và thao tác các bài thuyết trình một cách dễ dàng, tăng thêm nét chuyên nghiệp cho các dự án của bạn.
 Bằng cách làm theo hướng dẫn từng bước này, bạn có thể nâng cao bản trình bày của mình bằng nhiều mẫu khác nhau, khiến chúng trở nên hấp dẫn và hấp dẫn về mặt hình ảnh hơn. Để biết thêm các tính năng nâng cao và tùy chọn tùy chỉnh, hãy nhớ kiểm tra[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/).
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi bản trình bày PowerPoint trong các ứng dụng Java.
### Làm cách nào tôi có thể tải Aspose.Slides cho Java?
 Bạn có thể tải xuống Aspose.Slides cho Java từ[đây](https://releases.aspose.com/slides/java/).
### Có bản dùng thử miễn phí cho Aspose.Slides cho Java không?
 Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể sử dụng Aspose.Slides cho Java để thao tác với các bản trình bày hiện có không?
Có, Aspose.Slides cho Java cho phép bạn mở, chỉnh sửa và lưu các bản trình bày PowerPoint hiện có.
### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Bạn có thể nhận được sự hỗ trợ từ[Diễn đàn hỗ trợ Aspose.Slides](https://forum.aspose.com/c/slides/11).