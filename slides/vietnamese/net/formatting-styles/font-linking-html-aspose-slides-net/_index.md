---
"date": "2025-04-15"
"description": "Tìm hiểu cách đảm bảo hiển thị phông chữ nhất quán khi chuyển đổi bản trình bày sang HTML bằng Aspose.Slides cho .NET bằng cách nhúng phông chữ trực tiếp."
"title": "Cách liên kết phông chữ trong HTML bằng Aspose.Slides cho .NET&#58; Hướng dẫn từng bước"
"url": "/vi/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách liên kết phông chữ trong HTML bằng Aspose.Slides cho .NET

## Giới thiệu

Việc chuyển đổi bài thuyết trình sang HTML trong khi vẫn duy trì phông chữ hiển thị nhất quán trên nhiều nền tảng có thể là một thách thức. **Aspose.Slides cho .NET** cung cấp giải pháp liền mạch bằng cách cho phép bạn liên kết tất cả phông chữ được sử dụng trong bản trình bày trực tiếp trong đầu ra HTML thông qua các tệp phông chữ được nhúng.

Trong hướng dẫn này, chúng ta sẽ khám phá cách triển khai liên kết phông chữ bằng Aspose.Slides cho .NET và đảm bảo tính nhất quán của thiết kế trên các nền tảng khác nhau. 

**Những gì bạn sẽ học được:**
- Thiết lập môi trường của bạn với Aspose.Slides cho .NET
- Liên kết phông chữ trong chuyển đổi HTML
- Viết bộ điều khiển tùy chỉnh để nhúng phông chữ
- Ứng dụng thực tế và cân nhắc hiệu suất

Hãy cùng tìm hiểu các bước cần thiết để đạt được điều này.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

### Thư viện và phụ thuộc bắt buộc
- **Aspose.Slides cho .NET** thư viện: Thành phần cốt lõi cho việc triển khai của chúng tôi.

### Yêu cầu thiết lập môi trường
- Môi trường phát triển có cài đặt .NET Framework hoặc .NET Core.

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình C#.
- Sự quen thuộc với HTML và CSS, đặc biệt là `@font-face` luật lệ.

## Thiết lập Aspose.Slides cho .NET

Để sử dụng Aspose.Slides trong dự án .NET của bạn, bạn cần cài đặt thư viện. Sau đây là một số phương pháp:

### Sử dụng .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Sử dụng Package Manager Console
```powershell
Install-Package Aspose.Slides
```

### Thông qua Giao diện người dùng Trình quản lý gói NuGet
- Mở dự án của bạn trong Visual Studio.
- Điều hướng đến "Trình quản lý gói NuGet".
- Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Các bước xin cấp giấy phép
Bạn có thể nhận được giấy phép dùng thử miễn phí để kiểm tra tất cả các tính năng mà không có giới hạn bằng cách làm theo các bước sau:
1. **Dùng thử miễn phí**: Tải xuống giấy phép tạm thời [đây](https://releases.aspose.com/slides/net/).
2. **Giấy phép tạm thời**: Nộp đơn xin gia hạn quyền truy cập [đây](https://purchase.aspose.com/temporary-license/).
3. **Mua**: Để có đầy đủ chức năng, hãy mua giấy phép [đây](https://purchase.aspose.com/buy).

### Khởi tạo và thiết lập cơ bản
```csharp
// Tạo một thể hiện của lớp License
easpose.slides.License license = new aspose.slides.License();

// Áp dụng giấy phép từ đường dẫn tệp
license.SetLicense("Aspose.Slides.lic");
```

## Hướng dẫn thực hiện

Bây giờ, chúng ta hãy triển khai liên kết phông chữ trong chuyển đổi HTML bằng cách sử dụng **Aspose.Slides cho .NET**.

### Tổng quan về tính năng: Liên kết phông chữ trong chuyển đổi HTML
Tính năng này đảm bảo rằng tất cả các phông chữ được sử dụng trong bản trình bày được liên kết trực tiếp trong tệp HTML kết quả bằng cách nhúng các tệp phông chữ. Phương pháp này cung cấp giải pháp mạnh mẽ để duy trì tính nhất quán của thiết kế trên các trình duyệt và nền tảng khác nhau.

#### Bước 1: Tạo Bộ điều khiển tùy chỉnh
Tạo một lớp điều khiển tùy chỉnh `LinkAllFontsHtmlController` mà thừa hưởng từ `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Thiết lập thư mục nơi các tập tin phông chữ sẽ được lưu trữ
    }
}
```
#### Bước 2: Triển khai phương pháp viết phông chữ
Các `WriteFont` phương pháp ghi dữ liệu phông chữ vào một tệp và tạo mã HTML tương ứng để nhúng:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Xác định tên phông chữ cần sử dụng, ưu tiên phông chữ thay thế nếu có.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Tạo đường dẫn tệp cho tệp phông chữ .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Ghi dữ liệu phông chữ vào đường dẫn tệp đã chỉ định.
    File.WriteAllBytes(path, fontData);

    // Tạo khối kiểu HTML nhúng phông chữ bằng quy tắc @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}