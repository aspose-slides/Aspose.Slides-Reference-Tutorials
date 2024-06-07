---
title: Tạo Tóm tắt Phóng to PowerPoint
linktitle: Tạo Tóm tắt Phóng to PowerPoint
second_title: Aspose.Slides API xử lý PowerPoint Java
description: Tìm hiểu cách tạo Phóng to tóm tắt trong PowerPoint bằng Aspose.Slides cho Java với hướng dẫn từng bước toàn diện này.
type: docs
weight: 16
url: /vi/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về cách tạo Tóm tắt Thu phóng trong PowerPoint bằng Aspose.Slides cho Java. Nếu bạn đang muốn thêm yếu tố động và tương tác vào bản trình bày của mình thì Thu phóng Tóm tắt là một tính năng tuyệt vời. Nó cho phép bạn tạo một slide duy nhất có thể phóng to các phần khác nhau của bản trình bày, mang lại trải nghiệm hấp dẫn và dễ điều hướng hơn cho khán giả của bạn.
Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn toàn bộ quá trình, từ thiết lập môi trường phát triển đến tạo và tùy chỉnh khung Thu phóng tóm tắt. Cho dù bạn là nhà phát triển Java dày dạn kinh nghiệm hay mới bắt đầu, bạn sẽ thấy hướng dẫn này dễ làm theo và chứa đựng nhiều thông tin chi tiết có giá trị.
## Điều kiện tiên quyết
Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ bạn cần để bắt đầu:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên máy của mình. Bạn có thể tải nó xuống từ[Trang web của Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides cho Java: Tải xuống thư viện từ[Trang phát hành Aspose](https://releases.aspose.com/slides/java/).
3. Môi trường phát triển tích hợp (IDE): Sử dụng IDE như IntelliJ IDEA, Eclipse hoặc NetBeans để có trải nghiệm phát triển liền mạch hơn.
4. Kiến thức cơ bản về Java: Làm quen với các khái niệm lập trình Java sẽ giúp bạn hiểu và thực hiện các bước trong hướng dẫn này.
## Gói nhập khẩu
Trước khi chúng ta bắt đầu, bạn cần nhập các gói cần thiết. Đảm bảo rằng bạn đã đưa Aspose.Slides cho Java vào phần phụ thuộc dự án của mình.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
```
## Bước 1: Thiết lập dự án của bạn
Đầu tiên, hãy đảm bảo môi trường phát triển của bạn được thiết lập chính xác. Thực hiện theo các bước sau để định cấu hình dự án của bạn:
### Tạo một dự án mới
1. Mở IDE của bạn.
2. Tạo một dự án Java mới.
3.  Thêm thư viện Aspose.Slides for Java vào đường dẫn xây dựng dự án của bạn. Bạn có thể tải xuống tệp JAR từ[Trang phát hành Aspose](https://releases.aspose.com/slides/java/) và đưa nó vào dự án của bạn.
### Khởi tạo bản trình bày
Tiếp theo, khởi tạo một đối tượng trình bày mới nơi bạn sẽ thêm các trang trình bày và phần của mình.
```java
Presentation pres = new Presentation();
```
## Bước 2: Thêm trang trình bày và phần
Trong bước này, chúng ta sẽ thêm các slide vào bản trình bày và sắp xếp chúng thành các phần. Tổ chức này rất quan trọng để tạo Thu phóng Tóm tắt.
### Thêm một slide và phần mới
1. Thêm một slide trống: Thêm một slide mới vào bài thuyết trình.
2. Tùy chỉnh nền slide: Đặt màu tô đồng nhất cho nền slide.
3. Thêm phần: Nhóm slide thành một phần.
Đây là mã để đạt được điều này:
```java
// Thêm slide đầu tiên
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// Thêm phần đầu tiên
pres.getSections().addSection("Section 1", slide);
```
### Lặp lại cho các phần bổ sung
Lặp lại quy trình để thêm nhiều trang trình bày và phần khác:
```java
// Thêm trang trình bày và phần thứ hai
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// Thêm trang trình bày và phần thứ ba
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// Thêm trang trình bày và phần thứ tư
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## Bước 3: Tạo Khung thu phóng tóm tắt
Bây giờ, chúng ta sẽ tạo khung Thu phóng Tóm tắt trên slide đầu tiên. Khung này sẽ đóng vai trò là thành phần tương tác cho phép người dùng phóng to các phần khác nhau.

1. Xác định vị trí Trang chiếu Đầu tiên: Truy xuất trang chiếu đầu tiên nơi bạn sẽ thêm khung Thu phóng Tóm tắt.
2. Thêm Khung thu phóng tóm tắt: Sử dụng`addSummaryZoomFrame` phương pháp thêm khung.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## Bước 4: Lưu bài thuyết trình
Cuối cùng, lưu bản trình bày vào vị trí mong muốn của bạn. Bước này đảm bảo tất cả các thay đổi của bạn được ghi vào một tệp.
### Lưu các tập tin
1. Xác định đường dẫn đầu ra: Chỉ định đường dẫn nơi bản trình bày sẽ được lưu.
2.  Lưu bài thuyết trình: Sử dụng`save` phương pháp lưu tệp ở định dạng PPTX.
```java
String resultPath = RunExamples.getOutPath() + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### Vứt bỏ đối tượng trình bày
Vứt bỏ đối tượng trình bày để giải phóng mọi tài nguyên mà nó đang sử dụng:
```java
if (pres != null) pres.dispose();
```
## Phần kết luận
 Chúc mừng! Bạn đã tạo thành công Thu phóng tóm tắt trong PowerPoint bằng Aspose.Slides cho Java. Tính năng này nâng cao bài thuyết trình của bạn bằng cách làm cho chúng tương tác và hấp dẫn hơn. Bằng cách làm theo hướng dẫn này, giờ đây bạn có kỹ năng triển khai tính năng này trong các dự án của riêng mình. Hãy nhớ khám phá[Aspose.Slides cho tài liệu Java](https://reference.aspose.com/slides/java/) để biết thêm các tính năng nâng cao và tùy chọn tùy chỉnh.
## Câu hỏi thường gặp
### Aspose.Slides cho Java là gì?
Aspose.Slides for Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và thao tác các bản trình bày PowerPoint theo chương trình bằng Java.
### Tôi có thể sử dụng Aspose.Slides for Java để tạo các loại nội dung khác trong PowerPoint không?
Có, Aspose.Slides cho Java hỗ trợ nhiều tính năng, bao gồm tạo trang trình bày, thêm hình dạng, biểu đồ, bảng, v.v.
### Có bản dùng thử miễn phí cho Aspose.Slides cho Java không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Slides cho Java từ[trang mạng](https://releases.aspose.com/).
### Làm cách nào để có được giấy phép tạm thời cho Aspose.Slides cho Java?
 Bạn có thể xin giấy phép tạm thời từ[Trang mua hàng](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm thêm ví dụ và hỗ trợ cho Aspose.Slides cho Java ở đâu?
 Bạn có thể tìm thêm ví dụ và tìm kiếm sự hỗ trợ trên[Diễn đàn hỗ trợ Aspose.Slides](https://forum.aspose.com/c/slides/11).