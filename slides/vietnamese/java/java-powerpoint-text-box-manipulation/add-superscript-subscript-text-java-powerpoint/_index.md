---
"description": "Tìm hiểu cách thêm văn bản chỉ số trên và chỉ số dưới trong bản trình bày Java PowerPoint bằng Aspose.Slides for Java. Hoàn hảo để nâng cao slide của bạn."
"linktitle": "Thêm văn bản chỉ số trên và chỉ số dưới trong Java PowerPoint"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Thêm văn bản chỉ số trên và chỉ số dưới trong Java PowerPoint"
"url": "/vi/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm văn bản chỉ số trên và chỉ số dưới trong Java PowerPoint

## Giới thiệu
Việc tạo các bài thuyết trình PowerPoint hấp dẫn và nhiều thông tin thường yêu cầu sử dụng các tính năng định dạng như văn bản chỉ số trên và chỉ số dưới. Hướng dẫn này sẽ hướng dẫn bạn quy trình kết hợp văn bản chỉ số trên và chỉ số dưới vào các bài thuyết trình Java PowerPoint của bạn bằng Aspose.Slides for Java.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides cho Java. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse được thiết lập để phát triển Java.
- Có hiểu biết cơ bản về lập trình Java và thuyết trình bằng PowerPoint.

## Nhập gói
Đầu tiên, hãy nhập các gói cần thiết từ Aspose.Slides cho Java:
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
// Tạo một AutoShape để làm hộp văn bản
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Bước 4: Thêm văn bản chữ số trên
```java
// Tạo một đoạn văn cho văn bản chính
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Tạo một phần cho văn bản chữ mũ
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Đặt thoát cho chữ số trên
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Thêm đoạn văn chính có chữ mũ vào hộp văn bản
textFrame.getParagraphs().add(mainParagraph);
```
## Bước 5: Thêm văn bản chỉ số dưới
```java
// Tạo một đoạn văn khác cho văn bản chỉ số dưới
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Tạo một phần cho văn bản chỉ số dưới
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Đặt thoát cho chỉ số dưới
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Thêm đoạn văn chỉ số dưới vào hộp văn bản
textFrame.getParagraphs().add(subscriptParagraph);
```
## Bước 6: Lưu bài thuyết trình
```java
// Lưu bài thuyết trình
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách nâng cao bài thuyết trình Java PowerPoint của bạn bằng văn bản chỉ số trên và chỉ số dưới bằng Aspose.Slides for Java. Bằng cách làm theo các bước này, bạn có thể tạo các slide hấp dẫn và nhiều thông tin hơn về mặt hình ảnh, truyền đạt hiệu quả nội dung của bạn.

## Câu hỏi thường gặp
### Aspose.Slides for Java là gì?
Aspose.Slides for Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi các bài thuyết trình PowerPoint theo chương trình.
### Tôi có thể tìm thêm tài liệu về Aspose.Slides cho Java ở đâu?
Có thể tìm thấy tài liệu chi tiết [đây](https://reference.aspose.com/slides/java/).
### Làm thế nào tôi có thể xin được giấy phép tạm thời cho Aspose.Slides cho Java?
Bạn có thể nhận được giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể dùng thử Aspose.Slides cho Java miễn phí không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).
### Tôi có thể nhận hỗ trợ cho Aspose.Slides for Java ở đâu?
Để được hỗ trợ và thảo luận, hãy truy cập [Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}