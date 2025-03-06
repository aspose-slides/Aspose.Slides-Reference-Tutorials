---
title: Định dạng kiểu nối trong PowerPoint
linktitle: Định dạng kiểu nối trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách nâng cao bản trình bày PowerPoint của bạn bằng cách đặt các kiểu nối dòng khác nhau cho các hình dạng bằng Aspose.Slides cho Java. Thực hiện theo hướng dẫn từng bước của chúng tôi.
weight: 15
url: /vi/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Tạo các bản trình bày PowerPoint hấp dẫn về mặt hình ảnh có thể là một nhiệm vụ khó khăn, đặc biệt khi bạn muốn mọi chi tiết đều hoàn hảo. Đây là lúc Aspose.Slides cho Java phát huy tác dụng. Đó là một API mạnh mẽ cho phép bạn tạo, thao tác và quản lý bản trình bày theo chương trình. Một trong những tính năng mà bạn có thể sử dụng là đặt các kiểu nối đường khác nhau cho các hình dạng, điều này có thể nâng cao đáng kể tính thẩm mỹ cho các trang chiếu của bạn. Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách bạn có thể sử dụng Aspose.Slides cho Java để đặt kiểu nối cho các hình dạng trong bản trình bày PowerPoint. 
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, có một số điều kiện tiên quyết bạn cần phải có:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên máy của mình. Bạn có thể tải nó xuống từ[trang web của Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Thư viện Aspose.Slides for Java: Bạn cần tải xuống và đưa Aspose.Slides for Java vào dự án của bạn. Bạn có thể lấy nó từ[đây](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Sử dụng IDE như IntelliJ IDEA, Eclipse hoặc NetBeans để viết và thực thi mã Java của bạn.
4. Kiến thức cơ bản về Java: Hiểu biết cơ bản về lập trình Java sẽ giúp bạn làm theo hướng dẫn.
## Gói nhập khẩu
Trước tiên, bạn cần nhập các gói cần thiết cho Aspose.Slides. Điều này rất cần thiết để truy cập các lớp và phương thức cần thiết cho các thao tác trình bày của chúng ta.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Bước 1: Thiết lập thư mục dự án
Hãy bắt đầu bằng cách tạo một thư mục để lưu trữ các tập tin trình bày của chúng ta. Điều này đảm bảo rằng tất cả các tệp của chúng tôi được sắp xếp và có thể truy cập dễ dàng.
```java
String dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Trong bước này, chúng tôi xác định đường dẫn thư mục và kiểm tra xem nó có tồn tại không. Nếu không, chúng tôi tạo thư mục. Đây là một cách đơn giản nhưng hiệu quả để giữ cho các tập tin của bạn được ngăn nắp.
## Bước 2: Khởi tạo bài thuyết trình
 Tiếp theo, chúng tôi khởi tạo`Presentation` class, đại diện cho tệp PowerPoint của chúng tôi. Đây là nền tảng mà chúng ta sẽ xây dựng các slide và hình dạng của mình.
```java
Presentation pres = new Presentation();
```
Dòng mã này tạo ra một bản trình bày mới. Hãy coi việc này giống như việc mở một tệp PowerPoint trống nơi bạn sẽ thêm tất cả nội dung của mình.
## Bước 3: Thêm hình vào slide
### Nhận slide đầu tiên
Trước khi thêm hình dạng, chúng ta cần tham chiếu đến slide đầu tiên trong bản trình bày của mình. Theo mặc định, bản trình bày mới chứa một trang chiếu trống.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Thêm hình chữ nhật
Bây giờ, hãy thêm ba hình chữ nhật vào slide của chúng ta. Những hình dạng này sẽ thể hiện các kiểu nối đường khác nhau.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
Trong bước này, chúng ta thêm ba hình chữ nhật vào các vị trí được chỉ định trên slide. Mỗi hình chữ nhật sau này sẽ được tạo kiểu khác nhau để thể hiện các kiểu nối khác nhau.
## Bước 4: Tạo kiểu cho các hình dạng
### Đặt màu tô
Chúng ta muốn hình chữ nhật của mình được tô màu đồng nhất. Ở đây, chúng tôi chọn màu đen cho màu tô.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Đặt độ rộng và màu của dòng
Tiếp theo, chúng ta xác định độ rộng và màu sắc của đường kẻ cho mỗi hình chữ nhật. Điều này giúp phân biệt trực quan các kiểu nối.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Bước 5: Áp dụng kiểu tham gia
Điểm nổi bật của hướng dẫn này là thiết lập kiểu nối dòng. Chúng ta sẽ sử dụng ba kiểu khác nhau: Mitre, Bevel và Round.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Mỗi kiểu nối đường mang lại cho các hình dạng một cái nhìn độc đáo ở các góc nơi các đường gặp nhau. Điều này có thể đặc biệt hữu ích để tạo sơ đồ hoặc hình minh họa trực quan khác biệt.
## Bước 6: Thêm văn bản vào hình dạng
Để làm rõ ý nghĩa của mỗi hình dạng, chúng tôi thêm văn bản vào mỗi hình chữ nhật mô tả kiểu nối được sử dụng.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Việc thêm văn bản sẽ giúp xác định các kiểu khác nhau khi bạn trình bày hoặc chia sẻ trang chiếu.
## Bước 7: Lưu bài thuyết trình
Cuối cùng, chúng tôi lưu bản trình bày của mình vào thư mục đã chỉ định.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Lệnh này ghi bản trình bày vào tệp PPTX mà bạn có thể mở bằng Microsoft PowerPoint hoặc bất kỳ phần mềm tương thích nào khác.
## Phần kết luận
Và bạn có nó rồi đấy! Bạn vừa tạo một trang chiếu PowerPoint có ba hình chữ nhật, mỗi hình thể hiện một kiểu nối dòng khác nhau bằng Aspose.Slides cho Java. Hướng dẫn này không chỉ giúp bạn hiểu những điều cơ bản về Aspose.Slides mà còn chỉ ra cách cải thiện bài thuyết trình của bạn bằng các phong cách độc đáo. Chúc bạn trình bày vui vẻ!
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API mạnh mẽ để tạo, thao tác và quản lý bản trình bày PowerPoint theo chương trình.
### Tôi có thể sử dụng Aspose.Slides cho Java trong bất kỳ IDE nào không?
Có, bạn có thể sử dụng Aspose.Slides cho Java trong bất kỳ IDE nào được Java hỗ trợ như IntelliJ IDEA, Eclipse hoặc NetBeans.
### Có bản dùng thử miễn phí cho Aspose.Slides cho Java không?
 Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Các kiểu nối dòng trong PowerPoint là gì?
Kiểu nối đường đề cập đến hình dạng của các góc nơi hai đường gặp nhau. Các kiểu phổ biến bao gồm Mitre, Bevel và Round.
### Tôi có thể tìm thêm tài liệu về Aspose.Slides cho Java ở đâu?
 Bạn có thể tìm tài liệu chi tiết[đây](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
