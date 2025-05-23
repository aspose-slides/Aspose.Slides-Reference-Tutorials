---
"description": "Tìm hiểu cách nâng cao bài thuyết trình PowerPoint với nội dung động! Làm theo hướng dẫn từng bước của chúng tôi bằng cách sử dụng Aspose.Slides cho .NET. Tăng cường sự tương tác ngay!"
"linktitle": "Thêm Khung Đối tượng OLE vào Bài thuyết trình bằng Aspose.Slides"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Thêm Khung Đối tượng OLE vào Bài thuyết trình bằng Aspose.Slides"
"url": "/vi/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Khung Đối tượng OLE vào Bài thuyết trình bằng Aspose.Slides

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình thêm Khung đối tượng OLE (Liên kết và nhúng đối tượng) vào Slide trình bày bằng Aspose.Slides cho .NET. Aspose.Slides là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp PowerPoint theo chương trình. Làm theo hướng dẫn từng bước này để nhúng liền mạch các đối tượng OLE vào slide trình bày của bạn, nâng cao các tệp PowerPoint của bạn bằng nội dung động và tương tác.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
1. Aspose.Slides cho Thư viện .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải xuống từ [Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).
2. Thư mục tài liệu: Tạo một thư mục trên hệ thống của bạn để lưu trữ các tệp cần thiết. Bạn có thể đặt đường dẫn đến thư mục này trong đoạn mã được cung cấp.
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
// Tạo thư mục nếu thư mục đó chưa có.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Khởi tạo lớp Presentation biểu diễn PPTX
using (Presentation pres = new Presentation())
{
    // Truy cập trang chiếu đầu tiên
    ISlide sld = pres.Slides[0];
    
    // Tiếp tục các bước tiếp theo...
}
```
## Bước 2: Tải một đối tượng OLE (Tệp Excel) vào Stream
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
## Bước 4: Thêm Hình dạng Khung Đối tượng OLE
```csharp
// Thêm hình dạng Khung đối tượng OLE
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## Bước 5: Lưu bài thuyết trình
```csharp
// Ghi PPTX vào đĩa
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
Bây giờ bạn đã thêm thành công Khung đối tượng OLE vào trang trình bày của mình bằng Aspose.Slides cho .NET.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách tích hợp liền mạch OLE Object Frames vào slide PowerPoint bằng Aspose.Slides for .NET. Chức năng này nâng cao bài thuyết trình của bạn bằng cách cho phép nhúng động nhiều đối tượng khác nhau, chẳng hạn như bảng tính Excel, mang lại trải nghiệm người dùng tương tác hơn.
## Câu hỏi thường gặp
### H: Tôi có thể nhúng các đối tượng khác ngoài bảng tính Excel bằng Aspose.Slides cho .NET không?
A: Có, Aspose.Slides hỗ trợ nhúng nhiều đối tượng OLE khác nhau, bao gồm tài liệu Word và tệp PDF.
### H: Tôi phải xử lý lỗi như thế nào trong quá trình nhúng Đối tượng OLE?
A: Đảm bảo xử lý ngoại lệ phù hợp trong mã của bạn để giải quyết mọi vấn đề có thể phát sinh trong quá trình nhúng.
### H: Aspose.Slides có tương thích với các định dạng tệp PowerPoint mới nhất không?
A: Có, Aspose.Slides hỗ trợ các định dạng tệp PowerPoint mới nhất, bao gồm cả PPTX.
### H: Tôi có thể tùy chỉnh giao diện của Khung đối tượng OLE nhúng không?
A: Hoàn toàn có thể, bạn có thể điều chỉnh kích thước, vị trí và các thuộc tính khác của Khung đối tượng OLE theo sở thích của mình.
### H: Tôi có thể tìm kiếm sự hỗ trợ ở đâu nếu gặp khó khăn trong quá trình thực hiện?
A: Ghé thăm [Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và hướng dẫn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}