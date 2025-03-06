---
title: Thay đổi văn bản trên nút SmartArt bằng Java
linktitle: Thay đổi văn bản trên nút SmartArt bằng Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Khám phá cách cập nhật văn bản nút SmartArt trong PowerPoint bằng Java với Aspose.Slides, nâng cao khả năng tùy chỉnh bản trình bày.
weight: 22
url: /vi/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
SmartArt trong PowerPoint là một tính năng mạnh mẽ để tạo các sơ đồ hấp dẫn về mặt trực quan. Aspose.Slides cho Java cung cấp hỗ trợ toàn diện để thao tác các phần tử SmartArt theo chương trình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thay đổi văn bản trên nút SmartArt bằng Java.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides cho Java được tải xuống và tham chiếu trong dự án Java của bạn.
- Hiểu biết cơ bản về lập trình Java.

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết để truy cập chức năng Aspose.Slides trong mã Java của bạn.
```java
import com.aspose.slides.*;
```
Hãy chia ví dụ thành nhiều bước:
## Bước 1: Khởi tạo đối tượng trình bày
```java
Presentation presentation = new Presentation();
```
 Tạo một phiên bản mới của`Presentation` lớp để làm việc với bài thuyết trình PowerPoint.
## Bước 2: Thêm SmartArt vào Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Thêm SmartArt vào slide đầu tiên. Trong ví dụ này, chúng tôi đang sử dụng`BasicCycle` cách trình bày.
## Bước 3: Truy cập nút SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Nhận tham chiếu đến nút gốc thứ hai của SmartArt.
## Bước 4: Đặt văn bản trên nút
```java
node.getTextFrame().setText("Second root node");
```
Đặt văn bản cho nút SmartArt đã chọn.
## Bước 5: Lưu bài thuyết trình
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Lưu bản trình bày đã sửa đổi vào một vị trí được chỉ định.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày cách thay đổi văn bản trên nút SmartArt bằng Java và Aspose.Slides. Với kiến thức này, bạn có thể thao tác linh hoạt các thành phần SmartArt trong bản trình bày PowerPoint của mình, nâng cao sự hấp dẫn và rõ ràng về mặt hình ảnh của chúng.
## Câu hỏi thường gặp
### Tôi có thể thay đổi bố cục của SmartArt sau khi thêm nó vào slide không?
 Có, bạn có thể thay đổi bố cục bằng cách truy cập`SmartArt.setAllNodes(LayoutType)` phương pháp.
### Aspose.Slides có tương thích với Java 11 không?
Có, Aspose.Slides cho Java tương thích với Java 11 và các phiên bản mới hơn.
### Tôi có thể tùy chỉnh giao diện của nút SmartArt theo chương trình không?
Chắc chắn, bạn có thể sửa đổi các thuộc tính khác nhau như màu sắc, kích thước và hình dạng bằng API Aspose.Slides.
### Aspose.Slides có hỗ trợ các loại bố cục SmartArt khác không?
Có, Aspose.Slides hỗ trợ nhiều bố cục SmartArt, cho phép bạn chọn bố cục phù hợp nhất với nhu cầu thuyết trình của mình.
### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Slides ở đâu?
 Bạn có thể ghé thăm[Tài liệu Aspose.Slides](https://reference.aspose.com/slides/java/) để có tài liệu tham khảo và hướng dẫn API chi tiết. Ngoài ra, bạn có thể tìm kiếm sự trợ giúp từ[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) hoặc xem xét việc mua một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để được hỗ trợ chuyên nghiệp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
