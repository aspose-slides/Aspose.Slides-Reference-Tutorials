---
title: Chuyển đổi Chế độ xem slide ghi chú thành PDF trong Java Slides
linktitle: Chuyển đổi Chế độ xem slide ghi chú thành PDF trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách chuyển đổi bản trình bày PowerPoint có ghi chú thành tệp PDF bằng Aspose.Slides cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi về mã nguồn.
weight: 16
url: /vi/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Giới thiệu về Chuyển đổi Notes Slide View sang PDF trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi bản trình bày PowerPoint có chế độ xem trang trình bày ghi chú thành PDF bằng thư viện Aspose.Slides cho Java. Thư viện này cung cấp các tính năng mạnh mẽ để làm việc với bản trình bày PowerPoint bằng Java.

## Điều kiện tiên quyết
1. Đã cài đặt Bộ công cụ phát triển Java (JDK).
2. Thư viện Aspose.Slides dành cho Java đã được thêm vào dự án của bạn.

## Bước 1: Nhập các lớp cần thiết
Để bắt đầu, bạn cần nhập các lớp cần thiết từ thư viện Aspose.Slides. Đây là mã để làm điều đó:

```java
import com.aspose.slides.*;
```

## Bước 2: Tải bản trình bày PowerPoint
 Bạn nên chuẩn bị sẵn file thuyết trình PowerPoint của mình. Thay thế`"Your Document Directory"` với đường dẫn đến thư mục chứa tệp trình bày của bạn. Đây là mã để tải bản trình bày:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Bước 3: Định cấu hình tùy chọn PDF
Bây giờ, hãy định cấu hình các tùy chọn xuất PDF. Cụ thể, chúng tôi sẽ đặt vị trí ghi chú thành "BottomFull" để bao gồm các ghi chú bên dưới các trang chiếu trong tệp PDF. Đây là mã:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Bạn có thể tùy chỉnh các tùy chọn PDF khác theo yêu cầu của mình.

## Bước 4: Lưu bản trình bày dưới dạng PDF kèm Ghi chú
 Cuối cùng, hãy lưu bản trình bày dưới dạng tệp PDF, bao gồm cả ghi chú. Bạn có thể chỉ định tên tệp đầu ra (ví dụ:`"Pdf_Notes_out.pdf"`) và chọn định dạng (`SaveFormat.Pdf`). Đây là mã để làm điều đó:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Bước 5: Dọn dẹp tài nguyên
Đừng quên giải phóng các tài nguyên sau khi bạn hoàn thành bài thuyết trình:

```java
if (presentation != null) presentation.dispose();
```

## Mã nguồn hoàn chỉnh để chuyển đổi ghi chú dạng xem slide sang PDF trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo một đối tượng Trình bày đại diện cho một tệp trình bày
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Lưu bản trình bày vào ghi chú PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách chuyển đổi bản trình bày PowerPoint có ghi chú dạng xem trang chiếu thành tệp PDF bằng thư viện Aspose.Slides cho Java. Chúng tôi đã làm theo hướng dẫn từng bước với mã nguồn để đạt được chuyển đổi này. Dưới đây là những điểm chính:

## Câu hỏi thường gặp

### Làm cách nào để thay đổi vị trí ghi chú trong PDF?

 Bạn có thể thay đổi vị trí ghi chú trong PDF bằng cách sửa đổi`setNotesPosition` đối số phương pháp. Ví dụ: bạn có thể đặt nó thành`NotesPositions.RightFull` để đặt ghi chú ở phía bên phải của slide.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Tôi có thể tùy chỉnh thêm việc xuất PDF không?

 Có, bạn có thể tùy chỉnh việc xuất PDF bằng cách điều chỉnh các tùy chọn khác nhau trong`PdfOptions` sự vật. Ví dụ: bạn có thể đặt chất lượng, độ nén và các thông số khác theo nhu cầu của mình.

### Làm cách nào tôi có thể lấy Aspose.Slides cho Java?

 Bạn có thể tải xuống Aspose.Slides cho Java từ trang web tại[đây](https://releases.aspose.com/slides/java/).

### Có bất kỳ yêu cầu cấp phép nào để sử dụng Aspose.Slides không?

Có, Aspose.Slides yêu cầu giấy phép hợp lệ để sử dụng cho mục đích thương mại. Bạn có thể lấy giấy phép từ trang web Aspose.

### Tôi có thể tìm thêm tài liệu và ví dụ ở đâu?

 Bạn có thể tìm thấy tài liệu và ví dụ toàn diện về Aspose.Slides for Java tại[đây](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
