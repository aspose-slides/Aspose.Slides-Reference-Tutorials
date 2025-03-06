---
title: Hướng dẫn nhúng đối tượng OLE với Aspose.Slides cho .NET
linktitle: Thay thế tiêu đề ảnh của khung đối tượng OLE trong slide thuyết trình
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách cải thiện các trang trình bày của bạn bằng các đối tượng OLE động bằng cách sử dụng Aspose.Slides cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 15
url: /vi/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hướng dẫn nhúng đối tượng OLE với Aspose.Slides cho .NET

## Giới thiệu
Việc tạo các slide thuyết trình sinh động và hấp dẫn thường liên quan đến việc kết hợp nhiều yếu tố đa phương tiện khác nhau. Trong hướng dẫn này, chúng ta sẽ khám phá cách thay thế tiêu đề ảnh của Khung đối tượng OLE (Liên kết và nhúng đối tượng) trong các trang trình bày bằng cách sử dụng thư viện Aspose.Slides cho .NET mạnh mẽ. Aspose.Slides đơn giản hóa quá trình xử lý các đối tượng OLE, cung cấp cho các nhà phát triển các công cụ để cải thiện bản trình bày của họ một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn từng bước, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Slides for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Slides for .NET. Bạn có thể tải nó xuống từ[Tài liệu Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Dữ liệu mẫu: Chuẩn bị tệp Excel mẫu (ví dụ: "ExcelObject.xlsx") mà bạn muốn nhúng dưới dạng đối tượng OLE trong bản trình bày. Ngoài ra, hãy có tệp hình ảnh (ví dụ: "Image.png") sẽ dùng làm biểu tượng cho đối tượng OLE.
- Môi trường phát triển: Thiết lập môi trường phát triển với các công cụ cần thiết, chẳng hạn như Visual Studio hoặc bất kỳ IDE ưa thích nào khác để phát triển .NET.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy đảm bảo nhập các không gian tên cần thiết để làm việc với Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Bước 1: Thiết lập thư mục tài liệu
```csharp
string dataDir = "Your Document Directory";
```
Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.
## Bước 2: Xác định đường dẫn tệp biểu tượng và tệp nguồn OLE
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Cập nhật các đường dẫn này bằng đường dẫn thực tế tới tệp hình ảnh và tệp Excel mẫu của bạn.
## Bước 3: Tạo một bản trình bày
```csharp
using (Presentation pres = new Presentation())
{
    // Mã cho các bước tiếp theo sẽ ở đây
}
```
 Khởi tạo một phiên bản mới của`Presentation` lớp học.
## Bước 4: Thêm khung đối tượng OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Thêm khung đối tượng OLE vào slide, chỉ định vị trí và kích thước của nó.
## Bước 5: Thêm đối tượng hình ảnh
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Đọc tệp hình ảnh và thêm nó vào bản trình bày dưới dạng đối tượng hình ảnh.
## Bước 6: Đặt chú thích cho biểu tượng OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Đặt chú thích mong muốn cho biểu tượng OLE.
## Phần kết luận
Việc kết hợp các đối tượng OLE vào các trang trình bày của bạn bằng Aspose.Slides cho .NET là một quá trình đơn giản. Hướng dẫn này đã hướng dẫn bạn qua các bước cần thiết, từ thiết lập thư mục tài liệu đến thêm và tùy chỉnh các đối tượng OLE. Thử nghiệm với các loại tệp và chú thích khác nhau để nâng cao sức hấp dẫn trực quan cho bản trình bày của bạn.
## Câu hỏi thường gặp
### Tôi có thể nhúng các loại tệp khác dưới dạng đối tượng OLE bằng Aspose.Slides không?
Có, Aspose.Slides hỗ trợ nhúng nhiều loại tệp khác nhau, chẳng hạn như bảng tính Excel, tài liệu Word, v.v.
### Biểu tượng đối tượng OLE có thể tùy chỉnh được không?
Tuyệt đối. Bạn có thể thay thế biểu tượng mặc định bằng bất kỳ hình ảnh nào bạn chọn để phù hợp hơn với chủ đề bài thuyết trình của mình.
### Aspose.Slides có cung cấp hỗ trợ cho hoạt ảnh với các đối tượng OLE không?
Kể từ phiên bản mới nhất, Aspose.Slides tập trung vào việc nhúng và hiển thị đối tượng OLE và không xử lý trực tiếp các hoạt ảnh trong các đối tượng OLE.
### Tôi có thể thao tác các đối tượng OLE theo chương trình sau khi thêm chúng vào trang chiếu không?
Chắc chắn. Bạn có toàn quyền kiểm soát theo chương trình đối với các đối tượng OLE, cho phép bạn sửa đổi các thuộc tính và hình thức của chúng nếu cần.
### Có bất kỳ hạn chế nào đối với kích thước của các đối tượng OLE được nhúng không?
Mặc dù có những hạn chế về kích thước nhưng nhìn chung chúng rất hào phóng. Bạn nên thử nghiệm với trường hợp sử dụng cụ thể của mình để đảm bảo hiệu suất tối ưu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
