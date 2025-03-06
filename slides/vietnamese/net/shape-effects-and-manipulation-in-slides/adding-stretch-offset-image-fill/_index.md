---
title: Thêm Stretch Offset cho Hình ảnh Điền vào Bản trình bày PowerPoint
linktitle: Thêm Stretch Offset cho Hình ảnh Điền vào Trang trình bày
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách cải thiện bản trình bày PowerPoint bằng Aspose.Slides cho .NET. Làm theo hướng dẫn từng bước để thêm phần bù kéo dài cho phần tô hình ảnh.
type: docs
weight: 18
url: /vi/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## Giới thiệu
Trong thế giới năng động của các bài thuyết trình, hình ảnh đóng vai trò then chốt trong việc thu hút sự chú ý của khán giả. Aspose.Slides for .NET trao quyền cho các nhà phát triển nâng cao bản trình bày PowerPoint của họ bằng cách cung cấp một bộ tính năng mạnh mẽ. Một tính năng như vậy là khả năng thêm phần bù giãn cho hình ảnh, cho phép tạo ra các slide sáng tạo và hấp dẫn về mặt hình ảnh.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Slides for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).
2. Môi trường phát triển: Đảm bảo rằng bạn đã thiết lập môi trường phát triển .NET đang hoạt động.
Bây giờ, hãy bắt đầu với hướng dẫn từng bước.
## Nhập không gian tên
Đầu tiên, nhập các không gian tên cần thiết để tận dụng chức năng Aspose.Slides trong ứng dụng .NET của bạn.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập dự án của bạn
Tạo một dự án .NET mới trong môi trường phát triển ưa thích của bạn. Đảm bảo rằng Aspose.Slides cho .NET được tham chiếu chính xác.
## Bước 2: Khởi tạo lớp trình bày
 Khởi tạo`Presentation` class để thể hiện tệp PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Mã của bạn ở đây
}
```
## Bước 3: Lấy slide đầu tiên
Truy xuất slide đầu tiên từ bản trình bày để làm việc.
```csharp
ISlide sld = pres.Slides[0];
```
## Bước 4: Khởi tạo lớp ImageEx
 Tạo một thể hiện của`ImageEx`class để xử lý hình ảnh bạn muốn thêm vào slide.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Bước 5: Thêm khung ảnh
 Sử dụng`AddPictureFrame` cách thêm khung ảnh vào slide. Chỉ định kích thước và vị trí của khung.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Bước 6: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào đĩa.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Đó là nó! Bạn đã thêm thành công phần bù kéo dài cho phần điền hình ảnh vào các slide bằng Aspose.Slides for .NET.
## Phần kết luận
Cải thiện bản trình bày PowerPoint của bạn giờ đây dễ dàng hơn bao giờ hết với Aspose.Slides cho .NET. Bằng cách làm theo hướng dẫn này, bạn đã học được cách kết hợp độ giãn giãn cho hình ảnh, mang lại mức độ sáng tạo mới cho các trang chiếu của bạn.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho .NET trong các ứng dụng web của mình không?
Có, Aspose.Slides for .NET phù hợp cho cả ứng dụng máy tính để bàn và web.
### Có bản dùng thử miễn phí dành cho Aspose.Slides cho .NET không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho .NET?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để hỗ trợ cộng đồng.
### Tôi có thể tìm tài liệu đầy đủ về Aspose.Slides cho .NET ở đâu?
 Tham khảo đến[tài liệu](https://reference.aspose.com/slides/net/) để biết thông tin chi tiết.
### Tôi có thể mua Aspose.Slides cho .NET không?
 Có, bạn có thể mua sản phẩm[đây](https://purchase.aspose.com/buy).