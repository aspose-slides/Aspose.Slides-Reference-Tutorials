---
date: '2026-03-18'
description: Tìm hiểu cách tạo biểu đồ cột cụm trong Java với Aspose.Slides, cách
  thêm biểu đồ, thiết lập màu sắc và lưu bản trình bày dưới dạng PPTX. Hướng dẫn từng
  bước kèm ví dụ mã.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ cột nhóm trong Java với Aspose.Slides

## Giới thiệu
Việc tạo ra các biểu diễn dữ liệu hấp dẫn về mặt hình ảnh là điều cần thiết cho các bài thuyết trình kinh doanh ấn tượng, và việc học **cách tạo biểu đồ cột nhóm** bằng lập trình có thể giúp bạn tiết kiệm hàng giờ công việc thủ công. Trong hướng dẫn này, bạn sẽ thấy **cách thêm biểu đồ**, tự động **đặt màu**, và cuối cùng **lưu bản trình bày dưới dạng PPTX** bằng **Aspose.Slides for Java**. Chúng tôi sẽ hướng dẫn từng bước mọi thứ bạn cần—từ việc cài đặt thư viện, thêm biểu đồ, tùy chỉnh màu nền cho các series, đến việc lưu file.

### Những gì bạn sẽ đạt được
- Cài đặt và cấu hình Aspose.Slides cho Java  
- **Tạo biểu đồ cột nhóm** trong một bản trình bày mới hoàn toàn  
- Tự động áp dụng màu nền cho series (**how to set colors**)  
- **Lưu bản trình bày dưới dạng PPTX** vào đĩa (**how to save presentation**)  

Hãy hoàn thành các điều kiện tiên quyết trước khi chúng ta bắt đầu tạo biểu đồ.

## Câu trả lời nhanh
- **Lớp chính là gì?** `Presentation` từ `com.aspose.slides`  
- **Làm thế nào để thêm biểu đồ?** Sử dụng `addChart(ChartType.ClusteredColumn, …)` trên bộ sưu tập shape của slide (**how to add chart**)  
- **Có thể tự động đặt màu không?** Có, gọi `setAutomaticSeriesColor(true)` trên mỗi series (**how to set colors**)  
- **Định dạng nào được sử dụng để lưu?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Có cần giấy phép không?** Bản dùng thử hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất  

## Các điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn có các công cụ và kiến thức cần thiết:

### Thư viện và phụ thuộc cần thiết
Bạn sẽ cần thư viện Aspose.Slides cho Java. Đảm bảo bạn đang sử dụng phiên bản 25.4 hỗ trợ JDK16.

### Yêu cầu thiết lập môi trường
Môi trường phát triển của bạn nên hỗ trợ Java (tốt nhất là JDK16) và có khả năng xây dựng dự án bằng Maven hoặc Gradle.

### Kiến thức tiên quyết
Hiểu biết cơ bản về lập trình Java, làm việc với các thư viện qua Maven/Gradle, và nắm bắt cách hoạt động của các bản trình bày PowerPoint sẽ rất hữu ích.

