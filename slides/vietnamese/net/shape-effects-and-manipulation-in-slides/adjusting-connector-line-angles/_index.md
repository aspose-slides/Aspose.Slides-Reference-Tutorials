---
title: Điều chỉnh góc đường kết nối trong PowerPoint bằng Aspose.Slides
linktitle: Điều chỉnh các góc của đường kết nối trong các slide thuyết trình bằng Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách điều chỉnh góc đường kết nối trong trang chiếu PowerPoint bằng Aspose.Slides for .NET. Nâng cao bài thuyết trình của bạn một cách chính xác và dễ dàng.
weight: 28
url: /vi/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Việc tạo các slide thuyết trình hấp dẫn về mặt trực quan thường liên quan đến việc điều chỉnh chính xác các đường kết nối. Trong hướng dẫn này, chúng ta sẽ khám phá cách điều chỉnh góc đường kết nối trong các trang trình bày bằng Aspose.Slides cho .NET. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PowerPoint theo chương trình, cung cấp các khả năng mở rộng để tạo, sửa đổi và thao tác với bản trình bày.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có những điều sau:
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác được cài đặt.
-  Aspose.Slides cho thư viện .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/slides/net/).
- Tệp bản trình bày PowerPoint có các đường nối mà bạn muốn điều chỉnh.
## Nhập không gian tên
Để bắt đầu, hãy đảm bảo bao gồm các không gian tên cần thiết trong mã C# của bạn:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Bước 1: Thiết lập dự án của bạn
Tạo một dự án C# mới trong Visual Studio và cài đặt gói NuGet Aspose.Slides. Thiết lập cấu trúc dự án có tham chiếu đến thư viện Aspose.Slides.
## Bước 2: Tải bài thuyết trình
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 Tải tập tin thuyết trình PowerPoint của bạn vào`Presentation`sự vật. Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế tới tệp của bạn.
## Bước 3: Truy cập Slide và Shapes
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Truy cập slide đầu tiên trong bản trình bày và khởi tạo một biến để thể hiện các hình dạng trên slide.
## Bước 4: Lặp lại các hình dạng
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Mã xử lý các đường kết nối
}
```
Lặp lại từng hình trên trang chiếu để xác định và xử lý các đường kết nối.
## Bước 5: Điều chỉnh góc đường kết nối
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Mã để xử lý AutoShapes
}
else if (shape is Connector)
{
    // Mã để xử lý Trình kết nối
}
Console.WriteLine(dir);
```
 Xác định xem hình dạng là Hình tự động hay Đường kết nối và điều chỉnh các góc của đường kết nối bằng cách sử dụng công cụ được cung cấp`getDirection` phương pháp.
##  Bước 6: Xác định`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Code tính hướng
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 Thực hiện các`getDirection` phương pháp tính toán góc của đường kết nối dựa trên kích thước và hướng của nó.
## Phần kết luận
Với các bước này, bạn có thể điều chỉnh các góc đường kết nối trong bản trình bày PowerPoint của mình theo chương trình bằng cách sử dụng Aspose.Slides for .NET. Hướng dẫn này cung cấp nền tảng để nâng cao sức hấp dẫn trực quan cho các trang trình bày của bạn.
## Câu hỏi thường gặp
### Aspose.Slides có phù hợp với cả ứng dụng Windows và web không?
Có, Aspose.Slides có thể được sử dụng trong cả Windows và ứng dụng web.
### Tôi có thể tải xuống bản dùng thử miễn phí Aspose.Slides trước khi mua không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu toàn diện về Aspose.Slides cho .NET ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/slides/net/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Slides?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Có diễn đàn hỗ trợ cho Aspose.Slides không?
 Có, bạn có thể truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
