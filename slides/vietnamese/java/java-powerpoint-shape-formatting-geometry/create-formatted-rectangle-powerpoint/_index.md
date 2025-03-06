---
title: Tạo hình chữ nhật có định dạng trong PowerPoint
linktitle: Tạo hình chữ nhật có định dạng trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo và định dạng hình chữ nhật trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước này.
weight: 18
url: /vi/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình chữ nhật được định dạng trong trang chiếu PowerPoint bằng Aspose.Slides cho Java. Chúng tôi sẽ chia nhỏ từng bước để đảm bảo bạn có thể làm theo và triển khai bước này trong các dự án của riêng mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào mã, hãy đề cập đến các điều kiện tiên quyết. Bạn sẽ cần những thứ sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2. Thư viện Aspose.Slides cho Java: Tải xuống và đưa thư viện Aspose.Slides cho Java vào dự án của bạn.
3. Môi trường phát triển tích hợp (IDE): Một IDE như IntelliJ IDEA hoặc Eclipse sẽ giúp trải nghiệm mã hóa của bạn mượt mà hơn.
4. Kiến thức cơ bản về Java: Làm quen với lập trình Java sẽ giúp bạn làm theo hướng dẫn này.
## Gói nhập khẩu
Để bắt đầu, bạn cần nhập các gói cần thiết từ thư viện Aspose.Slides. Đây là cách bạn có thể làm điều đó:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Việc nhập này rất quan trọng vì chúng mang đến các lớp cần thiết để tạo và định dạng hình dạng trong bản trình bày PowerPoint của bạn.
## Bước 1: Thiết lập thư mục dự án
Đầu tiên, bạn cần tạo một thư mục cho dự án của mình. Thư mục này sẽ lưu trữ các tập tin PowerPoint của bạn.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Mã này kiểm tra xem thư mục có tồn tại hay không và tạo nó nếu không. Đó là một cách thực hành tốt để giữ cho các tệp dự án của bạn được ngăn nắp.
## Bước 2: Khởi tạo lớp trình bày
 Tiếp theo, bạn sẽ khởi tạo`Presentation` class, đại diện cho tệp PowerPoint của bạn.
```java
Presentation pres = new Presentation();
```
Dòng mã này tạo một bản trình bày trống, mới mà bạn có thể bắt đầu thêm nội dung vào.
## Bước 3: Thêm slide vào bài thuyết trình
Bây giờ, hãy thêm một slide vào bài thuyết trình của bạn. Theo mặc định, bản trình bày mới chứa một trang trình bày nên chúng tôi sẽ làm việc với trang trình bày đó.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Đoạn mã này lấy slide đầu tiên từ bản trình bày.
## Bước 4: Thêm hình chữ nhật
Bây giờ chúng ta sẽ thêm một hình chữ nhật vào slide.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ở đây, chúng tôi đang thêm một hình chữ nhật có kích thước (chiều rộng, chiều cao) và vị trí (x, y) được chỉ định vào trang chiếu.
## Bước 5: Định dạng hình chữ nhật
Hãy áp dụng một số định dạng để làm cho hình chữ nhật trông hấp dẫn hơn.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Mã này đặt loại tô thành màu đồng nhất và màu tô thành sô cô la.
## Định dạng đường viền của hình chữ nhật
Tiếp theo, chúng ta sẽ định dạng đường viền của hình chữ nhật.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Mã này đặt màu đường viền thành màu đen và chiều rộng đường viền thành 5.
## Bước 6: Lưu bài thuyết trình
Cuối cùng, hãy lưu bản trình bày vào thư mục dự án của bạn.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Dòng mã này lưu bản trình bày dưới dạng tệp PPTX trong thư mục được chỉ định của bạn.
## Bước 7: Dọn dẹp tài nguyên
 Đó là một thực hành tốt để loại bỏ`Presentation` nhằm giải phóng tài nguyên.
```java
if (pres != null) pres.dispose();
```
Điều này đảm bảo rằng tất cả các tài nguyên được phát hành đúng cách.
## Phần kết luận
Tạo và định dạng hình dạng trong bản trình bày PowerPoint bằng Aspose.Slides cho Java là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tự động hóa việc tạo các trang trình bày hấp dẫn về mặt hình ảnh một cách dễ dàng. Cho dù bạn đang phát triển ứng dụng để báo cáo kinh doanh, nội dung giáo dục hay bản trình bày động, Aspose.Slides for Java đều cung cấp các công cụ bạn cần để thành công.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides for Java là thư viện cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi bản trình bày PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE nào không?
Có, bạn có thể sử dụng Aspose.Slides cho Java với bất kỳ IDE tương thích với Java nào như IntelliJ IDEA, Eclipse hoặc NetBeans.
### Làm cách nào tôi có thể dùng thử miễn phí Aspose.Slides cho Java?
 Bạn có thể tải xuống bản dùng thử miễn phí Aspose.Slides cho Java từ[đây](https://releases.aspose.com/).
###  Có cần thiết phải vứt bỏ`Presentation` object?
 Vâng, việc vứt bỏ`Presentation` object giúp giải phóng tài nguyên và tránh rò rỉ bộ nhớ.
### Tôi có thể tìm tài liệu về Aspose.Slides cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
