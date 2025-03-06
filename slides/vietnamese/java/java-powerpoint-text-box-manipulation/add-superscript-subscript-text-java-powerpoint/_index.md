---
title: Thêm văn bản chỉ số trên và chỉ số dưới trong Java PowerPoint
linktitle: Thêm văn bản chỉ số trên và chỉ số dưới trong Java PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách thêm văn bản chỉ số trên và chỉ số dưới trong bản trình bày Java PowerPoint bằng Aspose.Slides cho Java. Hoàn hảo để nâng cao các slide của bạn.
type: docs
weight: 13
url: /vi/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---
## Giới thiệu
Tạo bản trình bày PowerPoint hấp dẫn và giàu thông tin thường yêu cầu sử dụng các tính năng định dạng như văn bản chỉ số trên và chỉ số dưới. Hướng dẫn này sẽ hướng dẫn bạn quy trình kết hợp văn bản chỉ số trên và chỉ số dưới vào bản trình bày Java PowerPoint của bạn bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse được thiết lập để phát triển Java.
- Làm quen cơ bản với lập trình Java và thuyết trình PowerPoint.

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết từ Aspose.Slides cho Java:
```java
import com.aspose.slides.*;
```
## Bước 1: Thiết lập bài thuyết trình
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Bước 2: Truy cập vào Slide
```java
// Nhận slide đầu tiên
ISlide slide = presentation.getSlides().get_Item(0);
```
## Bước 3: Tạo hộp văn bản
```java
// Tạo Hình tự động để dùng làm hộp văn bản
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Bước 4: Thêm văn bản chỉ số trên
```java
// Tạo một đoạn văn cho văn bản chính
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Tạo một phần cho văn bản chỉ số trên
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Đặt lối thoát cho chỉ số trên
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Thêm đoạn văn chính có chỉ số trên vào hộp văn bản
textFrame.getParagraphs().add(mainParagraph);
```
## Bước 5: Thêm văn bản đăng ký
```java
// Tạo một đoạn văn khác cho văn bản chỉ số dưới
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Tạo một phần cho văn bản chỉ số dưới
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Đặt lối thoát cho chỉ số dưới
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Thêm đoạn chỉ số vào hộp văn bản
textFrame.getParagraphs().add(subscriptParagraph);
```
## Bước 6: Lưu bài thuyết trình
```java
// Lưu bài thuyết trình
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách cải thiện bản trình bày PowerPoint Java của bạn bằng văn bản chỉ số trên và chỉ số dưới bằng cách sử dụng Aspose.Slides cho Java. Bằng cách làm theo các bước này, bạn có thể tạo các trang trình bày hấp dẫn và giàu thông tin hơn để truyền đạt nội dung của mình một cách hiệu quả.

## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi bản trình bày PowerPoint theo chương trình.
### Tôi có thể tìm thêm tài liệu về Aspose.Slides cho Java ở đâu?
 Tài liệu chi tiết có thể được tìm thấy[đây](https://reference.aspose.com/slides/java/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho Java?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể dùng thử Aspose.Slides cho Java miễn phí không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Để được hỗ trợ và thảo luận, hãy truy cập[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).