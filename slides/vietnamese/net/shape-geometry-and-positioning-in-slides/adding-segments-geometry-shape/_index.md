---
title: Làm chủ hình ảnh - Thêm phân đoạn bằng Aspose.Slides trong .NET
linktitle: Thêm các phân đoạn vào hình dạng hình học trong bản trình bày với Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách nâng cao ứng dụng .NET của bạn bằng Aspose.Slides. Hướng dẫn này hướng dẫn bạn cách thêm các phân đoạn vào các hình dạng hình học để có được bài thuyết trình hấp dẫn.
weight: 13
url: /vi/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Trong thế giới phát triển .NET, việc tạo ra các bản trình bày hấp dẫn về mặt hình ảnh là một yêu cầu chung. Aspose.Slides for .NET là một thư viện mạnh mẽ tạo điều kiện tích hợp liền mạch các khả năng tạo bản trình bày mạnh mẽ vào các ứng dụng .NET của bạn. Hướng dẫn này tập trung vào một khía cạnh cụ thể của thiết kế bản trình bày – thêm các phân đoạn vào các hình dạng hình học.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Visual Studio được cài đặt trên máy của bạn.
- Thư viện Aspose.Slides cho .NET được tải xuống và tham chiếu trong dự án của bạn.
## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo nhập các vùng tên cần thiết để truy cập các chức năng Aspose.Slides. Thêm các dòng sau vào mã của bạn:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Bây giờ, hãy chia ví dụ thành nhiều bước.
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio. Đảm bảo rằng bạn có thư viện Aspose.Slides được tham chiếu trong dự án của bạn.
## Bước 2: Tạo bản trình bày
Khởi tạo một đối tượng trình bày mới bằng thư viện Aspose.Slides. Điều này sẽ phục vụ như canvas cho hình dạng hình học của bạn.
```csharp
using (Presentation pres = new Presentation())
{
    // Mã của bạn để tạo bản trình bày ở đây
}
```
## Bước 3: Thêm hình dạng hình học
Tạo một hình dạng hình học trong bản trình bày. Ví dụ: hãy thêm một hình chữ nhật vào slide đầu tiên.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Bước 4: Nhận đường dẫn hình học
Truy xuất đường dẫn hình học của hình đã tạo để thao tác các phân đoạn của nó.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Bước 5: Thêm phân đoạn
Thêm các đoạn (đường) vào đường dẫn hình học. Trong ví dụ này, hai dòng được thêm vào đường dẫn.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Bước 6: Chỉ định đường dẫn hình học đã chỉnh sửa
Gán đường dẫn hình học đã sửa đổi trở lại hình dạng để áp dụng các thay đổi.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Bước 7: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi vào vị trí mong muốn.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Với các bước này, bạn đã thêm thành công các phân đoạn vào hình dạng hình học trong bản trình bày bằng Aspose.Slides for .NET.
## Phần kết luận
Aspose.Slides for .NET trao quyền cho các nhà phát triển nâng cao ứng dụng của họ bằng khả năng tạo bản trình bày nâng cao. Việc thêm các phân đoạn vào hình dạng hình học cung cấp phương tiện để tùy chỉnh các yếu tố trực quan trong bản trình bày của bạn.
### Các câu hỏi thường gặp
### Tôi có thể thêm các loại hình dạng khác nhau bằng Aspose.Slides không?
Có, Aspose.Slides hỗ trợ nhiều loại hình dạng khác nhau, bao gồm hình chữ nhật, hình tròn và hình dạng hình học tùy chỉnh.
### Có cần giấy phép để sử dụng Aspose.Slides trong dự án của tôi không?
Có, cần có giấy phép hợp lệ. Bạn có thể lấy giấy phép tạm thời cho mục đích thử nghiệm hoặc mua giấy phép đầy đủ để sản xuất.
### Làm cách nào tôi có thể nhận được hỗ trợ cho các truy vấn liên quan đến Aspose.Slides?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và thảo luận.
### Có hướng dẫn nào khác dành cho Aspose.Slides không?
 Khám phá cái[tài liệu](https://reference.aspose.com/slides/net/) để có hướng dẫn và ví dụ toàn diện.
### Tôi có thể dùng thử Aspose.Slides miễn phí trước khi mua không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
