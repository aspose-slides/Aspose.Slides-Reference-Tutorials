---
"date": "2025-04-16"
"description": "Tìm hiểu cách thiết lập thuộc tính ngôn ngữ cho văn bản trong hình dạng bằng Aspose.Slides cho .NET. Hướng dẫn này bao gồm cách thêm hình dạng tự động, thiết lập ID ngôn ngữ và lưu bản trình bày."
"title": "Cách thiết lập ngôn ngữ trong PowerPoint Shapes bằng Aspose.Slides cho .NET"
"url": "/vi/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách thiết lập ngôn ngữ trong PowerPoint Shapes bằng Aspose.Slides cho .NET

Trong thế giới thuyết trình kỹ thuật số, đảm bảo nội dung của bạn có thể truy cập được và định dạng đúng trên nhiều ngôn ngữ khác nhau có thể là một thách thức. Với Aspose.Slides for .NET, bạn có thể dễ dàng thiết lập các thuộc tính ngôn ngữ cho văn bản trong các hình dạng trong slide PowerPoint. Tính năng này đặc biệt có lợi khi chuẩn bị các tài liệu đa ngôn ngữ hoặc đảm bảo tính nhất quán trong giao tiếp toàn cầu.

**Những gì bạn sẽ học được:**
- Thêm hình dạng tự động và chèn văn bản vào đó.
- Thiết lập ID ngôn ngữ cho phần văn bản bằng Aspose.Slides.
- Lưu bài thuyết trình với cấu hình tùy chỉnh.

Hãy cùng tìm hiểu cách bạn có thể triển khai tính năng này một cách liền mạch.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

- **Thư viện và các phụ thuộc**: Bạn cần cài đặt Aspose.Slides for .NET. Thư viện này rất cần thiết để thao tác các bài thuyết trình PowerPoint bằng C#.
  
- **Thiết lập môi trường**: Cần có môi trường phát triển với .NET Core hoặc .NET Framework.

- **Điều kiện tiên quyết về kiến thức**: Sự quen thuộc với các khái niệm lập trình C# cơ bản và hiểu biết về các nguyên tắc lập trình hướng đối tượng sẽ rất hữu ích.

## Thiết lập Aspose.Slides cho .NET

Để bắt đầu, bạn cần cài đặt thư viện Aspose.Slides. Bạn có thể thực hiện việc này bằng một trong các phương pháp sau:

**.NETCLI**
```shell
dotnet add package Aspose.Slides
```

**Trình quản lý gói**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet**
Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

### Mua lại giấy phép

Bạn có thể bắt đầu dùng thử miễn phí bằng cách tải xuống giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/). Để sử dụng liên tục, hãy cân nhắc mua giấy phép thông qua [liên kết này](https://purchase.aspose.com/buy).

Sau khi thiết lập xong, hãy khởi tạo Aspose.Slides trong dự án của bạn:

```csharp
using Aspose.Slides;
```

## Hướng dẫn thực hiện

Bây giờ chúng ta đã thiết lập xong, hãy triển khai tính năng để thiết lập ngôn ngữ cho văn bản hình dạng.

### Tổng quan về tính năng: Thiết lập Ngôn ngữ văn bản hình dạng

Tính năng này cho phép bạn chỉ định ngôn ngữ của văn bản trong hình dạng PowerPoint. Bằng cách đặt ID ngôn ngữ, bạn đảm bảo rằng kiểm tra chính tả và các tính năng cụ thể khác của ngôn ngữ được áp dụng chính xác.

#### Bước 1: Khởi tạo bài thuyết trình

Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp học.

```csharp
using (Presentation pres = new Presentation())
{
    // Mã của bạn ở đây
}
```

Thao tác này sẽ khởi tạo một đối tượng trình bày PowerPoint mới mà chúng ta sẽ thao tác.

#### Bước 2: Thêm hình dạng tự động và khung văn bản

Thêm hình chữ nhật vào trang chiếu của bạn và chèn văn bản vào đó:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Đây, `AddAutoShape` thêm một hình chữ nhật vào slide đầu tiên. Các tham số xác định vị trí và kích thước của nó.

#### Bước 3: Đặt ID ngôn ngữ

Thiết lập ngôn ngữ cho phần văn bản trong hình dạng:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Thao tác này chỉ định tiếng Anh (Anh) làm ngôn ngữ để kiểm tra chính tả.

#### Bước 4: Lưu bài thuyết trình

Cuối cùng, lưu bài thuyết trình của bạn vào đường dẫn đã chỉ định:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}