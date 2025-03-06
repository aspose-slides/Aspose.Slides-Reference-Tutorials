---
title: Tạo hình thu nhỏ với hệ số tỷ lệ cho hình dạng trong Aspose.Slides
linktitle: Tạo hình thu nhỏ với hệ số tỷ lệ cho hình dạng trong Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tạo hình thu nhỏ PowerPoint với các giới hạn cụ thể bằng Aspose.Slides cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 12
url: /vi/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình thu nhỏ với hệ số tỷ lệ cho hình dạng trong Aspose.Slides

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về cách tạo hình thu nhỏ có giới hạn cho các hình dạng trong Aspose.Slides cho .NET. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với các bản trình bày PowerPoint trong ứng dụng .NET của họ. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tạo hình thu nhỏ với các giới hạn cụ thể cho các hình dạng trong bản trình bày bằng Aspose.Slides.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Slides for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Slides. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).
- Môi trường phát triển: Có môi trường phát triển phù hợp cho .NET, chẳng hạn như Visual Studio, được thiết lập trên máy của bạn.
## Nhập không gian tên
Trong ứng dụng .NET của bạn, hãy bắt đầu bằng cách nhập các không gian tên cần thiết để truy cập các chức năng Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Bước 1: Thiết lập bài thuyết trình
Bắt đầu bằng cách khởi tạo một lớp Trình bày đại diện cho tệp bản trình bày PowerPoint mà bạn muốn làm việc:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Mã của bạn để tạo hình thu nhỏ có ở đây
}
```
## Bước 2: Tạo hình ảnh có tỷ lệ đầy đủ
Trong khối Trình bày, tạo hình ảnh có kích thước đầy đủ của hình mà bạn muốn tạo hình thu nhỏ:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // Mã của bạn để lưu hình ảnh ở đây
}
```
## Bước 3: Lưu hình ảnh vào đĩa
Lưu hình ảnh đã tạo vào đĩa, chỉ định định dạng (trong trường hợp này là PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách tạo hình thu nhỏ có giới hạn cho các hình dạng bằng Aspose.Slides cho .NET. Tính năng này có thể cực kỳ hữu ích khi bạn cần tạo các hình ảnh có kích thước cụ thể trong bản trình bày PowerPoint của mình theo chương trình.
## Các câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Slides với các khung .NET khác không?
Có, Aspose.Slides tương thích với nhiều khung .NET khác nhau, mang lại sự linh hoạt cho việc tích hợp vào các loại ứng dụng khác nhau.
### Câu hỏi 2: Có phiên bản dùng thử cho Aspose.Slides không?
 Có, bạn có thể khám phá chức năng của Aspose.Slides bằng cách tải xuống phiên bản dùng thử[đây](https://releases.aspose.com/).
### Câu hỏi 3: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides?
 Bạn có thể nhận được giấy phép tạm thời cho Aspose.Slides bằng cách truy cập[liên kết này](https://purchase.aspose.com/temporary-license/).
### Câu hỏi 4: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Slides ở đâu?
 Nếu có bất kỳ thắc mắc hoặc trợ giúp nào, vui lòng truy cập diễn đàn hỗ trợ Aspose.Slides[đây](https://forum.aspose.com/c/slides/11).
### Câu hỏi 5: Tôi có thể mua Aspose.Slides cho .NET không?
 Chắc chắn! Để mua Aspose.Slides cho .NET, vui lòng truy cập trang mua hàng[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
