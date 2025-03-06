---
title: Thay đổi dữ liệu đối tượng OLE trong bản trình bày bằng Aspose.Slides
linktitle: Thay đổi dữ liệu đối tượng OLE trong bản trình bày bằng Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Khám phá sức mạnh của Aspose.Slides dành cho .NET trong việc thay đổi dữ liệu đối tượng OLE một cách dễ dàng. Nâng cao bài thuyết trình của bạn với nội dung động.
weight: 25
url: /vi/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thay đổi dữ liệu đối tượng OLE trong bản trình bày bằng Aspose.Slides

## Giới thiệu
Tạo bản trình bày PowerPoint năng động và tương tác là yêu cầu phổ biến trong thế giới kỹ thuật số ngày nay. Một công cụ mạnh mẽ để đạt được điều này là Aspose.Slides for .NET, một thư viện mạnh mẽ cho phép các nhà phát triển thao tác và nâng cao các bản trình bày PowerPoint theo chương trình. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình thay đổi dữ liệu đối tượng OLE (Liên kết và nhúng đối tượng) trong các trang trình bày bằng Aspose.Slides.
## Điều kiện tiên quyết
Trước khi bạn bắt đầu làm việc với Aspose.Slides cho .NET, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
1. Môi trường phát triển: Thiết lập môi trường phát triển có cài đặt .NET.
2.  Thư viện Aspose.Slides: Tải xuống và cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tìm thấy thư viện[đây](https://releases.aspose.com/slides/net/).
3. Hiểu biết cơ bản: Làm quen với các khái niệm cơ bản về lập trình C# và thuyết trình PowerPoint.
## Nhập không gian tên
Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để sử dụng các chức năng của Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách tạo một dự án C# mới và nhập thư viện Aspose.Slides. Đảm bảo dự án của bạn được định cấu hình chính xác và bạn có sẵn các phần phụ thuộc cần thiết.
## Bước 2: Truy cập Bản trình bày và Trang trình bày
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Bước 3: Xác định vị trí đối tượng OLE
Duyệt qua tất cả các hình dạng trong slide để tìm khung đối tượng OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Bước 4: Đọc và sửa đổi dữ liệu sổ làm việc
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Đọc dữ liệu đối tượng trong Workbook
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Sửa đổi dữ liệu sổ làm việc
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Thay đổi dữ liệu đối tượng khung Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Bước 5: Lưu bài thuyết trình
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Phần kết luận
Bằng cách làm theo các bước này, bạn có thể thay đổi liền mạch dữ liệu đối tượng OLE trong các trang trình bày bằng Aspose.Slides cho .NET. Điều này mở ra vô số khả năng để tạo các bản trình bày năng động và tùy chỉnh phù hợp với nhu cầu cụ thể của bạn.
## Các câu hỏi thường gặp
### Aspose.Slides cho .NET là gì?
Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các bản trình bày PowerPoint theo chương trình, cho phép thao tác và nâng cao dễ dàng.
### Tôi có thể tìm tài liệu Aspose.Slides ở đâu?
 Có thể tìm thấy tài liệu về Aspose.Slides cho .NET[đây](https://reference.aspose.com/slides/net/).
### Làm cách nào để tải xuống Aspose.Slides cho .NET?
 Bạn có thể tải xuống thư viện từ trang phát hành[đây](https://releases.aspose.com/slides/net/).
### Có bản dùng thử miễn phí cho Aspose.Slides không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể nhận hỗ trợ cho Aspose.Slides cho .NET ở đâu?
 Để được hỗ trợ và thảo luận, hãy truy cập[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
