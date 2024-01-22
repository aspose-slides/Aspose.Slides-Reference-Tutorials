---
title: Tạo hình thu nhỏ từ slide trong ghi chú
linktitle: Tạo hình thu nhỏ từ slide trong ghi chú
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hình thu nhỏ từ các trang chiếu trong phần ghi chú của bản trình bày của bạn bằng Aspose.Slides for .NET. Nâng cao nội dung hình ảnh của bạn!
type: docs
weight: 12
url: /vi/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

Trong thế giới thuyết trình hiện đại, nội dung trực quan là vua. Tạo các slide hấp dẫn là điều cần thiết để giao tiếp hiệu quả. Một cách để cải thiện bản trình bày của bạn là tạo hình thu nhỏ từ các trang chiếu, đặc biệt khi bạn muốn nhấn mạnh các chi tiết cụ thể hoặc chia sẻ cái nhìn tổng quan. Aspose.Slides for .NET là một công cụ mạnh mẽ có thể giúp bạn đạt được điều này một cách liền mạch. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình thu nhỏ từ các trang chiếu trong phần ghi chú của bản trình bày bằng Aspose.Slides cho .NET.

## Điều kiện tiên quyết

Trước khi đi sâu vào chi tiết, bạn nên có sẵn các điều kiện tiên quyết sau:

### 1. Aspose.Slides cho .NET

 Đảm bảo bạn đã cài đặt và thiết lập Aspose.Slides for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).

### 2. Môi trường .NET

Bạn nên có sẵn môi trường phát triển .NET trên hệ thống của mình.

### 3. Tệp trình bày

 Có một tập tin trình bày (ví dụ,`ThumbnailFromSlideInNotes.pptx`) mà bạn muốn tạo hình thu nhỏ từ đó.

Bây giờ, hãy chia quy trình thành các bước:

## Bước 1: Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để hoạt động với Aspose.Slides. Thêm mã sau vào đầu tập lệnh C# của bạn:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Bước 2: Tải bài thuyết trình

 Tiếp theo, bạn sẽ cần tải tệp trình bày chứa các trang trình bày có ghi chú. Sử dụng đoạn mã sau để khởi tạo một`Presentation` lớp học:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Mã của bạn ở đây
}
```

## Bước 3: Truy cập vào Slide

Bạn có thể chọn slide nào trong bản trình bày mà bạn muốn tạo hình thu nhỏ. Trong ví dụ này, chúng ta sẽ truy cập vào slide đầu tiên:

```csharp
ISlide sld = pres.Slides[0];
```

## Bước 4: Xác định kích thước mong muốn

Chỉ định kích thước (chiều rộng và chiều cao) cho hình thu nhỏ bạn muốn tạo. Ví dụ:

```csharp
int desiredX = 1200; // Chiều rộng
int desiredY = 800;  // Chiều cao
```

## Bước 5: Tính hệ số tỷ lệ

Để đảm bảo hình thu nhỏ vừa với kích thước mong muốn, hãy tính hệ số tỷ lệ như sau:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Bước 6: Tạo hình thu nhỏ

Bây giờ, hãy tạo hình thu nhỏ của hình ảnh có tỷ lệ đầy đủ bằng cách sử dụng các hệ số tỷ lệ được tính toán:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Bước 7: Lưu hình thu nhỏ

Cuối cùng, lưu hình thu nhỏ được tạo dưới dạng ảnh JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Đó là nó! Bạn đã tạo thành công hình thu nhỏ từ một trang chiếu trong phần ghi chú của bản trình bày bằng Aspose.Slides for .NET.

## Phần kết luận

Việc kết hợp hình thu nhỏ vào bản trình bày của bạn có thể cải thiện đáng kể tính hấp dẫn và hiệu quả về mặt hình ảnh của chúng. Aspose.Slides for .NET làm cho quá trình này trở nên đơn giản, cho phép bạn tạo hình thu nhỏ tùy chỉnh từ các trang chiếu của mình một cách dễ dàng.

## Câu hỏi thường gặp (Câu hỏi thường gặp)

### Tôi có thể lưu hình thu nhỏ được tạo ở định dạng nào?
Bạn có thể lưu hình thu nhỏ ở nhiều định dạng khác nhau, bao gồm JPEG, PNG, v.v., tùy thuộc vào yêu cầu của bạn.

### Tôi có thể tạo hình thu nhỏ cho nhiều trang trình bày cùng một lúc không?
Có, bạn có thể lặp qua các trang chiếu trong bản trình bày của mình và tạo hình thu nhỏ cho từng trang.

### Aspose.Slides cho .NET có tương thích với các khung .NET khác nhau không?
Có, Aspose.Slides cho .NET tương thích với nhiều khung .NET khác nhau, bao gồm .NET Core và .NET Framework.

### Tôi có thể tùy chỉnh giao diện của hình thu nhỏ được tạo không?
Tuyệt đối! Aspose.Slides for .NET cung cấp các tùy chọn để tùy chỉnh giao diện của hình thu nhỏ, chẳng hạn như kích thước, chất lượng, v.v.

### Tôi có thể nhận hỗ trợ hoặc trợ giúp thêm với Aspose.Slides cho .NET ở đâu?
 Bạn có thể tìm trợ giúp và tham gia với cộng đồng Aspose tại[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/).