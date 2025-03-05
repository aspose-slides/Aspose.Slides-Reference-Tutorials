---
title: Áp dụng hiệu ứng Bevel trên Shapes trong PowerPoint
linktitle: Áp dụng hiệu ứng Bevel trên Shapes trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách áp dụng hiệu ứng góc xiên cho hình dạng trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước của chúng tôi. Nâng cao bài thuyết trình của bạn.
type: docs
weight: 13
url: /vi/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---
## Giới thiệu
Tạo các bài thuyết trình hấp dẫn trực quan là rất quan trọng để thu hút và duy trì sự chú ý của khán giả. Việc thêm hiệu ứng góc xiên vào hình dạng có thể nâng cao tính thẩm mỹ tổng thể của trang chiếu, làm cho bản trình bày của bạn trở nên nổi bật. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình áp dụng hiệu ứng góc xiên cho các hình dạng trong PowerPoint bằng Aspose.Slides cho Java. Cho dù bạn là nhà phát triển đang tìm cách tự động hóa việc tạo bản trình bày hay chỉ là người yêu thích mày mò thiết kế thì hướng dẫn này sẽ giúp bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK. Bạn có thể tải nó xuống từ[Trang web của Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides cho Thư viện Java: Tải xuống thư viện từ[Aspose.Slides cho Java](https://releases.aspose.com/slides/java/).
- IDE (Môi trường phát triển tích hợp): Sử dụng bất kỳ IDE nào bạn chọn, chẳng hạn như IntelliJ IDEA, Eclipse hoặc NetBeans.
-  Giấy phép Aspose: Để sử dụng Aspose.Slides không có giới hạn, hãy lấy giấy phép từ[Quyết định mua hàng](https://purchase.aspose.com/buy) hoặc nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết để làm việc với Aspose.Slides trong dự án Java của mình. Đây là cách bạn có thể làm điều đó:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Bước 1: Thiết lập dự án của bạn
 Trước khi bạn có thể bắt đầu viết mã, hãy đảm bảo dự án của bạn được thiết lập chính xác. Bao gồm thư viện Aspose.Slides trong đường dẫn xây dựng dự án của bạn. Nếu bạn đang sử dụng Maven, hãy thêm phần phụ thuộc sau vào`pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## Bước 2: Tạo bản trình bày
 Để bắt đầu làm việc với Aspose.Slides, bạn cần tạo một phiên bản của`Presentation` lớp học. Lớp này đại diện cho một tệp PowerPoint.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo một thể hiện của lớp Trình bày
Presentation pres = new Presentation();
```
## Bước 3: Truy cập Slide đầu tiên
Sau khi tạo bản trình bày, hãy truy cập trang trình bày đầu tiên nơi bạn sẽ thêm và thao tác với các hình dạng.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Bước 4: Thêm hình dạng vào slide
Bây giờ, thêm một hình dạng vào slide. Trong ví dụ này, chúng ta sẽ thêm một hình elip.
```java
// Thêm hình dạng trên slide
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## Bước 5: Áp dụng hiệu ứng Bevel cho hình dạng
Tiếp theo, áp dụng các hiệu ứng vát cho hình dạng để tạo cho nó một diện mạo ba chiều.
```java
// Đặt thuộc tính ThreeDFormat của hình dạng
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## Bước 6: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày dưới dạng tệp PPTX vào thư mục đã chỉ định của bạn.
```java
// Viết bài thuyết trình dưới dạng tệp PPTX
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## Bước 7: Vứt bỏ đối tượng trình bày
 Để giải phóng tài nguyên, hãy luôn đảm bảo rằng`Presentation` đối tượng được xử lý đúng cách.
```java
if (pres != null) pres.dispose();
```
## Phần kết luận
 Áp dụng hiệu ứng góc xiên cho các hình dạng trong bản trình bày PowerPoint bằng Aspose.Slides cho Java là một quy trình đơn giản có thể nâng cao đáng kể sức hấp dẫn trực quan của trang trình bày của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tạo các bài thuyết trình chuyên nghiệp và hấp dẫn. Hãy nhớ khám phá[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/) để biết thêm thông tin chi tiết và các tính năng nâng cao.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và quản lý bản trình bày PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides cho Java miễn phí không?
 Aspose.Slides cung cấp bản dùng thử miễn phí mà bạn có thể tải xuống từ[đây](https://releases.aspose.com/). Để có đầy đủ tính năng, bạn cần phải mua giấy phép.
### Tôi có thể thêm những loại hình dạng nào vào trang trình bày của mình?
Bạn có thể thêm nhiều hình dạng khác nhau như hình chữ nhật, hình elip, đường thẳng và hình dạng tùy chỉnh bằng Aspose.Slides cho Java.
### Có thể áp dụng các hiệu ứng 3D khác ngoài góc xiên không?
Có, Aspose.Slides cho Java cho phép bạn áp dụng nhiều hiệu ứng 3D khác nhau, bao gồm hiệu ứng chiều sâu, ánh sáng và máy ảnh.
### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Bạn có thể nhận được hỗ trợ từ cộng đồng Aspose và nhóm hỗ trợ trên trang web của họ.[diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11).