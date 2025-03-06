---
title: Tạo hình chữ nhật bằng Aspose.Slides cho .NET
linktitle: Tạo hình chữ nhật đơn giản trong slide thuyết trình bằng Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Khám phá thế giới bản trình bày PowerPoint động với Aspose.Slides cho .NET. Tìm hiểu cách tạo hình chữ nhật hấp dẫn trong trang trình bày bằng hướng dẫn từng bước này.
type: docs
weight: 12
url: /vi/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## Giới thiệu
Nếu bạn đang tìm cách nâng cao các ứng dụng .NET của mình bằng các bản trình bày PowerPoint năng động và hấp dẫn về mặt hình ảnh thì Aspose.Slides dành cho .NET là giải pháp phù hợp cho bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo hình chữ nhật đơn giản trong các trang trình bày bằng Aspose.Slides cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy phát triển của mình.
-  Aspose.Slides for .NET: Tải xuống và cài đặt thư viện Aspose.Slides for .NET từ[đây](https://releases.aspose.com/slides/net/).
- Kiến thức C# cơ bản: Cần phải làm quen với ngôn ngữ lập trình C#.
## Nhập không gian tên
Trong dự án C# của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để truy cập các chức năng của Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập dự án
Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio. Đảm bảo rằng Aspose.Slides for .NET được tham chiếu chính xác trong dự án của bạn.
## Bước 2: Khởi tạo đối tượng trình bày
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Mã của bạn cho các bước tiếp theo sẽ xuất hiện ở đây.
}
```
## Bước 3: Lấy slide đầu tiên
```csharp
ISlide sld = pres.Slides[0];
```
## Bước 4: Thêm hình chữ nhật tự động
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Mã này thêm hình chữ nhật tại tọa độ (50, 150) với chiều rộng là 150 và chiều cao là 50.
## Bước 5: Lưu bài thuyết trình
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Bước này lưu bản trình bày có hình chữ nhật đã thêm vào thư mục được chỉ định.
## Phần kết luận
Chúc mừng! Bạn đã tạo thành công một hình chữ nhật đơn giản trong slide thuyết trình bằng Aspose.Slides for .NET. Đây mới chỉ là khởi đầu – Aspose.Slides cung cấp nhiều tính năng để tùy chỉnh và nâng cao hơn nữa bản trình bày của bạn.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho .NET trong cả môi trường Windows và Linux không?
Có, Aspose.Slides for .NET độc lập với nền tảng và có thể được sử dụng trong cả môi trường Windows và Linux.
### Có bản dùng thử miễn phí dành cho Aspose.Slides cho .NET không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho .NET?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để hỗ trợ cộng đồng.
### Tôi có thể mua giấy phép tạm thời cho Aspose.Slides cho .NET không?
 Có, bạn có thể mua giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm tài liệu về Aspose.Slides cho .NET ở đâu?
 Tham khảo tài liệu[đây](https://reference.aspose.com/slides/net/).