## Cài đặt Aspose.Slides cho Java
Để tích hợp Aspose.Slides vào dự án của bạn, hãy làm theo các hướng dẫn cài đặt dưới đây:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Tải trực tiếp**  
Đối với những người muốn tải trực tiếp, hãy truy cập [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Các bước lấy giấy phép
- **Dùng thử miễn phí**: Bắt đầu với bản dùng thử miễn phí để khám phá các tính năng.  
- **Giấy phép tạm thời**: Nhận giấy phép tạm thời để thử nghiệm không giới hạn.  
- **Mua**: Đối với việc sử dụng lâu dài, mua giấy phép đầy đủ.  

**Khởi tạo và Cài đặt Cơ bản**  
Khởi tạo Aspose.Slides như sau:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Cách Thêm Biểu Đồ Cột Nhóm
Thêm một biểu đồ là bước chức năng đầu tiên. Phần này giải thích **cách thêm biểu đồ** bằng API.

### Tính năng 1: Tạo Biểu Đồ Cột Nhóm
Hãy tạo một biểu đồ cột nhóm bằng Aspose.Slides cho Java. Tính năng này cho phép bạn thêm các biểu đồ hấp dẫn vào slide một cách dễ dàng.

#### Tổng quan
Trong phần này, chúng ta sẽ khởi tạo một bản trình bày mới và chèn một biểu đồ cột nhóm vào slide đầu tiên.

**Bước 1: Khởi tạo Presentation**  
Tạo một đối tượng `Presentation` để bắt đầu làm việc với các tệp PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Bước 2: Thêm Biểu Đồ Cột Nhóm**  
Thêm biểu đồ tại tọa độ đã chỉ định (100, 50) và kích thước (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Bước 3: Dọn Dẹp Tài Nguyên**  
Luôn giải phóng tài nguyên để tránh rò rỉ bộ nhớ:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Cách Đặt Màu Cho Biểu Đồ
Tăng cường tính thẩm mỹ bằng cách tự động áp dụng màu nền cho series (**how to set colors**).

### Tính năng 2: Đặt Màu Tự Động Cho Series
Đặt màu cho mỗi series của biểu đồ một cách tự động để tạo giao diện thống nhất.

#### Tổng quan
Đặt màu cho mỗi series của biểu đồ một cách tự động để tạo giao diện thống nhất.

**Bước 1: Truy cập Biểu Đồ và Duyệt Series**  
Sau khi tạo biểu đồ, truy cập vào nó và duyệt qua các series:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Bước 2: Quản Lý Tài Nguyên**  
Giải phóng đối tượng presentation khi hoàn thành:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Cách Lưu Bản Trình Bày Dưới Dạng PPTX
Khi biểu đồ đã hoàn hảo, bạn sẽ muốn lưu file (**how to save presentation**).

### Tính năng 3: Lưu Bản Trình Bày Lên Đĩa
Cuối cùng, lưu công việc của bạn một cách dễ dàng bằng Aspose.Slides.

#### Tổng quan
Lưu các bản trình bày đã chỉnh sửa ở định dạng và vị trí mong muốn.

**Bước 1: Xác Định Đường Dẫn Đầu Ra**  
Chỉ định nơi bạn muốn lưu file:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Bước 2: Lưu Bản Trình Bày**  
Sử dụng phương thức `save` của đối tượng `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Ứng Dụng Thực Tiễn
- **Báo cáo tài chính**: Trực quan hoá doanh thu hàng quý một cách rõ ràng.  
- **Phân tích dữ liệu marketing**: Trình bày kết quả chiến dịch bằng hình ảnh hấp dẫn.  
- **Quản lý dự án**: Theo dõi các mốc và tiến độ một cách trực quan trong các cuộc họp nhóm.

## Các Yếu Tố Hiệu Suất
Khi làm việc với Aspose.Slides, hãy cân nhắc các thực hành tốt sau:

- Quản lý bộ nhớ hiệu quả bằng cách giải phóng các đối tượng `Presentation` kịp thời.  
- Tối ưu kích thước file khi lưu bản trình bày để tiết kiệm không gian đĩa.  
- Sử dụng cấu trúc dữ liệu hiệu quả cho series của biểu đồ để nâng cao hiệu suất.

## Kết luận
Chúc mừng! Bạn đã học cách **tạo biểu đồ cột nhóm**, tự động **đặt màu**, và **lưu bản trình bày dưới dạng PPTX** bằng Aspose.Slides cho Java. Kỹ năng này không chỉ nâng cao các bản trình bày của bạn mà còn giúp quy trình biểu diễn dữ liệu trực quan trở nên nhanh gọn hơn.

**Các bước tiếp theo:**  
Khám phá các tính năng khác như tùy chỉnh các thành phần của biểu đồ, thêm nhãn dữ liệu, hoặc tích hợp với nguồn dữ liệu bên ngoài để mở rộng khả năng dự án của bạn.

## Phần Câu Hỏi Thường Gặp
1. **Làm thế nào để cài đặt Aspose.Slides cho một phiên bản JDK cụ thể?**  
   - Sử dụng các phụ thuộc Maven/Gradle chỉ định `classifier` như đã trình bày trong phần cài đặt.  
2. **Nếu bản trình bày của tôi không lưu đúng cách thì sao?**  
   - Đảm bảo bạn có quyền ghi vào thư mục đầu ra và đường dẫn tệp là chính xác.  
3. **Tôi có thể tạo các loại biểu đồ khác bằng Aspose.Slides cho Java không?**  
   - Chắc chắn! Khám phá các tùy chọn `ChartType` như Pie, Bar, hoặc Line charts.  
4. **Làm sao để xử lý bộ dữ liệu lớn trong biểu đồ?**  
   - Tối ưu cấu trúc dữ liệu và cân nhắc tiền xử lý dữ liệu trước khi trực quan hoá.  
5. **Tôi có thể tìm thêm ví dụ về việc sử dụng Aspose.Slides cho Java ở đâu?**  
   - Truy cập [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) để xem các hướng dẫn chi tiết và mẫu mã.

## Tài Nguyên
- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy a License](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary License**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Slides 25.4 (JDK16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}