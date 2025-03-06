---
title: Đặt ngôn ngữ trình bày và hình dạng văn bản trong Java
linktitle: Đặt ngôn ngữ trình bày và hình dạng văn bản trong Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tự động hóa bản trình bày PowerPoint bằng Aspose.Slides cho Java. Tạo, sửa đổi và nâng cao các trang trình bày theo chương trình một cách dễ dàng.
weight: 19
url: /vi/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt ngôn ngữ trình bày và hình dạng văn bản trong Java

## Giới thiệu
Việc tạo và thao tác các bản trình bày PowerPoint theo chương trình bằng Java có thể hợp lý hóa quá trình tự động hóa quy trình làm việc và nâng cao năng suất. Aspose.Slides for Java cung cấp một bộ công cụ mạnh mẽ để thực hiện các tác vụ này một cách hiệu quả. Hướng dẫn này hướng dẫn bạn các bước cần thiết để đặt ngôn ngữ trình bày và định hình văn bản bằng Aspose.Slides cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Đã cài đặt Bộ công cụ phát triển Java (JDK)
-  Thư viện Aspose.Slides cho Java mà bạn có thể tải xuống từ[đây](https://releases.aspose.com/slides/java/)
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse được thiết lập trên hệ thống của bạn
- Kiến thức cơ bản về ngôn ngữ lập trình Java
## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói Aspose.Slides cần thiết vào tệp Java của bạn:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Bước 1: Tạo đối tượng trình bày
 Bắt đầu bằng cách khởi tạo một`Presentation` sự vật:
```java
Presentation pres = new Presentation();
```
Điều này tạo ra một bản trình bày PowerPoint mới.
## Bước 2: Thêm và đặt cấu hình hình tự động
Tiếp theo, thêm Hình tự động vào trang chiếu đầu tiên và đặt cấu hình các thuộc tính của nó:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Ở đây, chúng tôi thêm Hình tự động hình chữ nhật tại tọa độ (50, 50) với kích thước 200x50 pixel.
## Bước 3: Đặt văn bản và ngôn ngữ
Đặt nội dung văn bản và chỉ định ngôn ngữ để kiểm tra chính tả:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 Thay thế`"Text to apply spellcheck language"` với văn bản bạn mong muốn. ID ngôn ngữ`"en-EN"`chỉ định tiếng Anh (Hoa Kỳ).
## Bước 4: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào một thư mục đầu ra được chỉ định:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 Đảm bảo thay thế`"Your Output Directory"` với đường dẫn thư mục thực tế của bạn nơi bạn muốn lưu tệp.
## Bước 5: Loại bỏ tài nguyên
 Vứt bỏ đúng cách`Presentation` đối tượng giải phóng tài nguyên:
```java
pres.dispose();
```
Bước này rất quan trọng để tránh rò rỉ bộ nhớ.

## Phần kết luận
Tóm lại, Aspose.Slides cho Java đơn giản hóa quá trình tạo và thao tác với các bản trình bày PowerPoint theo chương trình. Bằng cách làm theo các bước này, bạn có thể đặt ngôn ngữ trình bày và đặt cấu hình các thuộc tính văn bản theo yêu cầu của mình một cách hiệu quả.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho Java để tạo bản trình bày PowerPoint từ đầu không?
Có, Aspose.Slides cung cấp các API toàn diện để tạo bản trình bày hoàn toàn theo chương trình.
### Làm cách nào tôi có thể áp dụng các phông chữ khác nhau cho văn bản trong trang chiếu PowerPoint bằng Aspose.Slides cho Java?
 Bạn có thể đặt thuộc tính phông chữ thông qua`IPortionFormat` các đối tượng được liên kết với các phần văn bản.
### Có phiên bản dùng thử nào cho Aspose.Slides cho Java không?
 Có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Slides cho Java ở đâu?
 Tài liệu chi tiết có sẵn[đây](https://reference.aspose.com/slides/java/).
### Những tùy chọn hỗ trợ nào có sẵn cho Aspose.Slides cho Java?
 Bạn có thể truy cập diễn đàn Aspose.Slides[đây](https://forum.aspose.com/c/slides/11) để hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
