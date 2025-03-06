---
title: Chuyển đổi sang PDF với các slide ẩn trong Java Slides
linktitle: Chuyển đổi sang PDF với các slide ẩn trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách chuyển đổi bản trình bày PowerPoint sang PDF với các trang trình bày ẩn bằng Aspose.Slides cho Java. Làm theo hướng dẫn từng bước của chúng tôi với mã nguồn để tạo PDF liền mạch.
weight: 27
url: /vi/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi sang PDF với các slide ẩn trong Java Slides


## Giới thiệu Chuyển đổi bản trình bày PowerPoint sang PDF với các slide ẩn bằng Aspose.Slides cho Java

Trong hướng dẫn từng bước này, bạn sẽ tìm hiểu cách chuyển đổi bản trình bày PowerPoint sang PDF trong khi vẫn giữ các trang chiếu ẩn bằng Aspose.Slides cho Java. Các slide ẩn là những slide không được hiển thị trong bản trình bày thông thường nhưng có thể được đưa vào đầu ra PDF. Chúng tôi sẽ cung cấp cho bạn mã nguồn và hướng dẫn chi tiết để đạt được nhiệm vụ này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Slides for Java Library: Đảm bảo bạn đã thiết lập thư viện Aspose.Slides for Java trong dự án Java của mình. Bạn có thể tải nó xuống từ[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/).

2. Môi trường phát triển Java: Bạn nên cài đặt môi trường phát triển Java trên hệ thống của mình.

## Bước 1: Nhập Aspose.Slides cho Java

Trước tiên, bạn cần nhập thư viện Aspose.Slides vào dự án Java của mình. Đảm bảo rằng bạn đã thêm thư viện vào đường dẫn xây dựng dự án của mình.

```java
import com.aspose.slides.*;
```

## Bước 2: Tải bản trình bày PowerPoint

 Bạn sẽ bắt đầu bằng cách tải bản trình bày PowerPoint mà bạn muốn chuyển đổi sang PDF. Thay thế`"Your Document Directory"` Và`"HiddingSlides.pptx"` với đường dẫn tập tin thích hợp.

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Bước 3: Định cấu hình tùy chọn PDF

Định cấu hình các tùy chọn PDF để bao gồm các trang chiếu ẩn trong đầu ra PDF. Bạn có thể làm điều này bằng cách thiết lập`setShowHiddenSlides` tài sản của`PdfOptions` lớp học để`true`.

```java
// Khởi tạo lớp PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Chỉ định rằng tài liệu được tạo phải bao gồm các trang trình bày ẩn
pdfOptions.setShowHiddenSlides(true);
```

## Bước 4: Lưu bản trình bày dưới dạng PDF

 Bây giờ, hãy lưu bản trình bày vào tệp PDF với các tùy chọn được chỉ định. Thay thế`"PDFWithHiddenSlides_out.pdf"` với tên tệp đầu ra mong muốn của bạn.

```java
// Lưu bản trình bày thành PDF với các tùy chọn được chỉ định
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Bước 5: Dọn dẹp tài nguyên

Đảm bảo giải phóng các tài nguyên được bản trình bày sử dụng khi bạn hoàn thành nó.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Mã nguồn hoàn chỉnh để chuyển đổi sang PDF với các slide ẩn trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Khởi tạo lớp PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Chỉ định rằng tài liệu được tạo phải bao gồm các trang trình bày ẩn
	pdfOptions.setShowHiddenSlides(true);
	// Lưu bản trình bày thành PDF với các tùy chọn được chỉ định
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn toàn diện này, bạn đã học cách chuyển đổi bản trình bày PowerPoint sang PDF trong khi vẫn giữ các trang chiếu ẩn bằng Aspose.Slides cho Java. Chúng tôi đã cung cấp cho bạn hướng dẫn từng bước cùng với mã nguồn cần thiết để thực hiện nhiệm vụ này một cách liền mạch.

## Câu hỏi thường gặp

### Làm cách nào để ẩn các slide trong bản trình bày PowerPoint?

Để ẩn một slide trong bản trình bày PowerPoint, hãy làm theo các bước sau:
1. Chọn slide bạn muốn ẩn trong chế độ xem Slide Sorter.
2. Nhấp chuột phải vào slide đã chọn.
3. Chọn "Ẩn trang trình bày" từ menu ngữ cảnh.

### Tôi có thể hiện các trang trình bày ẩn trong Aspose.Slides cho Java theo chương trình không?

 Có, bạn có thể hiện các trang trình bày ẩn trong Aspose.Slides cho Java theo chương trình bằng cách đặt`Hidden` tài sản của`Slide` lớp học để`false`. Đây là một ví dụ:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Thay thế slideIndex bằng chỉ mục của slide ẩn
slide.setHidden(false);
```

### Làm cách nào để tải xuống Aspose.Slides cho Java?

 Bạn có thể tải xuống Aspose.Slides cho Java từ trang web Aspose. Tham quan[Trang tải xuống Aspose.Slides cho Java](https://releases.aspose.com/slides/java/) để có được phiên bản mới nhất.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
