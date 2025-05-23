---
"description": "Tìm hiểu cách thêm các nút con tùy chỉnh vào SmartArt trong bản trình bày PowerPoint bằng Java với Aspose.Slides. Nâng cao slide của bạn bằng đồ họa chuyên nghiệp một cách dễ dàng."
"linktitle": "Thêm các nút con tùy chỉnh trong SmartArt bằng Java"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm các nút con tùy chỉnh trong SmartArt bằng Java"
"url": "/vi/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các nút con tùy chỉnh trong SmartArt bằng Java

## Giới thiệu
SmartArt là một tính năng mạnh mẽ trong PowerPoint cho phép người dùng tạo đồ họa chuyên nghiệp một cách nhanh chóng và dễ dàng. Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách thêm các nút con tùy chỉnh vào SmartArt bằng Java với Aspose.Slides.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt Java trên hệ thống của mình.
2. Aspose.Slides cho Java: Tải xuống và cài đặt Aspose.Slides cho Java từ [đây](https://releases.aspose.com/slides/java/).

## Nhập gói
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn:
```java
import com.aspose.slides.*;
```
## Bước 1: Tải bài thuyết trình
Tải bản trình bày PowerPoint mà bạn muốn thêm các nút con tùy chỉnh vào SmartArt:
```java
String dataDir = "Your Document Directory";
// Tải bài thuyết trình mong muốn
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Bước 2: Thêm SmartArt vào Slide
Bây giờ, chúng ta hãy thêm SmartArt vào slide:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Bước 3: Di chuyển hình dạng SmartArt
Di chuyển hình SmartArt đến vị trí mới:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Bước 4: Thay đổi chiều rộng hình dạng
Thay đổi chiều rộng của hình SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Bước 5: Thay đổi chiều cao hình dạng
Thay đổi chiều cao của hình SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Bước 6: Xoay hình dạng
Xoay hình SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Bước 7: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày đã sửa đổi:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách thêm các nút con tùy chỉnh vào SmartArt bằng Java với Aspose.Slides. Bằng cách làm theo các bước này, bạn có thể nâng cao bài thuyết trình của mình bằng đồ họa tùy chỉnh, khiến chúng hấp dẫn và chuyên nghiệp hơn.
## Câu hỏi thường gặp
### Tôi có thể thêm các loại bố cục SmartArt khác nhau bằng Aspose.Slides for Java không?
Có, Aspose.Slides for Java hỗ trợ nhiều bố cục SmartArt khác nhau, cho phép bạn chọn bố cục phù hợp nhất với nhu cầu thuyết trình của mình.
### Aspose.Slides for Java có tương thích với các phiên bản PowerPoint khác nhau không?
Aspose.Slides for Java được thiết kế để hoạt động liền mạch với nhiều phiên bản PowerPoint khác nhau, đảm bảo khả năng tương thích và tính nhất quán trên nhiều nền tảng.
### Tôi có thể tùy chỉnh giao diện của hình dạng SmartArt theo chương trình không?
Chắc chắn rồi! Với Aspose.Slides for Java, bạn có thể tùy chỉnh giao diện, kích thước, màu sắc và bố cục của các hình dạng SmartArt theo chương trình để phù hợp với sở thích thiết kế của bạn.
### Aspose.Slides for Java có cung cấp tài liệu và hỗ trợ không?
Có, bạn có thể tìm thấy tài liệu toàn diện và quyền truy cập vào diễn đàn hỗ trợ cộng đồng trên trang web Aspose.
### Có phiên bản dùng thử nào cho Aspose.Slides dành cho Java không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Slides for Java từ trang web để khám phá các tính năng và khả năng của nó trước khi mua [đây](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}