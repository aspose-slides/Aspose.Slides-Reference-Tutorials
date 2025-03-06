---
title: Chuyển đổi Slide sang PDF bằng Ghi chú trong Java Slides
linktitle: Chuyển đổi Slide sang PDF bằng Ghi chú trong Java Slides
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách chuyển đổi trang chiếu PowerPoint sang PDF kèm theo ghi chú trong Java bằng Aspose.Slides cho Java. Hướng dẫn từng bước dành cho nhà phát triển Java. Tăng cường chia sẻ bản trình bày của bạn.
weight: 19
url: /vi/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Giới thiệu Chuyển đổi slide sang PDF bằng ghi chú trong Java

Trong thế giới thuyết trình kỹ thuật số, khả năng chuyển đổi slide sang PDF kèm theo ghi chú là một tính năng đáng giá. Các nhà phát triển Java có thể đạt được điều này bằng cách sử dụng thư viện Aspose.Slides for Java, thư viện này cung cấp một bộ công cụ mạnh mẽ để làm việc với các bản trình bày PowerPoint theo chương trình. Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách chuyển đổi trang trình bày sang PDF kèm theo ghi chú bằng Java và Aspose.Slides cho Java.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Slides cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/java/).

Bây giờ chúng ta đã có phác thảo, hãy đi sâu vào thực hiện từng bước.
## Bước 1: Thiết lập dự án

Đầu tiên, tạo một dự án Java và thêm thư viện Aspose.Slides for Java vào các phần phụ thuộc của dự án của bạn.

## Bước 2: Tải bài thuyết trình

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Bước 3: Tạo bản trình bày mới

```java
Presentation auxPresentation = new Presentation();
```

## Bước 4: Sao chép slide

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Bước 5: Điều chỉnh kích thước slide

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Bước 6: Định cấu hình tùy chọn PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Bước 7: Lưu dưới dạng PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Mã nguồn hoàn chỉnh để chuyển đổi slide sang PDF kèm ghi chú trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo một đối tượng Trình bày đại diện cho một tệp trình bày
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Đặt loại và kích thước slide
		//auxPresentation.getSlideSize().setSize(trình bày.getSlideSize().getSize().getWidth(), trình bày.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách chuyển đổi trang trình bày sang PDF kèm ghi chú trong Java bằng cách sử dụng Aspose.Slides cho Java. Chúng tôi đã đề cập đến việc thiết lập dự án, tải bản trình bày, tạo bản trình bày mới, sao chép trang trình bày, điều chỉnh kích thước trang trình bày, định cấu hình tùy chọn PDF và cuối cùng là lưu bản trình bày dưới dạng PDF kèm theo ghi chú.

## Câu hỏi thường gặp

### Làm cách nào để cài đặt Aspose.Slides cho Java?

Để cài đặt Aspose.Slides cho Java, hãy làm theo các bước sau:
1.  Tải thư viện từ[đây](https://releases.aspose.com/slides/java/).
2. Thêm tệp JAR vào đường dẫn lớp của dự án Java của bạn.

### Tôi có thể tùy chỉnh vị trí ghi chú trong tệp PDF được tạo không?

 Có, bạn có thể tùy chỉnh vị trí ghi chú bằng cách sửa đổi`NotesPositions` enum trong các tùy chọn PDF. Trong hướng dẫn này, chúng tôi đặt nó thành`BottomFull`, nhưng bạn cũng có thể khám phá các tùy chọn khác.

### Có bất kỳ yêu cầu cấp phép nào để sử dụng Aspose.Slides cho Java không?

Có, Aspose.Slides for Java là một thư viện thương mại và bạn có thể cần phải có giấy phép để sử dụng nó trong sản xuất. Truy cập trang web Aspose để biết chi tiết cấp phép.

### Tôi có thể chuyển đổi nhiều slide cùng một lúc không?

Chắc chắn! Bạn có thể lặp qua các trang chiếu trong bản trình bày của mình và sao chép chúng vào bản trình bày mới, cho phép bạn chuyển đổi nhiều trang chiếu sang PDF kèm theo ghi chú trong một lần.

### Tôi có thể tìm thêm tài liệu về Aspose.Slides cho Java ở đâu?

 Bạn có thể tìm tài liệu chi tiết về Aspose.Slides for Java trên trang web:[Aspose.Slides để tham khảo API Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
