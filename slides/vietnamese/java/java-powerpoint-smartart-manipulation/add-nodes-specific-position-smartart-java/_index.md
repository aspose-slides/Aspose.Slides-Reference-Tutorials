---
"description": "Khám phá cách thêm các nút ở các vị trí cụ thể trong SmartArt bằng Java với Aspose.Slides. Tạo các bài thuyết trình động một cách dễ dàng."
"linktitle": "Thêm các nút ở vị trí cụ thể trong SmartArt bằng Java"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm các nút ở vị trí cụ thể trong SmartArt bằng Java"
"url": "/vi/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các nút ở vị trí cụ thể trong SmartArt bằng Java

## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm các nút ở các vị trí cụ thể trong SmartArt bằng Java với Aspose.Slides. SmartArt là một tính năng trong PowerPoint cho phép bạn tạo sơ đồ và biểu đồ hấp dẫn về mặt thị giác.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
2. Thư viện Aspose.Slides cho Java đã được tải xuống. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).
3. Kiến thức cơ bản về ngôn ngữ lập trình Java.

## Nhập gói
Đầu tiên, hãy nhập các gói cần thiết vào mã Java của chúng ta:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Bước 1: Tạo một phiên bản trình bày
Bắt đầu bằng cách tạo một thể hiện của lớp Presentation:
```java
Presentation pres = new Presentation();
```
## Bước 2: Truy cập vào Slide trình bày
Truy cập vào trang chiếu mà bạn muốn thêm SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Bước 3: Thêm hình dạng SmartArt
Thêm hình dạng SmartArt vào trang chiếu:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Bước 4: Truy cập SmartArt Node
Truy cập nút SmartArt tại chỉ mục mong muốn:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Bước 5: Thêm nút con vào vị trí cụ thể
Thêm một nút con mới vào vị trí cụ thể trong nút cha:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Bước 6: Thêm văn bản vào nút
Đặt văn bản cho nút mới được thêm vào:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Bước 7: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách thêm các nút ở các vị trí cụ thể trong SmartArt bằng Java với Aspose.Slides. Bằng cách làm theo các bước này, bạn có thể thao tác các hình dạng SmartArt theo chương trình để tạo các bản trình bày động.
## Câu hỏi thường gặp
### Tôi có thể thêm nhiều nút cùng một lúc không?
Có, bạn có thể thêm nhiều nút theo chương trình bằng cách lặp lại các vị trí mong muốn.
### Aspose.Slides có tương thích với tất cả các phiên bản PowerPoint không?
Aspose.Slides hỗ trợ nhiều định dạng PowerPoint khác nhau, đảm bảo khả năng tương thích với hầu hết các phiên bản.
### Tôi có thể tùy chỉnh giao diện của các nút SmartArt không?
Có, bạn có thể tùy chỉnh giao diện của các nút, bao gồm kích thước, màu sắc và kiểu dáng.
### Aspose.Slides có hỗ trợ các ngôn ngữ lập trình khác không?
Có, Aspose.Slides cung cấp thư viện cho nhiều ngôn ngữ lập trình, bao gồm .NET và Python.
### Có phiên bản dùng thử nào cho Aspose.Slides không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}