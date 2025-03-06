---
title: Hướng dẫn thêm khung ảnh với Aspose.Slides .NET
linktitle: Thêm khung ảnh có chiều cao tỷ lệ tương đối trong Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm khung ảnh có chiều cao tỷ lệ tương đối trong Aspose.Slides cho .NET. Hãy làm theo hướng dẫn từng bước này để có bản trình bày liền mạch.
weight: 17
url: /vi/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi bản trình bày PowerPoint trong ứng dụng .NET của họ một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình thêm khung ảnh có chiều cao tỷ lệ tương đối bằng Aspose.Slides cho .NET. Hãy làm theo hướng dẫn từng bước này để nâng cao kỹ năng xây dựng bài thuyết trình của bạn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt Visual Studio hoặc bất kỳ môi trường phát triển C# ưa thích nào khác.
- Thư viện Aspose.Slides cho .NET đã được thêm vào dự án của bạn.
## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết vào mã C# của bạn. Bước này đảm bảo rằng bạn có quyền truy cập vào các lớp và chức năng do thư viện Aspose.Slides cung cấp.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn. Đảm bảo thêm thư viện Aspose.Slides for .NET vào dự án của bạn bằng cách tham chiếu nó.
## Bước 2: Tải bản trình bày và hình ảnh
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Tải hình ảnh cần thêm vào bộ sưu tập hình ảnh trình bày
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Trong bước này, chúng ta tạo một đối tượng trình bày mới và tải hình ảnh mà chúng ta muốn thêm vào bản trình bày.
## Bước 3: Thêm khung ảnh vào slide
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Bây giờ, hãy thêm khung ảnh vào slide đầu tiên của bài thuyết trình. Điều chỉnh các thông số như loại hình dạng, vị trí và kích thước theo yêu cầu của bạn.
## Bước 4: Đặt chiều rộng và chiều cao tỷ lệ tương đối
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Đặt chiều cao và chiều rộng tỷ lệ tương đối cho khung ảnh để đạt được hiệu ứng tỷ lệ mong muốn.
## Bước 5: Lưu bài thuyết trình
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Cuối cùng, lưu bản trình bày có khung ảnh đã thêm ở định dạng đầu ra được chỉ định.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm khung ảnh có chiều cao tỷ lệ tương đối bằng Aspose.Slides cho .NET. Thử nghiệm với các hình ảnh, vị trí và tỷ lệ khác nhau để tạo ra các bản trình bày hấp dẫn trực quan phù hợp với nhu cầu của bạn.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Slides cho .NET với các ngôn ngữ lập trình khác không?
Aspose.Slides chủ yếu hỗ trợ các ngôn ngữ .NET, nhưng bạn có thể khám phá các sản phẩm Aspose khác để có khả năng tương thích với các nền tảng khác nhau.
### Tôi có thể tìm tài liệu chi tiết về Aspose.Slides cho .NET ở đâu?
 Tham khảo đến[tài liệu](https://reference.aspose.com/slides/net/) để biết thông tin đầy đủ và ví dụ.
### Có bản dùng thử miễn phí dành cho Aspose.Slides cho .NET không?
 Vâng, bạn có thể nhận được một[dùng thử miễn phí](https://releases.aspose.com/) để đánh giá năng lực của thư viện.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho .NET?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để tìm kiếm sự hỗ trợ từ cộng đồng và các chuyên gia Aspose.
### Tôi có thể mua Aspose.Slides cho .NET ở đâu?
 Bạn có thể mua Aspose.Slides cho .NET từ[trang mua hàng](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
