---
"description": "Tìm hiểu cách chuyển đổi bài thuyết trình PowerPoint có ghi chú thành PDF bằng Aspose.Slides for Java. Làm theo hướng dẫn từng bước của chúng tôi với mã nguồn."
"linktitle": "Chuyển đổi chế độ xem Slide Notes sang PDF trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Chuyển đổi chế độ xem Slide Notes sang PDF trong Java Slides"
"url": "/vi/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi chế độ xem Slide Notes sang PDF trong Java Slides


## Giới thiệu về Chuyển đổi chế độ xem Slide Notes sang PDF trong Java Slides

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi bản trình bày PowerPoint có chế độ xem slide ghi chú thành PDF bằng thư viện Aspose.Slides for Java. Thư viện này cung cấp các tính năng mạnh mẽ để làm việc với các bản trình bày PowerPoint trong Java.

## Điều kiện tiên quyết
1. Đã cài đặt Java Development Kit (JDK).
2. Thư viện Aspose.Slides cho Java đã được thêm vào dự án của bạn.

## Bước 1: Nhập các lớp cần thiết
Để bắt đầu, bạn sẽ cần nhập các lớp cần thiết từ thư viện Aspose.Slides. Sau đây là mã để thực hiện điều đó:

```java
import com.aspose.slides.*;
```

## Bước 2: Tải bản trình bày PowerPoint
Bạn nên chuẩn bị sẵn tệp trình bày PowerPoint của mình. Thay thế `"Your Document Directory"` với đường dẫn đến thư mục nơi tệp trình bày của bạn được đặt. Sau đây là mã để tải bản trình bày:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Bước 3: Cấu hình tùy chọn PDF
Bây giờ, hãy cấu hình tùy chọn xuất PDF. Cụ thể, chúng ta sẽ đặt vị trí ghi chú thành "BottomFull" để bao gồm ghi chú bên dưới các slide trong PDF. Đây là mã:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Bạn có thể tùy chỉnh các tùy chọn PDF khác theo yêu cầu của mình.

## Bước 4: Lưu bài thuyết trình dưới dạng PDF với Ghi chú
Cuối cùng, hãy lưu bản trình bày dưới dạng tệp PDF, bao gồm cả ghi chú. Bạn có thể chỉ định tên tệp đầu ra (ví dụ: `"Pdf_Notes_out.pdf"`) và chọn định dạng (`SaveFormat.Pdf`). Sau đây là mã để thực hiện điều đó:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Bước 5: Dọn dẹp tài nguyên
Đừng quên phát hành tài nguyên sau khi hoàn tất bài thuyết trình:

```java
if (presentation != null) presentation.dispose();
```

## Mã nguồn đầy đủ để chuyển đổi chế độ xem Slide Notes sang PDF trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo một đối tượng Presentation biểu diễn một tệp trình bày
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Lưu bài thuyết trình vào ghi chú PDF
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách chuyển đổi các bài thuyết trình PowerPoint có chế độ xem slide ghi chú thành PDF bằng thư viện Aspose.Slides for Java. Chúng tôi đã làm theo hướng dẫn từng bước với mã nguồn để thực hiện chuyển đổi này. Sau đây là những điểm chính:

## Câu hỏi thường gặp

### Làm thế nào để thay đổi vị trí ghi chú trong PDF?

Bạn có thể thay đổi vị trí ghi chú trong PDF bằng cách sửa đổi `setNotesPosition` phương pháp đối số. Ví dụ, bạn có thể đặt nó thành `NotesPositions.RightFull` để đặt ghi chú ở bên phải của trang chiếu.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Tôi có thể tùy chỉnh thêm việc xuất PDF không?

Có, bạn có thể tùy chỉnh việc xuất PDF bằng cách điều chỉnh nhiều tùy chọn khác nhau trong `PdfOptions` đối tượng. Ví dụ, bạn có thể thiết lập chất lượng, độ nén và các thông số khác theo nhu cầu của mình.

### Làm thế nào tôi có thể tải Aspose.Slides cho Java?

Bạn có thể tải xuống Aspose.Slides cho Java từ trang web tại [đây](https://releases.aspose.com/slides/java/).

### Có yêu cầu cấp phép nào khi sử dụng Aspose.Slides không?

Có, Aspose.Slides yêu cầu giấy phép hợp lệ để sử dụng thương mại. Bạn có thể lấy giấy phép từ trang web Aspose.

### Tôi có thể tìm thêm tài liệu và ví dụ ở đâu?

Bạn có thể tìm thấy tài liệu và ví dụ toàn diện về Aspose.Slides cho Java tại [đây](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}