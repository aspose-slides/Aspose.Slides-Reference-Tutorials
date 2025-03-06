---
title: Aspose.Slides - Thêm video nhúng vào bản trình bày .NET
linktitle: Aspose.Slides - Thêm video nhúng vào bản trình bày .NET
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Nâng cao bản trình bày của bạn bằng các video được nhúng bằng Aspose.Slides for .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 19
url: /vi/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Giới thiệu
Trong thế giới năng động của các bài thuyết trình, việc tích hợp các yếu tố đa phương tiện có thể nâng cao đáng kể mức độ tương tác. Aspose.Slides for .NET cung cấp một giải pháp mạnh mẽ để kết hợp các khung video được nhúng vào các trang trình bày của bạn. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình, chia nhỏ từng bước để đảm bảo trải nghiệm liền mạch.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
-  Aspose.Slides for .NET Library: Tải xuống và cài đặt thư viện từ[trang phát hành](https://releases.aspose.com/slides/net/).
- Nội dung phương tiện: Có tệp video (ví dụ: "Wildlife.mp4") mà bạn muốn nhúng vào bản trình bày của mình.
## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết trong dự án .NET của bạn:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Bước 1: Thiết lập thư mục
Đảm bảo dự án của bạn có các thư mục cần thiết cho các tệp tài liệu và phương tiện:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Tạo thư mục nếu nó chưa có.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Bước 2: Khởi tạo lớp trình bày
Tạo một thể hiện của lớp Trình bày để thể hiện tệp PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Nhận slide đầu tiên
    ISlide sld = pres.Slides[0];
```
## Bước 3: Nhúng video vào bản trình bày
Sử dụng mã sau đây để nhúng video vào bản trình bày:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Bước 4: Thêm khung hình video
Bây giờ, thêm khung hình video vào slide:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Bước 5: Đặt thuộc tính video
Đặt video thành khung video và định cấu hình chế độ và âm lượng phát:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Bước 6: Lưu bài thuyết trình
Cuối cùng, lưu tệp PPTX vào đĩa:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Lặp lại các bước này cho mỗi video bạn muốn nhúng vào bản trình bày của mình.
## Phần kết luận
Chúc mừng! Bạn đã thêm thành công khung video được nhúng vào bản trình bày của mình bằng Aspose.Slides for .NET. Tính năng động này có thể nâng bài thuyết trình của bạn lên một tầm cao mới, thu hút khán giả bằng các yếu tố đa phương tiện được tích hợp liền mạch vào các trang chiếu của bạn.
## Câu hỏi thường gặp
### Tôi có thể nhúng video vào bất kỳ slide nào của bài thuyết trình không?
 Có, bạn có thể chọn bất kỳ slide nào bằng cách sửa đổi chỉ mục trong`pres.Slides[index]`.
### Những định dạng video nào được hỗ trợ?
Aspose.Slides hỗ trợ nhiều định dạng video, bao gồm MP4, AVI và WMV.
### Tôi có thể tùy chỉnh kích thước và vị trí của khung hình video không?
 Tuyệt đối! Điều chỉnh các thông số trong`AddVideoFrame(x, y, width, height, video)` khi cần thiết.
### Có giới hạn về số lượng video tôi có thể nhúng không?
Số lượng video nhúng thường bị giới hạn bởi dung lượng của phần mềm trình chiếu của bạn.
### Tôi có thể tìm kiếm sự hỗ trợ thêm hoặc chia sẻ kinh nghiệm của mình bằng cách nào?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để được cộng đồng hỗ trợ và thảo luận.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
