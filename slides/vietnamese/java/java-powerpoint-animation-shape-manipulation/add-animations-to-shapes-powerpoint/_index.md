---
title: Thêm hình động vào hình dạng trong PowerPoint
linktitle: Thêm hình động vào hình dạng trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm hoạt ảnh vào các hình dạng trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn chi tiết này. Hoàn hảo để tạo các bài thuyết trình hấp dẫn.
weight: 10
url: /vi/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình động vào hình dạng trong PowerPoint

## Giới thiệu
Tạo bản trình bày hấp dẫn thường yêu cầu thêm hoạt ảnh vào hình dạng và văn bản. Hoạt ảnh có thể làm cho trang trình bày của bạn trở nên năng động và hấp dẫn hơn, đảm bảo khán giả luôn quan tâm. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm hoạt ảnh vào các hình trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Đến cuối bài viết này, bạn sẽ có thể tạo hoạt ảnh chuyên nghiệp một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có mọi thứ mình cần:
1.  Aspose.Slides cho Thư viện Java: Bạn cần cài đặt thư viện Aspose.Slides cho Java. Bạn có thể[tải về tại đây](https://releases.aspose.com/slides/java/).
2. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên máy của mình.
3. Môi trường phát triển tích hợp (IDE): Sử dụng bất kỳ IDE Java nào như IntelliJ IDEA, Eclipse hoặc NetBeans.
4. Kiến thức cơ bản về Java: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình Java.
## Gói nhập khẩu
Để bắt đầu, bạn cần nhập các gói cần thiết cho Aspose.Slides và các lớp Java bắt buộc khác.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Bước 1: Thiết lập thư mục dự án của bạn
Đầu tiên, tạo một thư mục cho các tập tin dự án của bạn.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Bước 2: Khởi tạo đối tượng trình bày
 Tiếp theo, khởi tạo`Presentation` class để thể hiện tệp PowerPoint của bạn.
```java
// Khởi tạo lớp Trình bày đại diện cho PPTX
Presentation pres = new Presentation();
```
## Bước 3: Truy cập Slide đầu tiên
Bây giờ, hãy truy cập vào trang trình bày đầu tiên trong bản trình bày nơi bạn sẽ thêm hoạt ảnh.
```java
// Truy cập slide đầu tiên
ISlide sld = pres.getSlides().get_Item(0);
```
## Bước 4: Thêm hình dạng vào slide
Thêm hình chữ nhật vào slide và chèn một số văn bản vào đó.
```java
// Thêm hình chữ nhật vào slide
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Bước 5: Áp dụng hiệu ứng hoạt hình
Áp dụng hiệu ứng hoạt hình "PathFootball" cho hình dạng.
```java
// Thêm hiệu ứng hoạt hình PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Bước 6: Tạo Trình kích hoạt tương tác
Tạo hình dạng nút sẽ kích hoạt hoạt ảnh khi được nhấp vào.
```java
// Tạo hình dạng "nút" để kích hoạt hoạt ảnh
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Bước 7: Xác định trình tự tương tác
Xác định chuỗi hiệu ứng cho nút.
```java
// Tạo chuỗi hiệu ứng cho nút
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Bước 8: Thêm đường dẫn người dùng tùy chỉnh
Thêm hoạt ảnh đường dẫn người dùng tùy chỉnh vào hình dạng.
```java
// Thêm hiệu ứng hoạt hình đường dẫn người dùng tùy chỉnh
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Tạo hiệu ứng chuyển động
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Xác định các điểm đường dẫn
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Bước 9: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày vào vị trí mong muốn của bạn.
```java
// Lưu bản trình bày dưới dạng tệp PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Vứt bỏ đối tượng trình bày
if (pres != null) pres.dispose();
```
## Phần kết luận
Và bạn có nó rồi đấy! Bạn đã thêm thành công hoạt ảnh vào các hình trong bản trình bày PowerPoint bằng Aspose.Slides cho Java. Thư viện mạnh mẽ này giúp bạn dễ dàng cải thiện bản trình bày của mình bằng các hiệu ứng động, đảm bảo khán giả của bạn luôn tương tác. Hãy nhớ rằng, luyện tập sẽ tạo nên sự hoàn hảo, vì vậy hãy tiếp tục thử nghiệm các hiệu ứng và kích hoạt khác nhau để xem điều gì phù hợp nhất với nhu cầu của bạn.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ để tạo, sửa đổi và thao tác với các bản trình bày PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides miễn phí không?
 Bạn có thể dùng thử Aspose.Slides miễn phí với[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/). Để tiếp tục sử dụng, cần phải có giấy phép trả phí.
### Phiên bản Java nào tương thích với Aspose.Slides?
Aspose.Slides hỗ trợ Java SE 6 trở lên.
### Làm cách nào để thêm các hoạt ảnh khác nhau vào nhiều hình dạng?
Bạn có thể thêm các hình động khác nhau vào nhiều hình dạng bằng cách lặp lại các bước cho từng hình dạng và chỉ định các hiệu ứng khác nhau nếu cần.
### Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?
 Kiểm tra[tài liệu](https://reference.aspose.com/slides/java/) Và[diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11)để biết thêm ví dụ và trợ giúp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
