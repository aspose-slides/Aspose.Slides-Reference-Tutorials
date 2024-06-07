---
title: Tạo hình thu nhỏ cho ghi chú con SmartArt trong Aspose.Slides
linktitle: Tạo hình thu nhỏ cho ghi chú con SmartArt trong Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hình thu nhỏ SmartArt Child Note quyến rũ bằng Aspose.Slides cho .NET. Nâng cao bài thuyết trình của bạn bằng hình ảnh động!
type: docs
weight: 15
url: /vi/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---
## Giới thiệu
Trong lĩnh vực thuyết trình động, Aspose.Slides for .NET nổi bật như một công cụ mạnh mẽ, cung cấp cho các nhà phát triển khả năng thao tác và nâng cao các bài thuyết trình PowerPoint theo chương trình. Một tính năng hấp dẫn là khả năng tạo hình thu nhỏ cho SmartArt Child Notes, thêm một lớp hấp dẫn trực quan cho bản trình bày của bạn. Hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình tạo hình thu nhỏ cho SmartArt Child Notes bằng Aspose.Slides for .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Slides for .NET: Đảm bảo bạn đã tích hợp thư viện Aspose.Slides vào dự án .NET của mình. Nếu không, hãy tải xuống từ[trang phát hành](https://releases.aspose.com/slides/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển .NET đang hoạt động và có hiểu biết cơ bản về lập trình C#.
- Bản trình bày mẫu: Tạo hoặc lấy bản trình bày PowerPoint có chứa SmartArt với Ghi chú con để thử nghiệm.
## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết vào dự án C# của bạn. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để làm việc với Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Bước 1: Khởi tạo lớp trình bày
 Bắt đầu bằng việc khởi tạo`Presentation` lớp, đại diện cho tệp PPTX mà bạn sẽ làm việc.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Bước 2: Thêm SmartArt
 Bây giờ, hãy thêm SmartArt vào trang chiếu trong bản trình bày. Trong ví dụ này, chúng tôi đang sử dụng`BasicCycle` cách trình bày.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Bước 3: Lấy tham chiếu nút
Để làm việc với một nút cụ thể trong SmartArt, hãy lấy tham chiếu của nút đó bằng chỉ mục của nút đó.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Bước 4: Nhận hình thu nhỏ
Truy xuất hình ảnh thu nhỏ của Ghi chú con trong nút SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Bước 5: Lưu hình thu nhỏ
Lưu hình ảnh thu nhỏ được tạo vào một thư mục được chỉ định.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Lặp lại các bước này cho từng nút SmartArt trong bản trình bày của bạn, tùy chỉnh bố cục và kiểu nếu cần.
## Phần kết luận
Tóm lại, Aspose.Slides for .NET trao quyền cho các nhà phát triển tạo ra các bài thuyết trình hấp dẫn một cách dễ dàng. Khả năng tạo hình thu nhỏ cho SmartArt Child Notes nâng cao sức hấp dẫn trực quan cho bản trình bày của bạn, mang lại trải nghiệm người dùng năng động và tương tác.
## Các câu hỏi thường gặp
### Hỏi: Tôi có thể tùy chỉnh kích thước và định dạng của hình thu nhỏ được tạo không?
Trả lời: Có, bạn có thể điều chỉnh kích thước và định dạng của hình thu nhỏ bằng cách sửa đổi các tham số tương ứng trong mã.
### Câu hỏi: Aspose.Slides có hỗ trợ các bố cục SmartArt khác không?
Đ: Chắc chắn rồi! Aspose.Slides cung cấp nhiều bố cục SmartArt khác nhau, cho phép bạn chọn bố cục phù hợp nhất với nhu cầu thuyết trình của mình.
### Hỏi: Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?
 Đáp: Có, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/) để kiểm tra và đánh giá.
### Hỏi: Tôi có thể tìm kiếm trợ giúp hoặc kết nối với cộng đồng Aspose.Slides ở đâu?
Đáp: Hãy ghé thăm[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để tương tác với cộng đồng, đặt câu hỏi và tìm giải pháp.
### Câu hỏi: Tôi có thể mua Aspose.Slides cho .NET không?
 Đ: Chắc chắn rồi! Khám phá các lựa chọn mua hàng[đây](https://purchase.aspose.com/buy) để khai thác toàn bộ tiềm năng của Aspose.Slides trong các dự án của bạn.