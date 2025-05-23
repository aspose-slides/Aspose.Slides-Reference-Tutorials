---
"date": "2025-04-17"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ hình vòng trong bài thuyết trình Java bằng Aspose.Slides, bao gồm thiết lập môi trường và điều chỉnh tính thẩm mỹ của biểu đồ."
"title": "Cách tạo biểu đồ hình bánh rán trong Java bằng Aspose.Slides cho bài thuyết trình"
"url": "/vi/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ hình bánh rán trong Java bằng Aspose.Slides cho bài thuyết trình

## Giới thiệu
Tạo các bài thuyết trình hấp dẫn về mặt thị giác là điều cần thiết để truyền tải thông tin hiệu quả. Biểu đồ là yếu tố quan trọng giúp tăng cường sự hiểu biết về phân phối dữ liệu. Hướng dẫn này hướng dẫn bạn cách tạo biểu đồ hình tròn tùy chỉnh bằng Aspose.Slides for Java, cho phép tạo biểu đồ dễ dàng với các tùy chọn tùy chỉnh mở rộng như kích thước lỗ và vị trí.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho Java
- Tạo và cấu hình biểu đồ hình tròn trong bài thuyết trình
- Điều chỉnh tính thẩm mỹ của biểu đồ như kích thước lỗ
- Lưu bản trình bày với biểu đồ mới của bạn

Chúng ta hãy bắt đầu bằng cách thiết lập môi trường!

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã đáp ứng các điều kiện tiên quyết sau:

### Thư viện và phiên bản bắt buộc
Để làm việc với Aspose.Slides for Java, hãy đưa nó vào dự án của bạn thông qua Maven hoặc Gradle hoặc tải xuống trực tiếp.

#### Yêu cầu thiết lập môi trường
- Bộ công cụ phát triển Java (JDK) đang hoạt động, tốt nhất là phiên bản 8 trở lên.
- Môi trường phát triển tích hợp (IDE) như IntelliJ IDEA hoặc Eclipse.

### Điều kiện tiên quyết về kiến thức
Sự quen thuộc với Java và các khái niệm lập trình cơ bản là có lợi. Kiến thức cơ bản về Maven hoặc Gradle sẽ giúp hợp lý hóa quá trình thiết lập.

## Thiết lập Aspose.Slides cho Java
Có thể thực hiện việc tích hợp Aspose.Slides vào dự án của bạn theo nhiều cách:

