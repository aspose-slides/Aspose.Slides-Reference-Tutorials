---
title: Áp dụng hiệu ứng bóng ngoài trong Java PowerPoint
linktitle: Áp dụng hiệu ứng bóng ngoài trong Java PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách dễ dàng áp dụng các hiệu ứng bóng bên ngoài trong bản trình bày Java PowerPoint bằng Aspose.Slides với hướng dẫn từng bước chi tiết của chúng tôi.
type: docs
weight: 11
url: /vi/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---
## Giới thiệu
Việc tạo bản trình bày hấp dẫn thường yêu cầu thêm nhiều hiệu ứng khác nhau để nâng cao sức hấp dẫn trực quan cho trang trình bày của bạn. Một hiệu ứng như vậy là bóng bên ngoài, có thể làm cho các phần tử của bạn nổi bật và thêm chiều sâu cho nội dung của bạn. Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình áp dụng hiệu ứng bóng ngoài cho các hình dạng trong bản trình bày PowerPoint bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn từng bước, hãy đảm bảo bạn có mọi thứ mình cần:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên máy của mình. Bạn có thể tải nó xuống từ[trang web của Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides cho Thư viện Java: Tải xuống phiên bản mới nhất từ[Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Sử dụng IDE như IntelliJ IDEA hoặc Eclipse để viết và thực thi mã Java của bạn.
4.  Giấy phép giả định hợp lệ: Bạn có thể mua giấy phép từ[Aspose](https://purchase.aspose.com/buy) hoặc nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.
## Gói nhập khẩu
Trước tiên, bạn sẽ cần nhập các gói cần thiết cho Aspose.Slides. Điều này tạo tiền đề cho việc sử dụng các chức năng mạnh mẽ do thư viện cung cấp.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Hãy chia nhỏ quá trình áp dụng các hiệu ứng bóng ngoài thành các bước có thể quản lý được:
## Bước 1: Thiết lập thư mục dự án
Trước khi bắt đầu viết mã, bạn cần thiết lập thư mục dự án nơi các tệp PowerPoint của bạn sẽ được lưu trữ và truy cập.
Đảm bảo rằng thư mục dự án của bạn tồn tại. Nếu không, hãy tạo nó bằng mã sau:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Bước 2: Khởi tạo bài thuyết trình
Bây giờ, chúng ta cần khởi tạo bản trình bày để thêm các hình dạng và hiệu ứng.

 Tạo một phiên bản mới của`Presentation` class để bắt đầu làm việc với tệp PowerPoint mới.
```java
// Khởi tạo một lớp PPTX
Presentation pres = new Presentation();
```
## Bước 3: Thêm trang trình bày và hình dạng
Tiếp theo, thêm một trang trình bày vào bản trình bày của bạn rồi thêm hình dạng mà bạn sẽ áp dụng hiệu ứng đổ bóng.
### Nhận tài liệu tham khảo cho slide
Truy xuất tham chiếu đến slide đầu tiên trong bản trình bày.
```java
// Nhận tài liệu tham khảo của slide
ISlide sld = pres.getSlides().get_Item(0);
```
### Thêm hình tự động
Thêm Hình tự động hình chữ nhật vào trang chiếu ở tọa độ đã chỉ định.
```java
// Thêm Hình dạng Tự động thuộc loại Hình chữ nhật
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Bước 4: Tùy chỉnh hình dạng
Thêm văn bản vào hình dạng của bạn và điều chỉnh cài đặt tô màu của nó để làm cho hiệu ứng đổ bóng hiển thị rõ hơn.
### Thêm TextFrame vào hình dạng
Chèn văn bản vào hình chữ nhật.
```java
// Thêm TextFrame vào hình chữ nhật
aShp.addTextFrame("Aspose TextBox");
```
### Tắt tô hình dạng
Tắt tính năng tô màu của hình để nhấn mạnh bóng văn bản.
```java
// Tắt tính năng điền hình dạng trong trường hợp chúng ta muốn có bóng của văn bản
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Bước 5: Áp dụng hiệu ứng Outer Shadow
Bây giờ là lúc áp dụng hiệu ứng bóng bên ngoài cho hình dạng này.
### Kích hoạt hiệu ứng bóng ngoài
Kích hoạt hiệu ứng bóng bên ngoài cho hình dạng.
```java
// Thêm bóng ngoài và đặt tất cả các tham số cần thiết
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Định cấu hình tham số bóng
Đặt các thuộc tính khác nhau của bóng như bán kính mờ, hướng, khoảng cách, căn chỉnh và màu sắc.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Bước 6: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày vào đĩa.
```java
//Ghi bài thuyết trình vào đĩa
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Bước 7: Loại bỏ tài nguyên
Đảm bảo rằng bạn giải phóng tài nguyên bằng cách loại bỏ đối tượng trình bày.
```java
// Dọn dẹp tài nguyên
if (pres != null) pres.dispose();
```
## Phần kết luận
Và bạn có nó rồi đấy! Bạn đã áp dụng thành công hiệu ứng đổ bóng bên ngoài cho một hình trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Hiệu ứng này có thể nâng cao đáng kể sự hấp dẫn trực quan của các trang trình bày, làm nổi bật nội dung của bạn.
 Nếu bạn gặp bất kỳ vấn đề nào hoặc cần hỗ trợ thêm, đừng ngần ngại kiểm tra[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/) hoặc ghé thăm[diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11). Chúc mừng mã hóa!
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides for Java là một thư viện mạnh mẽ cho phép bạn tạo, thao tác và chuyển đổi bản trình bày PowerPoint trong các ứng dụng Java.
### Làm cách nào tôi có thể dùng thử miễn phí Aspose.Slides cho Java?
 Bạn có thể tải xuống bản dùng thử miễn phí từ[trang web giả định](https://releases.aspose.com/).
### Tôi có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE nào không?
Có, bạn có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE Java nào như IntelliJ IDEA, Eclipse hoặc NetBeans.
### Làm cách nào để có được giấy phép tạm thời cho Aspose.Slides?
 Bạn có thể nhận được giấy phép tạm thời từ[trang web giả định](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm thêm ví dụ và tài liệu về Aspose.Slides ở đâu?
 Bạn có thể tìm thêm ví dụ và tài liệu chi tiết về[Trang tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/).