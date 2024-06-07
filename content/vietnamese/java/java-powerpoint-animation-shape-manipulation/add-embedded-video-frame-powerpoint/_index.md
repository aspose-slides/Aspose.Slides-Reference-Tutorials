---
title: Thêm khung video nhúng vào PowerPoint
linktitle: Thêm khung video nhúng vào PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách nhúng khung video trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước này. Nâng cao bài thuyết trình của bạn một cách dễ dàng.
type: docs
weight: 21
url: /vi/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---
## Giới thiệu
Việc thêm video vào bản trình bày PowerPoint của bạn có thể khiến chúng trở nên hấp dẫn và giàu thông tin hơn. Sử dụng Aspose.Slides cho Java, bạn có thể dễ dàng nhúng video trực tiếp vào trang trình bày của mình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trong quy trình, đảm bảo bạn hiểu mọi phần của mã và cách thức hoạt động của mã. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn này sẽ giúp bạn cải thiện bản trình bày của mình bằng các video được nhúng.
## Điều kiện tiên quyết
Trước khi đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên máy của mình.
2. Aspose.Slides cho Java: Tải xuống và cài đặt thư viện Aspose.Slides cho Java.
3. Môi trường phát triển tích hợp (IDE): Sử dụng IDE như IntelliJ IDEA hoặc Eclipse để có trải nghiệm phát triển tốt hơn.
4. Tệp Video: Có tệp video bạn muốn nhúng vào bản trình bày PowerPoint của mình.
## Gói nhập khẩu
Trước tiên, bạn sẽ cần nhập các gói cần thiết để hoạt động với Aspose.Slides. Việc nhập này sẽ giúp bạn quản lý các trang trình bày, video và tệp trình bày.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Bước 1: Thiết lập môi trường của bạn
Trước khi bạn bắt đầu viết mã, hãy đảm bảo môi trường của bạn được thiết lập chính xác. Điều này liên quan đến việc tạo các thư mục cần thiết và chuẩn bị tệp video.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Tạo thư mục nếu nó chưa có.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Bước 2: Khởi tạo lớp trình bày
 Tạo một thể hiện của`Presentation` lớp học. Lớp này đại diện cho tệp PowerPoint của bạn.
```java
// Khởi tạo lớp Trình bày đại diện cho PPTX
Presentation pres = new Presentation();
```
## Bước 3: Lấy slide đầu tiên
Truy cập trang trình bày đầu tiên trong bản trình bày nơi bạn sẽ nhúng video.
```java
// Nhận slide đầu tiên
ISlide sld = pres.getSlides().get_Item(0);
```
## Bước 4: Thêm video vào bài thuyết trình
Nhúng tập tin video vào bản trình bày. Đảm bảo đường dẫn video được chỉ định chính xác.
```java
// Nhúng video vào trong bản trình bày
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Bước 5: Thêm khung hình video vào slide
Tạo khung video trên slide và đặt kích thước cũng như vị trí của nó.
```java
// Thêm khung video
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Bước 6: Định cấu hình thuộc tính khung video
Đặt video thành khung video và định cấu hình cài đặt phát lại của nó như chế độ phát và âm lượng.
```java
// Đặt video thành Khung video
vf.setEmbeddedVideo(vid);
// Đặt Chế độ phát và âm lượng của video
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Bước 7: Lưu bài thuyết trình
Lưu bản trình bày có video được nhúng vào thư mục được chỉ định của bạn.
```java
// Ghi tập tin PPTX vào đĩa
pres.save(resultPath, SaveFormat.Pptx);
```
## Bước 8: Dọn dẹp tài nguyên
Cuối cùng, loại bỏ đối tượng trình bày để giải phóng tài nguyên.
```java
// Vứt bỏ đối tượng trình bày
if (pres != null) pres.dispose();
```
## Phần kết luận
Nhúng video vào bản trình bày PowerPoint của bạn bằng Aspose.Slides cho Java là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể cải thiện bản trình bày của mình bằng nội dung video hấp dẫn. Hãy nhớ rằng, luyện tập sẽ tạo nên sự hoàn hảo, vì vậy hãy thử nhúng các video khác nhau và điều chỉnh thuộc tính của chúng để xem những gì phù hợp nhất với nhu cầu của bạn.
## Câu hỏi thường gặp
### Tôi có thể nhúng nhiều video vào một slide không?
Có, bạn có thể nhúng nhiều video vào một trang chiếu bằng cách thêm nhiều khung hình video.
### Làm cách nào để kiểm soát việc phát lại video?
 Bạn có thể điều khiển việc phát lại bằng cách sử dụng`setPlayMode` Và`setVolume` các phương pháp của`IVideoFrame` lớp học.
### Aspose.Slides hỗ trợ những định dạng video nào?
Aspose.Slides hỗ trợ nhiều định dạng video khác nhau bao gồm MP4, AVI và WMV.
### Tôi có cần giấy phép để sử dụng Aspose.Slides không?
Có, bạn cần có giấy phép hợp lệ để sử dụng Aspose.Slides. Bạn có thể có được giấy phép tạm thời để đánh giá.
### Tôi có thể tùy chỉnh kích thước và vị trí của khung hình video không?
Có, bạn có thể tùy chỉnh kích thước và vị trí bằng cách thiết lập các thông số phù hợp khi thêm khung hình video.