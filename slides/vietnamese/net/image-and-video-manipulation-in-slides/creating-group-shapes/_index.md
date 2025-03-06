---
title: Aspose.Slides - Tạo hình dạng nhóm trong .NET
linktitle: Tạo hình dạng nhóm trong các slide thuyết trình với Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo các hình dạng nhóm trong PowerPoint bằng Aspose.Slides for .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có bản trình bày hấp dẫn về mặt hình ảnh.
weight: 11
url: /vi/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Giới thiệu
Nếu bạn đang tìm cách nâng cao sức hấp dẫn trực quan của các trang trình bày và sắp xếp nội dung hiệu quả hơn thì việc kết hợp các hình dạng nhóm là một giải pháp mạnh mẽ. Aspose.Slides for .NET cung cấp một cách liền mạch để tạo và thao tác các hình dạng nhóm trong bản trình bày PowerPoint của bạn. Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình tạo các hình dạng nhóm bằng Aspose.Slides, chia nhỏ thành các bước dễ thực hiện.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
-  Aspose.Slides for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Slides. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/slides/net/).
- Môi trường phát triển: Thiết lập môi trường làm việc với IDE tương thích .NET, chẳng hạn như Visual Studio.
- Kiến thức cơ bản về C#: Làm quen với những kiến thức cơ bản về ngôn ngữ lập trình C#.
## Nhập không gian tên
Trong dự án C# của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Bước 1: Khởi tạo lớp trình bày

 Tạo một thể hiện của`Presentation` class và chỉ định thư mục nơi tài liệu của bạn được lưu trữ:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Tiếp tục với các bước sau trong khối sử dụng này
}
```

## Bước 2: Truy cập Slide đầu tiên

Truy xuất slide đầu tiên từ bản trình bày:

```csharp
ISlide sld = pres.Slides[0];
```

## Bước 3: Truy cập Bộ sưu tập Hình dạng

Truy cập bộ sưu tập các hình dạng trên slide:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Bước 4: Thêm hình dạng nhóm

Thêm hình dạng nhóm vào slide:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Bước 5: Thêm hình dạng bên trong hình dạng nhóm

Điền vào hình dạng nhóm với các hình dạng riêng lẻ:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Bước 6: Thêm khung hình dạng nhóm

Xác định khung cho toàn bộ hình dạng nhóm:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Bước 7: Lưu bài thuyết trình

Lưu bản trình bày đã sửa đổi vào thư mục được chỉ định của bạn:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Lặp lại các bước này trong ứng dụng C# của bạn để tạo thành công các hình dạng nhóm trong các trang trình bày của bạn bằng Aspose.Slides.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quá trình tạo các hình dạng nhóm bằng Aspose.Slides cho .NET. Bằng cách làm theo các bước này, bạn có thể nâng cao sự hấp dẫn trực quan và tổ chức các bản trình bày PowerPoint của mình.
## Các câu hỏi thường gặp
### Aspose.Slides có tương thích với phiên bản .NET mới nhất không?
 Có, Aspose.Slides được cập nhật thường xuyên để hỗ trợ các phiên bản .NET mới nhất. Kiểm tra[tài liệu](https://reference.aspose.com/slides/net/) để biết chi tiết về khả năng tương thích.
### Tôi có thể dùng thử Aspose.Slides trước khi mua không?
 Tuyệt đối! Bạn có thể tải xuống phiên bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ cho các truy vấn liên quan đến Aspose.Slides ở đâu?
Truy cập Aspose.Slides[diễn đàn](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và thảo luận.
### Làm cách nào để có được giấy phép tạm thời cho Aspose.Slides?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể mua giấy phép đầy đủ cho Aspose.Slides ở đâu?
 Bạn có thể mua giấy phép từ[trang mua hàng](https://purchase.aspose.com/buy).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
