---
title: Áp dụng hiệu ứng xoay 3D trên hình dạng trong PowerPoint
linktitle: Áp dụng hiệu ứng xoay 3D trên hình dạng trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách áp dụng hiệu ứng xoay 3D trên các hình trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước toàn diện này.
weight: 12
url: /vi/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Bạn đã sẵn sàng đưa bài thuyết trình PowerPoint của mình lên một tầm cao mới chưa? Việc thêm hiệu ứng xoay 3D có thể làm cho trang trình bày của bạn trở nên năng động và hấp dẫn hơn. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn từng bước này sẽ chỉ cho bạn cách áp dụng hiệu ứng xoay 3D cho các hình dạng trong PowerPoint bằng Aspose.Slides cho Java. Hãy đi sâu vào ngay!
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn những điều sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải nó xuống từ[Trang web của Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides cho Java: Tải xuống phiên bản mới nhất của Aspose.Slides cho Java từ[Liên kết tải xuống](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Sử dụng IDE như IntelliJ IDEA hoặc Eclipse để mã hóa.
4.  Giấy phép hợp lệ: Nếu bạn không có giấy phép, bạn có thể nhận được giấy phép[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để thử các tính năng.
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết vào dự án Java của bạn. Những thao tác nhập này sẽ giúp bạn xử lý các bản trình bày và hình dạng bằng Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Bước 1: Thiết lập dự án của bạn
Trước khi đi sâu vào mã, hãy thiết lập môi trường dự án của bạn. Đảm bảo bạn đã thêm Aspose.Slides cho Java vào phần phụ thuộc của dự án.
Thêm Aspose.Slides vào dự án của bạn:
1.  Tải xuống tệp JAR Aspose.Slides từ[trang tải xuống](https://releases.aspose.com/slides/java/).
2. Thêm các tệp JAR này vào đường dẫn xây dựng dự án của bạn.
## Bước 2: Tạo bản trình bày PowerPoint mới
Trong bước này, chúng ta sẽ tạo một bản trình bày PowerPoint mới.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation pres = new Presentation();
```
Đoạn mã này khởi tạo một đối tượng trình bày mới nơi chúng ta sẽ thêm các hình dạng của mình.
## Bước 3: Thêm hình chữ nhật
Tiếp theo, hãy thêm hình chữ nhật vào slide đầu tiên.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Mã này thêm hình chữ nhật vào vị trí và kích thước đã chỉ định trên trang chiếu đầu tiên.
## Bước 4: Áp dụng Xoay 3D cho hình chữ nhật
Bây giờ, hãy áp dụng hiệu ứng xoay 3D cho hình chữ nhật.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Ở đây, chúng tôi đặt độ sâu, góc quay của camera, loại camera và loại ánh sáng để mang lại cho hình chữ nhật của chúng tôi một diện mạo 3D.
## Bước 5: Thêm hình dạng đường
Hãy thêm một hình dạng khác, lần này là một đường thẳng vào slide.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Mã này đặt một hình dạng đường thẳng trên trang chiếu.
## Bước 6: Áp dụng Xoay 3D cho đường thẳng
Cuối cùng, chúng ta sẽ áp dụng hiệu ứng xoay 3D cho hình dạng đường thẳng.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Tương tự như hình chữ nhật, chúng ta thiết lập thuộc tính 3D cho hình dạng đường thẳng.
## Bước 7: Lưu bài thuyết trình
Sau khi thêm và định cấu hình hình dạng của bạn, hãy lưu bản trình bày.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Mã này lưu bản trình bày của bạn với tên tệp được chỉ định ở định dạng mong muốn.
## Phần kết luận
 Chúc mừng! Bạn đã áp dụng thành công hiệu ứng xoay 3D cho các hình trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Bằng cách làm theo các bước này, bạn có thể tạo các bài thuyết trình sinh động và hấp dẫn về mặt hình ảnh. Để tùy chỉnh thêm và các tính năng nâng cao hơn, hãy tham khảo[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/).
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ để tạo, sửa đổi và thao tác với các bản trình bày PowerPoint theo chương trình.
### Tôi có thể dùng thử Aspose.Slides cho Java miễn phí không?
 Vâng, bạn có thể nhận được một[dùng thử miễn phí](https://releases.aspose.com/) hoặc một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để kiểm tra các tính năng.
### Tôi có thể thêm hiệu ứng 3D vào những loại hình dạng nào trong Aspose.Slides?
Bạn có thể thêm hiệu ứng 3D vào nhiều hình dạng khác nhau như hình chữ nhật, đường thẳng, hình elip và hình dạng tùy chỉnh.
### Làm cách nào để nhận được hỗ trợ cho Aspose.Slides cho Java?
 Bạn có thể ghé thăm[diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11) để được hỗ trợ và thảo luận mọi vấn đề.
### Tôi có thể sử dụng Aspose.Slides cho Java trong các dự án thương mại không?
 Có, nhưng bạn cần phải mua giấy phép. Bạn có thể mua một cái từ[trang mua hàng](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
