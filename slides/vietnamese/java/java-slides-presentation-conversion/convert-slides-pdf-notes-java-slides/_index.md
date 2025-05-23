---
"description": "Tìm hiểu cách chuyển đổi slide PowerPoint sang PDF có ghi chú trong Java bằng Aspose.Slides for Java. Hướng dẫn từng bước dành cho nhà phát triển Java. Nâng cao khả năng chia sẻ bài thuyết trình của bạn."
"linktitle": "Chuyển đổi Slide sang PDF bằng Notes trong Java Slides"
"second_title": "API xử lý PowerPoint Java của Aspose.Slides"
"title": "Chuyển đổi Slide sang PDF bằng Notes trong Java Slides"
"url": "/vi/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi Slide sang PDF bằng Notes trong Java Slides


## Giới thiệu về Chuyển đổi Slide sang PDF bằng Ghi chú trong Java

Trong thế giới thuyết trình kỹ thuật số, khả năng chuyển đổi slide sang PDF kèm theo ghi chú là một tính năng có giá trị. Các nhà phát triển Java có thể đạt được điều này bằng cách sử dụng thư viện Aspose.Slides for Java, cung cấp một bộ công cụ mạnh mẽ để làm việc với các bài thuyết trình PowerPoint theo chương trình. Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách chuyển đổi slide sang PDF kèm theo ghi chú bằng Java và Aspose.Slides for Java.

## Điều kiện tiên quyết

Trước khi tìm hiểu sâu hơn về mã, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Slides cho Java. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/java/).

Bây giờ chúng ta đã có dàn ý, hãy cùng đi sâu vào từng bước thực hiện.
## Bước 1: Thiết lập dự án

Đầu tiên, hãy tạo một dự án Java và thêm thư viện Aspose.Slides for Java vào phần phụ thuộc của dự án.

## Bước 2: Tải bài thuyết trình

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Bước 3: Tạo bài thuyết trình mới

```java
Presentation auxPresentation = new Presentation();
```

## Bước 4: Sao chép các slide

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Bước 5: Điều chỉnh kích thước Slide

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Bước 6: Cấu hình tùy chọn PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Bước 7: Lưu dưới dạng PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Mã nguồn đầy đủ để chuyển đổi Slide sang PDF với Ghi chú trong Java Slides

```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo một đối tượng Presentation biểu diễn một tệp trình bày 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Thiết lập Loại và Kích thước Slide
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
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

Trong hướng dẫn này, chúng ta đã học cách chuyển đổi slide sang PDF có ghi chú trong Java bằng Aspose.Slides for Java. Chúng tôi đã đề cập đến việc thiết lập dự án, tải bản trình bày, tạo bản trình bày mới, sao chép slide, điều chỉnh kích thước slide, cấu hình tùy chọn PDF và cuối cùng là lưu bản trình bày dưới dạng PDF có ghi chú.

## Câu hỏi thường gặp

### Làm thế nào để cài đặt Aspose.Slides cho Java?

Để cài đặt Aspose.Slides cho Java, hãy làm theo các bước sau:
1. Tải xuống thư viện từ [đây](https://releases.aspose.com/slides/java/).
2. Thêm tệp JAR vào classpath của dự án Java của bạn.

### Tôi có thể tùy chỉnh vị trí ghi chú trong tệp PDF đã tạo không?

Có, bạn có thể tùy chỉnh vị trí ghi chú bằng cách sửa đổi `NotesPositions` enum trong các tùy chọn PDF. Trong hướng dẫn này, chúng tôi đặt nó thành `BottomFull`, nhưng bạn cũng có thể khám phá các lựa chọn khác.

### Có yêu cầu cấp phép nào khi sử dụng Aspose.Slides cho Java không?

Có, Aspose.Slides for Java là một thư viện thương mại và bạn có thể cần phải có giấy phép để sử dụng trong sản xuất. Truy cập trang web Aspose để biết thông tin chi tiết về giấy phép.

### Tôi có thể chuyển đổi nhiều slide cùng lúc không?

Chắc chắn rồi! Bạn có thể lặp qua các slide trong bài thuyết trình của mình và sao chép chúng vào bài thuyết trình mới, cho phép bạn chuyển đổi nhiều slide sang PDF có ghi chú cùng một lúc.

### Tôi có thể tìm thêm tài liệu về Aspose.Slides cho Java ở đâu?

Bạn có thể tìm thấy tài liệu chi tiết về Aspose.Slides for Java trên trang web: [Tài liệu tham khảo API Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}