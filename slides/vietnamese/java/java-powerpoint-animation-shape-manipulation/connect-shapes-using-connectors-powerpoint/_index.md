---
title: Kết nối các hình dạng bằng cách sử dụng Connectors trong PowerPoint
linktitle: Kết nối các hình dạng bằng cách sử dụng Connectors trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách kết nối các hình dạng bằng trình kết nối trong bản trình bày PowerPoint với Aspose.Slides cho Java. Hướng dẫn từng bước cho người mới bắt đầu.
type: docs
weight: 18
url: /vi/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách kết nối các hình dạng bằng trình kết nối trong bản trình bày PowerPoint với sự trợ giúp của Aspose.Slides cho Java. Hãy làm theo các hướng dẫn từng bước này để kết nối các hình dạng một cách hiệu quả và tạo các trang trình bày hấp dẫn về mặt trực quan.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về ngôn ngữ lập trình Java.
- Đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của bạn.
-  Đã tải xuống và thiết lập Aspose.Slides cho Java. Nếu bạn chưa cài đặt nó, bạn có thể tải xuống từ[đây](https://releases.aspose.com/slides/java/).
- Trình soạn thảo mã như Eclipse hoặc IntelliJ IDEA.

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết để làm việc với Aspose.Slides trong dự án Java của bạn.
```java
import com.aspose.slides.*;

```
## Bước 1: Khởi tạo lớp trình bày
 Khởi tạo`Presentation`lớp, đại diện cho tệp PPTX bạn đang làm việc.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Bước 2: Truy cập Bộ sưu tập Hình dạng
Truy cập bộ sưu tập hình dạng cho trang chiếu đã chọn nơi bạn muốn thêm hình dạng và đường kết nối.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Bước 3: Thêm hình dạng
Thêm các hình dạng cần thiết vào slide. Trong ví dụ này, chúng ta sẽ thêm một hình elip và một hình chữ nhật.
```java
// Thêm hình elip tự động
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Thêm hình chữ nhật tự động
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Bước 4: Thêm trình kết nối
Thêm hình dạng đường kết nối vào bộ sưu tập hình dạng trang chiếu.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Bước 5: Nối các hình dạng với các trình kết nối
Kết nối các hình dạng với đầu nối.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Bước 6: Định tuyến lại trình kết nối
Gọi định tuyến lại để đặt đường dẫn ngắn nhất tự động giữa các hình dạng.
```java
connector.reroute();
```
## Bước 7: Lưu bài thuyết trình
Lưu bản trình bày sau khi kết nối các hình bằng cách sử dụng trình kết nối.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Cuối cùng, đừng quên loại bỏ đối tượng Trình bày.
```java
if (input != null) input.dispose();
```
Bây giờ bạn đã kết nối thành công các hình dạng bằng trình kết nối trong PowerPoint bằng Aspose.Slides cho Java.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách kết nối các hình dạng bằng trình kết nối trong bản trình bày PowerPoint với Aspose.Slides cho Java. Bằng cách làm theo các bước đơn giản này, bạn có thể nâng cao bản trình bày của mình bằng các sơ đồ và lưu đồ hấp dẫn trực quan.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh giao diện của trình kết nối trong Aspose.Slides cho Java không?
Có, bạn có thể tùy chỉnh các thuộc tính khác nhau của đường kết nối như màu sắc, kiểu đường kẻ và độ dày để phù hợp với nhu cầu trình bày của mình.
### Aspose.Slides for Java có tương thích với tất cả các phiên bản PowerPoint không?
Aspose.Slides for Java hỗ trợ nhiều định dạng PowerPoint khác nhau, bao gồm PPTX, PPT và ODP.
### Tôi có thể kết nối nhiều hơn hai hình bằng một đầu nối không?
Có, bạn có thể kết nối nhiều hình dạng bằng các trình kết nối phức tạp do Aspose.Slides for Java cung cấp.
### Aspose.Slides cho Java có hỗ trợ thêm văn bản vào hình dạng không?
Hoàn toàn có thể, bạn có thể dễ dàng thêm văn bản vào hình dạng và trình kết nối theo chương trình bằng cách sử dụng Aspose.Slides cho Java.
### Có diễn đàn cộng đồng hoặc kênh hỗ trợ nào dành cho Aspose.Slides dành cho người dùng Java không?
 Có, bạn có thể tìm thấy các tài nguyên hữu ích, đặt câu hỏi và tương tác với những người dùng khác trên diễn đàn Aspose.Slides[đây](https://forum.aspose.com/c/slides/11).