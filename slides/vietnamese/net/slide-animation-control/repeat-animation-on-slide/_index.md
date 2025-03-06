---
title: Làm chủ hoạt ảnh PowerPoint với Aspose.Slides .NET
linktitle: Lặp lại hoạt ảnh trên slide
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Cải thiện bản trình bày PowerPoint bằng Aspose.Slides cho .NET. Kiểm soát hoạt ảnh một cách dễ dàng, thu hút khán giả và để lại ấn tượng lâu dài.
weight: 12
url: /vi/net/slide-animation-control/repeat-animation-on-slide/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Trong thế giới năng động của các bài thuyết trình, khả năng điều khiển hoạt ảnh đóng vai trò then chốt trong việc thu hút và thu hút sự chú ý của khán giả. Aspose.Slides for .NET trao quyền cho các nhà phát triển chịu trách nhiệm về các loại hoạt ảnh trong các trang trình bày, cho phép tạo ra bản trình bày có tính tương tác và hấp dẫn trực quan hơn. Trong hướng dẫn này, chúng ta sẽ khám phá cách kiểm soát các loại hoạt ảnh trên trang chiếu bằng Aspose.Slides cho .NET, theo từng bước.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Slides for .NET Library: Tải xuống và cài đặt thư viện từ[đây](https://releases.aspose.com/slides/net/).
2. Môi trường phát triển .NET: Thiết lập môi trường phát triển .NET trên máy của bạn.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để tận dụng các chức năng do Aspose.Slides cung cấp:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập dự án
Tạo một thư mục mới cho dự án của bạn và khởi tạo lớp Trình bày để thể hiện tệp trình bày.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Mã của bạn ở đây
}
```
## Bước 2: Truy cập chuỗi hiệu ứng
Truy xuất chuỗi hiệu ứng cho slide đầu tiên bằng thuộc tính MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Bước 3: Truy cập hiệu ứng đầu tiên
Có được hiệu ứng đầu tiên của chuỗi chính để thao tác các thuộc tính của nó.
```csharp
IEffect effect = effectsSequence[0];
```
## Bước 4: Sửa đổi cài đặt lặp lại
Thay đổi thuộc tính Thời gian/Lặp lại của hiệu ứng thành "Cho đến khi kết thúc trang chiếu".
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Bước 5: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi để trực quan hóa các thay đổi.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Lặp lại các bước này để có thêm hiệu ứng hoặc tùy chỉnh chúng theo yêu cầu trình bày của bạn.
## Phần kết luận
Việc kết hợp các hoạt ảnh động trong bản trình bày PowerPoint của bạn chưa bao giờ dễ dàng hơn thế với Aspose.Slides cho .NET. Hướng dẫn từng bước này trang bị cho bạn kiến thức để kiểm soát các loại hoạt ảnh, đảm bảo các trang trình bày của bạn để lại ấn tượng lâu dài cho người xem.
## Các câu hỏi thường gặp
### Tôi có thể áp dụng những hoạt ảnh này cho các đối tượng cụ thể trong một trang chiếu không?
Có, bạn có thể nhắm mục tiêu các đối tượng cụ thể bằng cách truy cập các hiệu ứng riêng lẻ của chúng trong chuỗi.
### Aspose.Slides có tương thích với các phiên bản PowerPoint mới nhất không?
Aspose.Slides cung cấp hỗ trợ cho nhiều phiên bản PowerPoint, đảm bảo khả năng tương thích với cả phiên bản cũ và mới.
### Tôi có thể tìm thêm ví dụ và tài nguyên ở đâu?
 Khám phá cái[tài liệu](https://reference.aspose.com/slides/net/) để có ví dụ đầy đủ và giải thích chi tiết.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides?
 Thăm nom[đây](https://purchase.aspose.com/temporary-license/) để biết thông tin về việc xin giấy phép tạm thời.
### Cần trợ giúp hoặc có thêm câu hỏi?
 Tương tác với cộng đồng Aspose.Slides trên[diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
