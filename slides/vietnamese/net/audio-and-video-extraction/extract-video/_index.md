---
title: Cách trích xuất video từ slide bằng Aspose.Slides cho .NET
linktitle: Trích xuất video từ slide
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách trích xuất video từ các trang chiếu PowerPoint bằng Aspose.Slides cho .NET. Hướng dẫn từng bước này giúp đơn giản hóa quy trình cho bạn.
weight: 14
url: /vi/net/audio-and-video-extraction/extract-video/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn làm việc với các bản trình bày PowerPoint trong môi trường .NET. Một trong những tính năng hữu ích mà nó cung cấp là khả năng trích xuất video từ slide. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách trích xuất video từ trang chiếu PowerPoint bằng Aspose.Slides cho .NET.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Slides cho .NET: Bạn cần cài đặt Aspose.Slides cho .NET. Bạn có thể lấy nó từ[trang mạng](https://purchase.aspose.com/buy).

- Bản trình bày PowerPoint: Chuẩn bị bản trình bày PowerPoint (ví dụ: Video.pptx) có chứa video bạn muốn trích xuất.

## Nhập không gian tên

Bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Slides cho .NET. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Bây giờ, hãy chia nhỏ quá trình trích xuất video từ một slide thành nhiều bước.

## Bước 1: Đặt thư mục tài liệu

```csharp
string dataDir = "Your Document Directory";
```

 Thay thế`"Your Document Directory"` với đường dẫn đến thư mục chứa bản trình bày PowerPoint của bạn.

## Bước 2: Tải bài thuyết trình

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Mã này khởi tạo một đối tượng Trình bày, đại diện cho tệp bản trình bày PowerPoint của bạn.

## Bước 3: Lặp lại các slide và hình dạng

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Ở đây, chúng tôi lặp qua từng trang chiếu trong bản trình bày rồi lặp qua các hình dạng trong trang chiếu đầu tiên (sửa đổi nếu cần).

## Bước 4: Kiểm tra xem Hình dạng có phải là Khung video không

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Bước này kiểm tra xem hình trên slide có phải là khung video hay không.

## Bước 5: Trích xuất dữ liệu video

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Mã này trích xuất thông tin về video, bao gồm loại nội dung và dữ liệu nhị phân.

## Bước 6: Lưu video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Cuối cùng, bước này lưu video vào một tệp mới trong thư mục được chỉ định.

Sau khi hoàn thành các bước này, bạn sẽ trích xuất thành công video từ trang chiếu PowerPoint bằng Aspose.Slides cho .NET.

## Phần kết luận

Aspose.Slides for .NET đơn giản hóa quá trình làm việc với bản trình bày PowerPoint, cho phép bạn thực hiện các tác vụ như trích xuất video từ các trang chiếu một cách dễ dàng. Bằng cách làm theo hướng dẫn từng bước này và sử dụng thư viện Aspose.Slides, bạn có thể nâng cao các ứng dụng .NET của mình bằng các tính năng PowerPoint mạnh mẽ.

## Câu hỏi thường gặp (FAQ)

### Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET là một thư viện cho phép các ứng dụng .NET hoạt động với các bản trình bày PowerPoint, bao gồm tạo, chỉnh sửa và trích xuất nội dung.

### Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/slides/net/).

### Aspose.Slides cho .NET có sẵn để dùng thử miễn phí không?
 Có, bạn có thể tải phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides cho .NET?
 Bạn có thể yêu cầu giấy phép tạm thời từ[liên kết này](https://purchase.aspose.com/temporary-license/).

### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho .NET ở đâu?
 Bạn có thể tìm thấy sự hỗ trợ trên[Diễn đàn Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
