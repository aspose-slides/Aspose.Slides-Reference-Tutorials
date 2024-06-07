---
title: Thêm khung đối tượng OLE vào bản trình bày bằng Aspose.Slides
linktitle: Thêm khung đối tượng OLE vào bản trình bày bằng Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách cải thiện bản trình bày PowerPoint bằng nội dung động! Làm theo hướng dẫn từng bước của chúng tôi bằng cách sử dụng Aspose.Slides cho .NET. Tăng cường sự tham gia ngay bây giờ!
type: docs
weight: 15
url: /vi/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình thêm Khung đối tượng OLE (Liên kết và nhúng đối tượng) vào Trang trình bày bằng Aspose.Slides cho .NET. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PowerPoint theo chương trình. Hãy làm theo hướng dẫn từng bước này để nhúng liền mạch các đối tượng OLE vào các trang trình bày của bạn, cải thiện các tệp PowerPoint của bạn bằng nội dung động và tương tác.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Slides for .NET Library: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải nó xuống từ[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).
2. Thư mục Tài liệu: Tạo một thư mục trên hệ thống của bạn để lưu trữ các tệp cần thiết. Bạn có thể đặt đường dẫn đến thư mục này trong đoạn mã được cung cấp.
## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập bài thuyết trình
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Tạo thư mục nếu nó chưa có.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Khởi tạo lớp Trình bày đại diện cho PPTX
using (Presentation pres = new Presentation())
{
    // Truy cập slide đầu tiên
    ISlide sld = pres.Slides[0];
    
    // Tiếp tục thực hiện các bước tiếp theo...
}
```
## Bước 2: Tải đối tượng OLE (tệp Excel) vào luồng
```csharp
// Tải tệp Excel để phát trực tuyến
MemoryStream mstream = new MemoryStream();
using (FileStream fs = new FileStream(dataDir + "book1.xlsx", FileMode.Open, FileAccess.Read))
{
    byte[] buf = new byte[4096];
    while (true)
    {
        int bytesRead = fs.Read(buf, 0, buf.Length);
        if (bytesRead <= 0)
            break;
        mstream.Write(buf, 0, bytesRead);
    }
}
```
## Bước 3: Tạo đối tượng dữ liệu để nhúng
```csharp
// Tạo đối tượng dữ liệu để nhúng
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.ToArray(), "xlsx");
```
## Bước 4: Thêm hình dạng khung đối tượng OLE
```csharp
//Thêm hình dạng Khung đối tượng OLE
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## Bước 5: Lưu bài thuyết trình
```csharp
// Ghi PPTX vào đĩa
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
Bây giờ bạn đã thêm thành công Khung đối tượng OLE vào slide thuyết trình của mình bằng Aspose.Slides for .NET.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá khả năng tích hợp liền mạch của Khung đối tượng OLE vào các trang chiếu PowerPoint bằng Aspose.Slides cho .NET. Chức năng này nâng cao bản trình bày của bạn bằng cách cho phép nhúng động nhiều đối tượng khác nhau, chẳng hạn như trang tính Excel, mang lại trải nghiệm người dùng tương tác hơn.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể nhúng các đối tượng không phải trang tính Excel bằng Aspose.Slides cho .NET không?
Trả lời: Có, Aspose.Slides hỗ trợ nhúng nhiều đối tượng OLE khác nhau, bao gồm tài liệu Word và tệp PDF.
### Câu hỏi: Làm cách nào để xử lý lỗi trong quá trình nhúng Đối tượng OLE?
Đáp: Đảm bảo xử lý ngoại lệ thích hợp trong mã của bạn để giải quyết mọi vấn đề có thể phát sinh trong quá trình nhúng.
### Hỏi: Aspose.Slides có tương thích với các định dạng tệp PowerPoint mới nhất không?
Trả lời: Có, Aspose.Slides hỗ trợ các định dạng tệp PowerPoint mới nhất, bao gồm PPTX.
### Câu hỏi: Tôi có thể tùy chỉnh giao diện của Khung đối tượng OLE được nhúng không?
Trả lời: Hoàn toàn có thể, bạn có thể điều chỉnh kích thước, vị trí và các thuộc tính khác của Khung đối tượng OLE theo sở thích của mình.
### Hỏi: Tôi có thể tìm kiếm sự hỗ trợ ở đâu nếu gặp khó khăn trong quá trình thực hiện?
Đáp: Hãy ghé thăm[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và hướng dẫn.