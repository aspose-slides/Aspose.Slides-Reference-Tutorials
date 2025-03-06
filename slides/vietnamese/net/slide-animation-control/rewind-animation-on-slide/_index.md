---
title: Làm chủ hoạt ảnh tua lại trong bản trình bày với Aspose.Slides
linktitle: Tua lại hoạt ảnh trên slide
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách tua lại hoạt ảnh trên trang chiếu PowerPoint bằng Aspose.Slides cho .NET. Hãy làm theo hướng dẫn từng bước này với các ví dụ về mã nguồn hoàn chỉnh.
weight: 13
url: /vi/net/slide-animation-control/rewind-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong thế giới năng động của các bài thuyết trình, việc kết hợp các hình ảnh động hấp dẫn có thể nâng cao đáng kể mức độ tương tác. Aspose.Slides for .NET cung cấp một bộ công cụ mạnh mẽ để thổi sức sống vào bài thuyết trình của bạn. Một tính năng hấp dẫn là khả năng tua lại hình ảnh động trên slide. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn từng bước trong quy trình, cho phép bạn khai thác toàn bộ tiềm năng của tính năng tua lại hoạt ảnh bằng Aspose.Slides cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
-  Aspose.Slides for .NET: Đảm bảo bạn đã cài đặt thư viện. Nếu không, hãy tải xuống từ[Aspose.Slides cho Tài liệu .NET](https://reference.aspose.com/slides/net/).
- Môi trường phát triển .NET: Đảm bảo bạn đã thiết lập môi trường phát triển .NET đang hoạt động.
- Kiến thức cơ bản về C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C#.
## Nhập không gian tên
Trong mã C#, bạn sẽ cần nhập các vùng tên cần thiết để tận dụng chức năng do Aspose.Slides cung cấp cho .NET. Đây là một đoạn để hướng dẫn bạn:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập dự án của bạn
Tạo một dự án mới trong môi trường phát triển .NET ưa thích của bạn. Thiết lập một thư mục cho tài liệu của bạn nếu nó không tồn tại.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Bước 2: Tải bài thuyết trình
 Khởi tạo`Presentation` class để thể hiện tệp trình bày của bạn.
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // Mã của bạn cho các bước tiếp theo sẽ ở đây
}
```
## Bước 3: Truy cập chuỗi hiệu ứng
Truy xuất chuỗi hiệu ứng cho slide đầu tiên.
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## Bước 4: Sửa đổi thời gian hiệu ứng
Truy cập hiệu ứng đầu tiên của chuỗi chính và sửa đổi thời gian của nó để cho phép tua lại.
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## Bước 5: Lưu bài thuyết trình
Lưu bản trình bày đã sửa đổi.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## Bước 6: Kiểm tra hiệu ứng tua lại trong bản trình bày đích
Tải bản trình bày đã sửa đổi và kiểm tra xem hiệu ứng tua lại có được áp dụng hay không.
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
Lặp lại các bước này cho các slide bổ sung hoặc tùy chỉnh quy trình theo cấu trúc bài thuyết trình của bạn.
## Phần kết luận
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## Câu hỏi thường gặp
### Aspose.Slides cho .NET có tương thích với phiên bản .NET framework mới nhất không?
 Aspose.Slides cho .NET được cập nhật thường xuyên để đảm bảo khả năng tương thích với các phiên bản .NET framework mới nhất. Kiểm tra[tài liệu](https://reference.aspose.com/slides/net/) để biết chi tiết về khả năng tương thích.
### Tôi có thể áp dụng hoạt ảnh tua lại cho các đối tượng cụ thể trong một trang chiếu không?
Có, bạn có thể tùy chỉnh mã để áp dụng hoạt ảnh tua lại có chọn lọc cho các đối tượng hoặc thành phần cụ thể trong trang chiếu.
### Có phiên bản dùng thử cho Aspose.Slides cho .NET không?
 Có, bạn có thể khám phá các tính năng bằng cách nhận bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Slides cho .NET?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để tìm kiếm sự hỗ trợ và tham gia với cộng đồng.
### Tôi có thể mua giấy phép tạm thời cho Aspose.Slides cho .NET không?
 Có, bạn có thể lấy giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
