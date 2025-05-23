---
"description": "Dễ dàng chuyển đổi slide thuyết trình có ghi chú của diễn giả sang PDF bằng Aspose.Slides cho .NET. Bảo toàn nội dung và ngữ cảnh một cách liền mạch."
"linktitle": "Chuyển đổi Slide sang PDF bằng Notes"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Chuyển đổi Slide sang PDF bằng Notes"
"url": "/vi/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi Slide sang PDF bằng Notes


# Viết Hướng dẫn từng bước về cách chuyển đổi Slide sang PDF với Ghi chú bằng Aspose.Slides cho .NET

Bạn đang tìm kiếm một cách đáng tin cậy để chuyển đổi các slide PowerPoint của mình sang định dạng PDF trong khi vẫn giữ nguyên tất cả các ghi chú quan trọng? Không cần tìm đâu xa! Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình sử dụng Aspose.Slides cho .NET để hoàn thành nhiệm vụ này.

## 1. Giới thiệu

Chuyển đổi slide PowerPoint sang PDF có ghi chú có thể là một công cụ hữu ích để chia sẻ bài thuyết trình trong khi vẫn đảm bảo giữ lại ngữ cảnh và bình luận quan trọng. Aspose.Slides for .NET cung cấp giải pháp mạnh mẽ cho nhiệm vụ này.

## 2. Thiết lập môi trường của bạn

Trước khi đi sâu vào quá trình mã hóa, hãy đảm bảo bạn đã thiết lập môi trường cần thiết. Bạn sẽ cần:

- Visual Studio hoặc môi trường phát triển .NET mà bạn ưa thích.
- Đã cài đặt thư viện Aspose.Slides cho .NET.
- Bài thuyết trình PowerPoint có ghi chú mà bạn muốn chuyển đổi.

## 3. Tải bài thuyết trình

Trong mã C# của bạn, bạn cần tải bản trình bày PowerPoint mà bạn muốn chuyển đổi. Sau đây là cách bạn có thể thực hiện:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Sao chép Slide

Để đảm bảo PDF của bạn bao gồm tất cả các slide cần thiết có ghi chú, bạn có thể sao chép chúng từ bản trình bày gốc. Sau đây là cách thực hiện:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Điều chỉnh kích thước Slide

Bạn có thể muốn điều chỉnh kích thước slide cho phù hợp với PDF của mình. Aspose.Slides for .NET cho phép bạn thực hiện điều này một cách dễ dàng:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Cấu hình tùy chọn PDF

Để kiểm soát cách hiển thị ghi chú của bạn trong PDF, bạn có thể cấu hình các tùy chọn PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Lưu dưới dạng PDF với Notes

Cuối cùng, bạn có thể lưu bài thuyết trình của mình dưới dạng PDF kèm theo ghi chú:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Kết luận

Xin chúc mừng! Bạn đã chuyển đổi thành công các slide PowerPoint sang định dạng PDF trong khi vẫn giữ nguyên mọi ghi chú quan trọng. Aspose.Slides for .NET giúp quá trình này trở nên đơn giản và hiệu quả.

## 9. Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh bố cục của ghi chú trong tệp PDF không?

Có, bạn có thể tùy chỉnh bố cục của ghi chú bằng cách sử dụng `INotesCommentsLayoutingOptions` trong tùy chọn PDF.

### Câu hỏi 2: Aspose.Slides cho .NET có hỗ trợ các định dạng đầu ra khác ngoài PDF không?

Có, Aspose.Slides for .NET hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm PPTX, DOCX, v.v.

### Câu hỏi 3: Có phiên bản dùng thử nào của Aspose.Slides dành cho .NET không?

Có, bạn có thể dùng thử miễn phí Aspose.Slides cho .NET tại [https://releases.aspose.com/](https://releases.aspose.com/).

### Câu hỏi 4: Tôi có thể nhận hỗ trợ cho Aspose.Slides cho .NET ở đâu?

Bạn có thể tìm thấy sự hỗ trợ và thảo luận cộng đồng tại [https://forum.aspose.com/](https://forum.aspose.com/).

### Câu hỏi 5: Tôi có thể mua giấy phép tạm thời cho Aspose.Slides dành cho .NET không?

Có, bạn có thể mua giấy phép tạm thời tại [https://purchase.aspose.com/giấy-phép-tạm-thời/](https://purchase.aspose.com/temporary-license/).

Tóm lại, khi sử dụng Aspose.Slides for .NET, bạn có thể dễ dàng chuyển đổi các slide PowerPoint sang định dạng PDF với các ghi chú còn nguyên vẹn. Đây là một công cụ hữu ích cho các chuyên gia cần chia sẻ bài thuyết trình với đồng nghiệp và khách hàng trong khi vẫn đảm bảo không bỏ sót ngữ cảnh quan trọng.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}