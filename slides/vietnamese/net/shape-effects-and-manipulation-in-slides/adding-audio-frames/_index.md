---
title: Thêm khung âm thanh vào slide thuyết trình bằng Aspose.Slides
linktitle: Thêm khung âm thanh vào slide thuyết trình bằng Aspose.Slides
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Cải thiện bản trình bày với Aspose.Slides cho .NET! Tìm hiểu cách thêm khung âm thanh một cách liền mạch, thu hút khán giả của bạn hơn bao giờ hết.
weight: 14
url: /vi/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm khung âm thanh vào slide thuyết trình bằng Aspose.Slides

## Giới thiệu
Trong thế giới năng động của các bài thuyết trình, việc kết hợp các yếu tố âm thanh có thể nâng cao đáng kể trải nghiệm tổng thể cho khán giả của bạn. Aspose.Slides for .NET trao quyền cho các nhà phát triển tích hợp liền mạch các khung âm thanh vào các trang trình bày, thêm một lớp tương tác và tương tác mới. Hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình thêm khung âm thanh vào các trang trình bày bằng Aspose.Slides cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Slides for .NET Library: Tải xuống và cài đặt thư viện Aspose.Slides for .NET từ[Liên kết tải xuống](https://releases.aspose.com/slides/net/).
2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển hoạt động cho .NET, chẳng hạn như Visual Studio.
3. Thư mục Tài liệu: Tạo một thư mục nơi bạn sẽ lưu trữ tài liệu của mình và ghi lại đường dẫn.
## Nhập không gian tên
Trong ứng dụng .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để truy cập chức năng Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Bước 1: Tạo bản trình bày và slide
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // Mã của bạn để tạo slide ở đây
}
```
## Bước 2: Tải tệp âm thanh
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## Bước 3: Thêm khung âm thanh
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Bước 4: Định cấu hình thuộc tính âm thanh
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## Bước 5: Lưu bài thuyết trình
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
Bằng cách làm theo các bước này, bạn đã tích hợp thành công các khung âm thanh vào bản trình bày của mình bằng Aspose.Slides for .NET.
## Phần kết luận
Việc kết hợp các yếu tố âm thanh vào bản trình bày của bạn sẽ nâng cao trải nghiệm tổng thể của người xem, giúp nội dung của bạn trở nên năng động và hấp dẫn hơn. Aspose.Slides for .NET đơn giản hóa quy trình này, cho phép các nhà phát triển tích hợp liền mạch các khung âm thanh chỉ bằng một vài dòng mã.
## Câu hỏi thường gặp
### Aspose.Slides cho .NET có tương thích với các định dạng âm thanh khác nhau không?
Aspose.Slides for .NET hỗ trợ nhiều định dạng âm thanh khác nhau, bao gồm WAV, MP3, v.v. Kiểm tra tài liệu để có danh sách đầy đủ.
### Tôi có thể kiểm soát cài đặt phát lại của khung âm thanh đã thêm không?
Có, Aspose.Slides cung cấp tính linh hoạt trong việc định cấu hình cài đặt phát lại như âm lượng, chế độ phát, v.v.
### Có phiên bản dùng thử cho Aspose.Slides cho .NET không?
 Có, bạn có thể khám phá các tính năng của Aspose.Slides for .NET bằng[dùng thử miễn phí](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ cho Aspose.Slides cho .NET ở đâu?
 Tham quan[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11) để tìm kiếm sự hỗ trợ và tham gia với cộng đồng.
### Làm cách nào để mua Aspose.Slides cho .NET?
 Bạn có thể mua thư viện từ[Cửa hàng Aspose](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
