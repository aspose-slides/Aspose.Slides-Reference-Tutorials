---
title: Liên kết Video qua ActiveX Control trong PowerPoint
linktitle: Liên kết video qua ActiveX Control
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách liên kết video với các trang chiếu PowerPoint bằng Aspose.Slides for .NET. Hướng dẫn từng bước này bao gồm mã nguồn và các mẹo để tạo bản trình bày tương tác và hấp dẫn bằng các video được liên kết.
weight: 12
url: /vi/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Liên kết Video qua Điều khiển ActiveX trong Bản trình bày bằng Aspose.Slides for .NET

Trong Aspose.Slides dành cho .NET, bạn có thể liên kết video với trang trình bày theo chương trình bằng cách sử dụng điều khiển ActiveX. Điều này cho phép bạn tạo các bản trình bày tương tác trong đó nội dung video có thể được phát trực tiếp trong trang chiếu. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình liên kết video với trang trình bày bằng Aspose.Slides cho .NET.

## Điều kiện tiên quyết:
- Visual Studio (hoặc bất kỳ môi trường phát triển .NET nào khác)
-  Aspose.Slides cho thư viện .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).

## Bước 1: Tạo một dự án mới
Tạo một dự án mới trong môi trường phát triển .NET ưa thích của bạn (ví dụ: Visual Studio) và thêm các tham chiếu vào thư viện Aspose.Slides cho .NET.

## Bước 2: Nhập các không gian tên cần thiết
Trong dự án của bạn, hãy nhập các không gian tên cần thiết để làm việc với Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Bước 3: Tải bản trình bày
Tải bản trình bày PowerPoint nơi bạn muốn thêm video được liên kết:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Mã của bạn để thêm video được liên kết sẽ có ở đây
}
```

## Bước 4: Thêm điều khiển ActiveX
 Tạo một thể hiện của`IOleObjectFrame` Giao diện thêm điều khiển ActiveX vào slide:

```csharp
ISlide slide = presentation.Slides[0]; // Chọn slide nơi bạn muốn thêm video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Trong đoạn mã trên, chúng tôi đang thêm khung điều khiển ActiveX có kích thước 640x480 vào trang chiếu. Chúng tôi đang chỉ định ProgID cho điều khiển ShockwaveFlash ActiveX, thường được sử dụng để nhúng video.

## Bước 5: Đặt thuộc tính của ActiveX Control
Đặt thuộc tính của điều khiển ActiveX để chỉ định nguồn video được liên kết:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Thay thế bằng đường dẫn file video thực tế
oleObjectFrame.AlternativeText = "Linked Video";
```

 Thay thế`"YourVideoPathHere"` với đường dẫn thực tế đến tệp video của bạn. Các`AlternativeText` thuộc tính cung cấp mô tả cho video được liên kết.

## Bước 6: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Câu hỏi thường gặp:

### Làm cách nào tôi có thể chỉ định kích thước và vị trí của video được liên kết trên trang chiếu?
Bạn có thể điều chỉnh kích thước và vị trí của khung điều khiển ActiveX bằng cách sử dụng các tham số của`AddOleObjectFrame` phương pháp. Bốn đối số bằng số lần lượt biểu thị tọa độ X và Y của góc trên bên trái cũng như chiều rộng và chiều cao của khung.

### Tôi có thể liên kết các video có định dạng khác nhau bằng cách sử dụng phương pháp này không?
Có, bạn có thể liên kết các video có nhiều định dạng khác nhau miễn là có sẵn điều khiển ActiveX thích hợp cho định dạng đó. Ví dụ: điều khiển ShockwaveFlash ActiveX được sử dụng trong hướng dẫn này phù hợp với video Flash (SWF). Đối với các định dạng khác, bạn có thể cần sử dụng các ProgID khác nhau.

### Có giới hạn về kích thước của video được liên kết không?
Kích thước của video được liên kết có thể ảnh hưởng đến kích thước và hiệu suất tổng thể của bản trình bày của bạn. Bạn nên tối ưu hóa video của mình để phát lại trên web trước khi liên kết chúng với bản trình bày.

### Phần kết luận:
Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng liên kết video thông qua điều khiển ActiveX trong bản trình bày bằng Aspose.Slides for .NET. Tính năng này cho phép bạn tạo các bài thuyết trình hấp dẫn và có tính tương tác kết hợp nội dung đa phương tiện một cách liền mạch.

 Để biết thêm chi tiết và các tùy chọn nâng cao, bạn có thể tham khảo[Aspose.Slides cho tài liệu .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
