---
title: Kết nối các hình dạng bằng cách sử dụng các trang kết nối trong PowerPoint
linktitle: Kết nối các hình dạng bằng cách sử dụng các trang kết nối trong PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách kết nối các hình dạng trong PowerPoint bằng Aspose.Slides cho Java. Tự động hóa bài thuyết trình của bạn một cách dễ dàng.
weight: 19
url: /vi/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách kết nối các hình dạng bằng các trang kết nối trong PowerPoint bằng Aspose.Slides cho Java. Thư viện mạnh mẽ này cho phép chúng ta thao tác các bản trình bày PowerPoint theo chương trình, thực hiện các tác vụ như kết nối các hình dạng liền mạch và hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình. Bạn có thể tải xuống và cài đặt nó từ[trang mạng](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Tải xuống và cài đặt Aspose.Slides cho Java từ[trang tải xuống](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn một IDE để phát triển Java, chẳng hạn như IntelliJ IDEA, Eclipse hoặc NetBeans.

## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.slides.*;

```
## Bước 1: Truy cập Bộ sưu tập Hình dạng
Truy cập bộ sưu tập hình dạng cho slide đã chọn:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo lớp Trình bày đại diện cho tệp PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Bước 2: Thêm hình dạng kết nối
Thêm hình dạng đường kết nối vào bộ sưu tập hình dạng trang chiếu:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Bước 3: Thêm hình tự động
Thêm các hình dạng tự động như hình elip và hình chữ nhật:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Bước 4: Nối các hình dạng với các đầu nối
Nối các hình dạng với đầu nối:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Bước 5: Thiết lập chỉ mục trang kết nối
Đặt chỉ mục trang kết nối mong muốn cho các hình dạng:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách kết nối các hình dạng bằng các trang kết nối trong PowerPoint bằng Aspose.Slides cho Java. Với kiến thức này, giờ đây bạn có thể tự động hóa và tùy chỉnh bản trình bày PowerPoint của mình một cách dễ dàng.
## Câu hỏi thường gặp
### Có thể sử dụng Aspose.Slides cho Java cho các tác vụ thao tác PowerPoint khác không?
Có, Aspose.Slides cho Java cung cấp nhiều chức năng để tạo, chỉnh sửa và chuyển đổi bản trình bày PowerPoint.
### Aspose.Slides cho Java có được sử dụng miễn phí không?
 Aspose.Slides for Java là một thư viện thương mại nhưng bạn có thể khám phá các tính năng của nó bằng bản dùng thử miễn phí. Thăm nom[đây](https://releases.aspose.com/) để bắt đầu.
### Tôi có thể nhận được hỗ trợ nếu gặp bất kỳ sự cố nào khi sử dụng Aspose.Slides cho Java không?
 Có, bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose[đây](https://forum.aspose.com/c/slides/11).
### Giấy phép tạm thời có sẵn cho Aspose.Slides cho Java không?
 Có, giấy phép tạm thời được cung cấp cho mục đích thử nghiệm và đánh giá. Bạn có thể có được một[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể mua giấy phép Aspose.Slides cho Java ở đâu?
Bạn có thể mua giấy phép từ trang web Aspose[đây](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
