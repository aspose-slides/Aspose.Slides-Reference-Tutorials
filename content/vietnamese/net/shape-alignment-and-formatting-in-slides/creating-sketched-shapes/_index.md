---
title: Tạo các hình dạng phác thảo tuyệt đẹp với Aspose.Slides
linktitle: Tạo các hình dạng phác thảo trong các slide thuyết trình với Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách thêm các hình dạng phác thảo sáng tạo vào các trang trình bày của bạn bằng Aspose.Slides for .NET. Tăng cường sự hấp dẫn thị giác một cách dễ dàng!
type: docs
weight: 13
url: /vi/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách tạo các hình dạng phác thảo trong các trang trình bày bằng Aspose.Slides cho .NET. Nếu bạn muốn thêm chút sáng tạo vào bài thuyết trình của mình, các hình dạng phác thảo sẽ mang lại tính thẩm mỹ độc đáo và được vẽ bằng tay. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn thực hiện quy trình, chia nó thành các bước đơn giản để đảm bảo trải nghiệm suôn sẻ.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Slides for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/slides/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển .NET với IDE ưa thích của bạn.
## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết vào dự án .NET của bạn. Bước này đảm bảo rằng bạn có quyền truy cập vào các lớp và chức năng cần thiết để làm việc với Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Bước 1: Thiết lập dự án
Bắt đầu bằng cách tạo một dự án .NET mới hoặc mở một dự án hiện có. Đảm bảo đưa Aspose.Slides vào tài liệu tham khảo dự án của bạn.
## Bước 2: Khởi tạo Aspose.Slides
Khởi tạo Aspose.Slides bằng cách thêm đoạn mã sau. Thao tác này sẽ thiết lập bản trình bày và chỉ định đường dẫn đầu ra cho tệp bản trình bày và hình ảnh thu nhỏ.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Tiếp tục thực hiện các bước tiếp theo...
}
```
## Bước 3: Thêm hình dạng phác thảo
Bây giờ, hãy thêm một hình dạng phác thảo vào slide. Trong ví dụ này, chúng ta sẽ thêm một hình chữ nhật với hiệu ứng phác họa tự do.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Chuyển đổi hình dạng thành bản phác thảo theo phong cách tự do
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Bước 4: Tạo hình thu nhỏ
Tạo hình thu nhỏ của trang chiếu để trực quan hóa hình dạng được phác thảo. Lưu hình thu nhỏ dưới dạng tệp PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Bước 5: Lưu bài thuyết trình
Lưu tệp trình bày với hình dạng phác thảo.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Đó là nó! Bạn đã tạo thành công bản trình bày với các hình dạng phác thảo bằng Aspose.Slides for .NET.
## Phần kết luận
Việc thêm các hình dạng phác thảo vào các trang trình bày của bạn có thể nâng cao sức hấp dẫn trực quan và thu hút khán giả của bạn. Với Aspose.Slides cho .NET, quá trình này trở nên đơn giản, cho phép bạn thỏa sức sáng tạo một cách dễ dàng.
## Câu hỏi thường gặp
### 1. Tôi có thể tùy chỉnh hiệu ứng phác thảo không?
Có, Aspose.Slides for .NET cung cấp nhiều tùy chọn tùy chỉnh khác nhau cho các hiệu ứng phác thảo. Tham khảo đến[tài liệu](https://reference.aspose.com/slides/net/) để biết thông tin chi tiết.
### 2. Có bản dùng thử miễn phí không?
 Chắc chắn! Bạn có thể khám phá bản dùng thử miễn phí Aspose.Slides cho .NET[đây](https://releases.aspose.com/).
### 3. Tôi có thể nhận hỗ trợ ở đâu?
 Đối với bất kỳ sự trợ giúp hoặc thắc mắc nào, hãy truy cập[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Làm cách nào tôi có thể mua Aspose.Slides cho .NET?
 Để mua Aspose.Slides cho .NET, hãy truy cập[trang mua hàng](https://purchase.aspose.com/buy).
### 5. Bạn có cung cấp giấy phép tạm thời không?
 Có, giấy phép tạm thời có sẵn[đây](https://purchase.aspose.com/temporary-license/).