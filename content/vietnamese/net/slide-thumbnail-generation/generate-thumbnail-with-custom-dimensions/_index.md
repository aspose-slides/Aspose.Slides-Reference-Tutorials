---
title: Tạo hình thu nhỏ trong trang trình bày với kích thước tùy chỉnh
linktitle: Tạo hình thu nhỏ với thứ nguyên tùy chỉnh
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hình ảnh thu nhỏ tùy chỉnh từ bản trình bày PowerPoint bằng Aspose.Slides cho .NET. Nâng cao trải nghiệm người dùng và chức năng.
type: docs
weight: 13
url: /vi/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

Tạo hình ảnh thu nhỏ tùy chỉnh cho bản trình bày PowerPoint của bạn có thể là tài sản có giá trị, cho dù bạn đang xây dựng một ứng dụng tương tác, nâng cao trải nghiệm người dùng hay tối ưu hóa nội dung cho nhiều nền tảng khác nhau. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình ảnh thu nhỏ tùy chỉnh từ bản trình bày PowerPoint bằng thư viện Aspose.Slides cho .NET. Thư viện mạnh mẽ này cho phép bạn thao tác, chuyển đổi và nâng cao các tệp PowerPoint theo chương trình trong các ứng dụng .NET.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào việc tạo hình ảnh thu nhỏ tùy chỉnh, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

### 1. Aspose.Slides cho .NET

 Bạn cần cài đặt thư viện Aspose.Slides for .NET trong dự án của mình. Nếu chưa có, bạn có thể tìm tài liệu cần thiết và liên kết tải xuống[đây](https://reference.aspose.com/slides/net/).

### 2. Bản trình bày PowerPoint

Đảm bảo rằng bạn có bản trình bày PowerPoint mà bạn muốn tạo hình ảnh thu nhỏ tùy chỉnh. Bản trình bày này có thể truy cập được trong thư mục dự án của bạn.

### 3. Môi trường phát triển

Để làm theo hướng dẫn này, bạn phải có kiến thức làm việc về lập trình .NET bằng C# và thiết lập môi trường phát triển, chẳng hạn như Visual Studio.

Bây giờ chúng ta đã đề cập đến các điều kiện tiên quyết, hãy chia nhỏ quy trình tạo hình thu nhỏ tùy chỉnh thành các hướng dẫn từng bước.

## Nhập không gian tên

Trước tiên, bạn cần đưa các không gian tên được yêu cầu vào mã C# của mình. Các không gian tên này cho phép bạn làm việc với Aspose.Slides và thao tác với các bản trình bày PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Bước 1: Tải bài thuyết trình

Để bắt đầu, hãy tải bản trình bày PowerPoint mà bạn muốn tạo hình ảnh thu nhỏ tùy chỉnh. Điều này đạt được bằng cách sử dụng thư viện Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Khởi tạo một lớp Trình bày đại diện cho tệp trình bày
using (Presentation pres = new Presentation(srcFileName))
{
    // Mã tạo hình thu nhỏ của bạn sẽ có ở đây
}
```

## Bước 2: Truy cập vào Slide

Trong bản trình bày đã tải, bạn cần truy cập vào trang chiếu cụ thể mà bạn muốn tạo hình ảnh thu nhỏ tùy chỉnh. Bạn có thể chọn slide theo chỉ mục của nó.

```csharp
// Truy cập slide đầu tiên (bạn có thể thay đổi chỉ mục nếu cần)
ISlide sld = pres.Slides[0];
```

## Bước 3: Xác định kích thước hình thu nhỏ tùy chỉnh

Chỉ định kích thước mong muốn cho hình ảnh thu nhỏ tùy chỉnh của bạn. Bạn có thể xác định chiều rộng và chiều cao bằng pixel theo yêu cầu của ứng dụng.

```csharp
int desiredX = 1200; // Chiều rộng
int desiredY = 800;  // Chiều cao
```

## Bước 4: Tính hệ số tỷ lệ

Để duy trì tỷ lệ khung hình của trang chiếu, hãy tính hệ số tỷ lệ cho kích thước X và Y dựa trên kích thước của trang chiếu và các kích thước bạn mong muốn.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Bước 5: Tạo hình ảnh thu nhỏ

Tạo hình ảnh có kích thước đầy đủ của trang chiếu với các kích thước tùy chỉnh được chỉ định và lưu nó vào đĩa ở định dạng JPEG.

```csharp
// Tạo một hình ảnh toàn diện
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Lưu hình ảnh vào đĩa ở định dạng JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Bây giờ bạn đã làm theo các bước này, bạn đã tạo thành công hình ảnh thu nhỏ tùy chỉnh từ bản trình bày PowerPoint của mình.

## Phần kết luận

Tạo hình ảnh thu nhỏ tùy chỉnh từ bản trình bày PowerPoint bằng Aspose.Slides cho .NET là một kỹ năng có giá trị có thể nâng cao trải nghiệm người dùng và chức năng của ứng dụng của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tạo hình thu nhỏ tùy chỉnh đáp ứng yêu cầu cụ thể của mình.

---

## Câu hỏi thường gặp (Câu hỏi thường gặp)

### Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint theo chương trình trong các ứng dụng .NET.

### Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/slides/net/).

### Aspose.Slides cho .NET có được sử dụng miễn phí không?
 Aspose.Slides for .NET là một thư viện thương mại. Bạn có thể tìm thấy thông tin về giá cả và giấy phép[đây](https://purchase.aspose.com/buy).

### Tôi có cần kỹ năng lập trình nâng cao để sử dụng Aspose.Slides cho .NET không?
Mặc dù một số kiến thức về lập trình .NET là có lợi nhưng Aspose.Slides for .NET cung cấp API thân thiện với người dùng giúp đơn giản hóa công việc với các bản trình bày PowerPoint.

### Có hỗ trợ kỹ thuật cho Aspose.Slides cho .NET không?
 Có, bạn có thể truy cập diễn đàn cộng đồng và hỗ trợ kỹ thuật[đây](https://forum.aspose.com/).