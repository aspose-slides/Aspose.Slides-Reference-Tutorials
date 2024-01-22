---
title: Cách đặt siêu liên kết Macro Nhấp vào Aspose.Slides cho .NET
linktitle: Quản lý siêu liên kết bằng Macro
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách đặt siêu liên kết macro trong bản trình bày của bạn bằng Aspose.Slides cho .NET. Tăng cường tính tương tác và thu hút khán giả của bạn.
type: docs
weight: 13
url: /vi/net/hyperlink-manipulation/macro-hyperlink/
---

Trong thế giới phát triển phần mềm hiện đại, việc tạo ra các bài thuyết trình năng động và tương tác là một khía cạnh quan trọng. Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn làm việc với các bài thuyết trình một cách liền mạch. Cho dù bạn đang xây dựng một bản trình bày kinh doanh hay một bản trình chiếu giáo dục, khả năng đặt số lần nhấp vào siêu liên kết macro có thể nâng cao đáng kể trải nghiệm người dùng. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập nhấp chuột siêu liên kết macro bằng Aspose.Slides cho .NET. 

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn từng bước, bạn cần phải có một số điều kiện tiên quyết:

1.Visual Studio: Đảm bảo rằng bạn đã cài đặt Visual Studio trên máy tính của mình vì đây sẽ là môi trường phát triển của chúng tôi.

 2.Aspose.Slides cho .NET: Bạn sẽ cần cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).

3. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# theo hướng dẫn này.

## Nhập không gian tên

Trong bước đầu tiên, hãy nhập các không gian tên cần thiết để hoạt động với Aspose.Slides:

### Bước 1: Nhập không gian tên

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Chúng tôi đã nhập khẩu`Aspose.Slides` không gian tên, là không gian tên cốt lõi để làm việc với các bài thuyết trình, và`Aspose.Slides.Export` không gian tên.

## Cài đặt Nhấp chuột siêu liên kết Macro

Bây giờ, hãy chuyển sang phần chính của hướng dẫn này - cài đặt nhấp chuột siêu liên kết macro trong bản trình bày của bạn.

### Bước 2: Khởi tạo bản trình bày

Đầu tiên, chúng ta cần khởi tạo một bài thuyết trình mới.

```csharp
using (Presentation presentation = new Presentation())
{
    // Mã của bạn sẽ ở đây.
}
```

Trong câu lệnh sử dụng này, bạn tạo một đối tượng trình bày mới và thực hiện tất cả các thao tác bên trong nó.

### Bước 3: Thêm hình tự động

Để đặt bấm vào siêu liên kết macro, bạn sẽ cần một đối tượng mà người dùng có thể bấm vào. Trong ví dụ này, chúng tôi sẽ sử dụng Hình tự động làm phần tử có thể nhấp vào.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Ở đây, chúng tôi tạo Hình tự động với loại "BlankButton" ở tọa độ cụ thể (20, 20) và có kích thước 80x30. Bạn có thể tùy chỉnh các giá trị này cho phù hợp với bố cục bản trình bày của mình.

### Bước 4: Đặt Bấm vào Siêu liên kết Macro

Bây giờ đến phần bạn đặt nhấp chuột siêu liên kết macro. Bạn sẽ cần cung cấp tên macro làm tham số.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Trong ví dụ này, chúng tôi đã đặt lần nhấp vào siêu liên kết macro thành "TestMacro". Khi người dùng bấm vào Hình tự động, nó sẽ kích hoạt macro này.

### Bước 5: Truy xuất thông tin

Bạn cũng có thể truy xuất thông tin về siêu liên kết bạn đã đặt.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Những dòng mã này cho phép bạn in URL bên ngoài và loại hành động của siêu liên kết.

Và thế là xong! Bạn đã đặt thành công thao tác bấm siêu liên kết macro trong bản trình bày của mình bằng Aspose.Slides for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt nhấp chuột siêu liên kết macro trong bản trình bày của bạn bằng Aspose.Slides cho .NET. Đây có thể là một tính năng có giá trị để tạo các bài thuyết trình tương tác và năng động thu hút khán giả của bạn. Với Aspose.Slides cho .NET, bạn có thể tùy ý sử dụng một công cụ mạnh mẽ để đưa quá trình phát triển bài thuyết trình của mình lên một tầm cao mới.

 Bây giờ, đã đến lúc bạn thử nghiệm và tạo các bản trình bày hấp dẫn bằng siêu liên kết macro tùy chỉnh. Hãy thoải mái khám phá[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/) để biết thêm thông tin chuyên sâu và khả năng.

## Câu hỏi thường gặp (Câu hỏi thường gặp)

### Tôi có thể sử dụng Aspose.Slides cho .NET với các ngôn ngữ lập trình khác không?
Aspose.Slides được thiết kế chủ yếu cho .NET, nhưng Aspose cung cấp các thư viện tương tự cho các ngôn ngữ lập trình khác, chẳng hạn như Java.

### Aspose.Slides cho .NET có phải là thư viện miễn phí không?
Aspose.Slides for .NET là một thư viện thương mại có sẵn phiên bản dùng thử miễn phí. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/).

### Có bất kỳ hạn chế nào đối với việc sử dụng macro trong bản trình bày được tạo bằng Aspose.Slides cho .NET không?
Aspose.Slides for .NET cho phép bạn làm việc với macro, nhưng bạn nên lưu ý đến các cân nhắc về tính bảo mật và tính tương thích khi sử dụng macro trong bản trình bày.

### Tôi có thể tùy chỉnh hình thức của Hình tự động được sử dụng cho siêu kết nối không?
Có, bạn có thể tùy chỉnh giao diện của Hình tự động bằng cách điều chỉnh các thuộc tính của nó, chẳng hạn như kích thước, màu sắc và phông chữ.

### Tôi có thể nhận trợ giúp hoặc hỗ trợ cho Aspose.Slides cho .NET ở đâu?
 Nếu gặp sự cố hoặc có thắc mắc, bạn có thể tìm kiếm trợ giúp trên diễn đàn hỗ trợ Aspose[đây](https://forum.aspose.com/).