**Chuyên gia:**
Thêm sự phụ thuộc này vào `pom.xml` tài liệu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Cấp độ:**
Bao gồm điều này trong của bạn `build.gradle` tài liệu:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải xuống trực tiếp:**
Ngoài ra, hãy tải xuống phiên bản mới nhất từ [Aspose.Slides cho bản phát hành Java](https://releases.aspose.com/slides/java/).

### Mua lại giấy phép
- **Dùng thử miễn phí**: Bắt đầu bằng cách tải xuống phiên bản dùng thử để khám phá các tính năng của Aspose.Slides.
- **Giấy phép tạm thời**: Xin giấy phép tạm thời để mở rộng chức năng mà không có giới hạn.
- **Mua**:Để sử dụng lâu dài, bạn cần phải mua giấy phép.

Sau khi thiết lập xong thư viện và môi trường, chúng ta hãy chuyển sang triển khai biểu đồ hình tròn.

## Hướng dẫn thực hiện

### Tạo biểu đồ hình bánh rán
Tạo bài thuyết trình với biểu đồ hình tròn tùy chỉnh bằng Aspose.Slides bao gồm một số bước. Chúng tôi sẽ chia nhỏ chúng để rõ ràng hơn:

#### Khởi tạo đối tượng trình bày
Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp, đại diện cho tài liệu PowerPoint của bạn.
```java
// Tạo một thể hiện của lớp Presentation để biểu diễn một tài liệu PPTX
Presentation presentation = new Presentation();
```
Bước này khởi tạo bản trình bày để bạn có thể thêm slide và biểu đồ.

#### Thêm biểu đồ hình bánh rán vào trang chiếu
Truy cập trang chiếu đầu tiên (hoặc tạo một trang chiếu nếu cần) và thêm biểu đồ hình tròn:
```java
// Truy cập trang chiếu đầu tiên trong bài thuyết trình
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Vị trí tại (50, 50) với kích thước 400x400
```
Đoạn mã này thêm biểu đồ hình tròn vào slide đầu tiên. Các tham số xác định vị trí và kích thước của biểu đồ trên slide.

#### Cấu hình kích thước lỗ bánh rán
Để tạo cho biểu đồ hình bánh rán của bạn một diện mạo độc đáo, hãy điều chỉnh kích thước lỗ:
```java
// Đặt kích thước lỗ cho biểu đồ hình bánh rán thành 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Ở đây, chúng tôi đặt kích thước lỗ là 90%, làm cho nó gần như là một vòng tròn đầy đủ. Điều chỉnh giá trị này dựa trên nhu cầu thiết kế của bạn.

#### Lưu bài thuyết trình
Sau khi cấu hình biểu đồ, hãy lưu bản trình bày:
```java
// Lưu bản trình bày vào đĩa ở định dạng PPTX tại thư mục đã chỉ định
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Dòng này ghi những thay đổi của bạn vào một tệp có tên `DoughnutHoleSize_out.pptx` trong thư mục được chỉ định của bạn.

#### Tài nguyên dọn dẹp
Cuối cùng, hãy đảm bảo bạn đã loại bỏ đối tượng trình bày:
```java
// Loại bỏ đối tượng trình bày để giải phóng tài nguyên
if (presentation != null) presentation.dispose();
```
Bước này rất quan trọng để quản lý tài nguyên và tránh rò rỉ bộ nhớ.

### Ứng dụng thực tế
Biểu đồ hình tròn rất linh hoạt. Sau đây là một số trường hợp mà chúng tỏa sáng:
1. **Phân bổ ngân sách**: Hiển thị cách phân bổ ngân sách giữa các phòng ban.
2. **Kết quả khảo sát**: Hình dung câu trả lời cho các câu hỏi có nhiều lựa chọn.
3. **Nguồn lưu lượng truy cập trang web**: Hiển thị phần trăm lưu lượng truy cập đến từ các nguồn khác nhau.

### Cân nhắc về hiệu suất
Khi làm việc với Aspose.Slides, hãy cân nhắc những mẹo sau để có hiệu suất tối ưu:
- Quản lý bộ nhớ bằng cách loại bỏ các đối tượng khi không còn cần thiết.
- Sử dụng luồng cho các tập dữ liệu lớn để giảm thiểu việc sử dụng bộ nhớ.
- Tối ưu hóa mã của bạn bằng cách sử dụng lại các trường hợp có thể.

## Phần kết luận
Xin chúc mừng! Bạn đã học cách tạo và tùy chỉnh biểu đồ hình tròn bằng Aspose.Slides for Java. Hướng dẫn này bao gồm thiết lập thư viện, thêm biểu đồ vào bản trình bày và tinh chỉnh giao diện của chúng.

Để tiếp tục khám phá các khả năng của Aspose.Slides, hãy cân nhắc thử nghiệm các loại biểu đồ khác hoặc tìm hiểu sâu hơn về các tính năng tự động hóa bản trình bày.

**Các bước tiếp theo:**
- Thử nghiệm với các cấu hình biểu đồ khác nhau.
- Khám phá thêm tài liệu Aspose.Slides để biết thêm nhiều tính năng nâng cao.

Bạn đã sẵn sàng tạo biểu đồ hình tròn của riêng mình chưa? Hãy thử áp dụng giải pháp này vào dự án tiếp theo của bạn!

## Phần Câu hỏi thường gặp
1. **Tôi có thể điều chỉnh màu sắc của các phân đoạn biểu đồ hình tròn không?**
   Có, bạn có thể tùy chỉnh màu phân đoạn bằng cách sử dụng `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` để thiết lập kiểu tô đặc và chỉ định màu mong muốn.

2. **Làm thế nào để thêm nhãn dữ liệu vào biểu đồ?**
   Sử dụng `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` và các phương pháp tương tự để thêm điểm dữ liệu và nhãn theo chương trình.

3. **Có thể lưu biểu đồ ở các định dạng khác ngoài PPTX không?**
   Chắc chắn rồi! Aspose.Slides hỗ trợ nhiều định dạng đầu ra như PDF, XPS và các định dạng hình ảnh như PNG hoặc JPEG.

4. **Tôi phải làm sao nếu gặp lỗi khi lưu bản trình bày?**
   Đảm bảo đường dẫn thư mục của bạn là chính xác và bạn có quyền ghi cho vị trí đã chỉ định. Kiểm tra xem phiên bản Aspose.Slides bạn đang sử dụng có hỗ trợ định dạng tệp bạn đang cố lưu hay không.

5. **Tôi có thể tự động cập nhật biểu đồ bằng nguồn dữ liệu trực tiếp không?**
   Có, bằng cách tích hợp API hoặc cơ sở dữ liệu vào ứng dụng Java, bạn có thể cập nhật dữ liệu biểu đồ và làm mới bản trình bày khi cần.

## Tài nguyên
- **Tài liệu**: Khám phá các tham chiếu API chi tiết tại [Aspose.Slides cho Java](https://reference.aspose.com/slides/java/).
- **Tải về**: Nhận phiên bản thư viện mới nhất từ [Aspose.Slides phát hành](https://releases.aspose.com/slides/java/).
- **Mua**: Để có quyền truy cập đầy đủ, hãy mua giấy phép tại [Mua Aspose](https://purchase.aspose.com/buy).
- **Dùng thử miễn phí**: Dùng thử Aspose.Slides với bản dùng thử miễn phí có sẵn trên trang tải xuống.
- **Giấy phép tạm thời**Xin giấy phép tạm thời để thử nghiệm mở rộng mà không có giới hạn.
- **Ủng hộ**: Có thắc mắc? Truy cập [Diễn đàn Aspose](https://forum.aspose.com/c/slides/11) để được hỗ trợ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}