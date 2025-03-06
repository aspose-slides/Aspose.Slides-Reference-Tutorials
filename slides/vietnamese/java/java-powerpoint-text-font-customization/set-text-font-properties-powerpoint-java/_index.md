---
title: Đặt thuộc tính phông chữ văn bản trong PowerPoint bằng Java
linktitle: Đặt thuộc tính phông chữ văn bản trong PowerPoint bằng Java
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách đặt thuộc tính phông chữ văn bản trong PowerPoint bằng Aspose.Slides cho Java. Hướng dẫn từng bước, dễ dàng dành cho nhà phát triển Java.#Tìm hiểu cách thao tác các thuộc tính phông chữ văn bản PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước này dành cho nhà phát triển Java.
weight: 18
url: /vi/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Trong hướng dẫn này, bạn sẽ tìm hiểu cách sử dụng Aspose.Slides cho Java để đặt các thuộc tính phông chữ văn bản khác nhau trong bản trình bày PowerPoint theo chương trình. Chúng tôi sẽ đề cập đến việc cài đặt loại phông chữ, kiểu (đậm, in nghiêng), gạch chân, kích thước và màu sắc cho văn bản trong trang trình bày.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- JDK được cài đặt trên hệ thống của bạn.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).
- Kiến thức cơ bản về lập trình Java.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse được thiết lập.
## Gói nhập khẩu
Trước tiên, hãy đảm bảo bạn đã nhập các lớp Aspose.Slides cần thiết:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Bước 1: Thiết lập dự án Java của bạn
Tạo một dự án Java mới trong IDE của bạn và thêm thư viện Aspose.Slides vào đường dẫn xây dựng dự án của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
 Khởi tạo một`Presentation` đối tượng làm việc với các tập tin PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Bước 3: Truy cập Slide và Thêm AutoShape
Lấy trang chiếu đầu tiên và thêm Hình tự động (Hình chữ nhật) vào đó:
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## Bước 4: Đặt văn bản thành Hình tự động
Đặt nội dung văn bản thành AutoShape:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## Bước 5: Đặt thuộc tính phông chữ
Truy cập phần văn bản và đặt các thuộc tính phông chữ khác nhau:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// Đặt họ phông chữ
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// Đặt chữ đậm
portion.getPortionFormat().setFontBold(NullableBool.True);
// Đặt chữ nghiêng
portion.getPortionFormat().setFontItalic(NullableBool.True);
// Đặt gạch chân
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// Đặt cỡ chữ
portion.getPortionFormat().setFontHeight(25);
// Đặt màu phông chữ
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Bước 6: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào một tệp:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## Bước 7: Dọn dẹp tài nguyên
Vứt bỏ đối tượng Trình bày để giải phóng tài nguyên:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách sử dụng Aspose.Slides cho Java để tùy chỉnh động các thuộc tính phông chữ văn bản trong các trang chiếu PowerPoint. Bằng cách làm theo các bước này, bạn có thể định dạng văn bản một cách hiệu quả để đáp ứng các yêu cầu thiết kế cụ thể theo chương trình.
## Câu hỏi thường gặp
### Tôi có thể áp dụng những thay đổi phông chữ này cho văn bản hiện có trong trang chiếu PowerPoint không?
 Có, bạn có thể sửa đổi văn bản hiện có bằng cách truy cập văn bản đó`Portion` và áp dụng các thuộc tính phông chữ mong muốn.
### Làm cách nào tôi có thể thay đổi màu phông chữ thành màu gradient hoặc kiểu tô?
 Thay vì`SolidFillColor` , sử dụng`GradientFillColor` hoặc`PatternedFillColor` tương ứng.
### Aspose.Slides có tương thích với các mẫu PowerPoint (.potx) không?
Có, bạn có thể sử dụng Aspose.Slides để làm việc với các mẫu PowerPoint.
### Aspose.Slides có hỗ trợ xuất sang định dạng PDF không?
Có, Aspose.Slides cho phép xuất bản trình bày sang nhiều định dạng khác nhau, bao gồm cả PDF.
### Tôi có thể tìm thêm trợ giúp và hỗ trợ cho Aspose.Slides ở đâu?
 Thăm nom[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và hướng dẫn.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
