---
date: '2026-01-14'
description: Tìm hiểu cách xuất biểu đồ sang Excel bằng Aspose.Slides cho Java và
  thêm slide biểu đồ tròn vào bản trình bày. Hướng dẫn chi tiết từng bước kèm mã nguồn.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Xuất biểu đồ sang Excel bằng Aspose.Slides Java
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Xuất Biểu Đồ ra Excel bằng Aspose.Slides cho Java

**Nắm Vững Các Kỹ Thuật Trực Quan Dữ Liệu với Aspose.Slides cho Java**

Trong bối cảnh dữ liệu chi phối ngày nay, khả năng **export chart to excel** trực tiếp từ ứng dụng Java của bạn có thể biến các hình ảnh PowerPoint tĩnh thành các bộ dữ liệu có thể tái sử dụng và phân tích. Dù bạn cần tạo báo cáo, cung cấp dữ liệu cho các pipeline phân tích, hay chỉ đơn giản cho phép người dùng kinh doanh chỉnh sửa dữ liệu biểu đồ trong Excel, Aspose.Slides giúp thực hiện một cách dễ dàng. Hướng dẫn này sẽ chỉ cho bạn cách tạo biểu đồ, thêm một slide biểu đồ tròn, và xuất dữ liệu biểu đồ đó ra một workbook Excel.

**Bạn sẽ học được:**
- Tải và thao tác các tệp trình chiếu một cách dễ dàng
- **Add pie chart slide** và các loại biểu đồ khác vào slide của bạn
- **Export chart to excel** (tạo excel từ biểu đồ) cho phân tích tiếp theo
- Đặt đường dẫn workbook bên ngoài để **embed chart in presentation** và giữ dữ liệu đồng bộ

Hãy bắt đầu!

## Câu trả lời nhanh
- **Mục đích chính là gì?** Xuất dữ liệu biểu đồ từ slide PowerPoint sang tệp Excel.  
- **Phiên bản thư viện yêu cầu là gì?** Aspose.Slides for Java 25.4 hoặc mới hơn.  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể thêm slide biểu đồ tròn không?** Có – hướng dẫn cho thấy cách thêm biểu đồ Pie.  
- **Java 16 có phải là yêu cầu tối thiểu không?** Có, JDK 16 hoặc cao hơn được khuyến nghị.

## Cách xuất biểu đồ ra excel bằng Aspose.Slides?

Việc xuất dữ liệu biểu đồ ra Excel đơn giản như tải một bản trình chiếu, tạo một biểu đồ, và sau đó ghi luồng workbook của biểu đồ vào tệp. Các bước dưới đây sẽ hướng dẫn bạn toàn bộ quá trình, từ thiết lập dự án đến xác minh cuối cùng.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn đã chuẩn bị các mục sau:

### Thư viện và Phiên bản Yêu cầu
- **Aspose.Slides for Java** phiên bản 25.4 hoặc mới hơn

### Yêu cầu Thiết lập Môi trường
- Bộ công cụ phát triển Java (JDK) 16 hoặc cao hơn
- Một trình soạn thảo mã hoặc IDE như IntelliJ IDEA hoặc Eclipse

### Yêu cầu Kiến thức
- Kỹ năng lập trình Java cơ bản
- Quen thuộc với hệ thống xây dựng Maven hoặc Gradle

## Cài đặt Aspose.Slides cho Java

Để bắt đầu sử dụng Aspose.Slides, hãy đưa nó vào dự án của bạn bằng Maven hoặc Gradle.

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

Ngoài ra, bạn có thể [tải phiên bản mới nhất trực tiếp](https://releases.aspose.com/slides/java/).

### Các bước Nhận Giấy phép

Aspose.Slides cung cấp giấy phép dùng thử miễn phí để khám phá toàn bộ khả năng. Bạn cũng có thể đăng ký giấy phép tạm thời hoặc mua giấy phép để sử dụng lâu dài. Thực hiện các bước sau:
1. Truy cập [trang mua Aspose](https://purchase.aspose.com/buy) để lấy giấy phép.  
2. Đối với bản dùng thử miễn phí, tải xuống từ [Releases](https://releases.aspose.com/slides/java/).  
3. Đăng ký giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

Sau khi có tệp giấy phép, hãy khởi tạo nó trong ứng dụng Java của bạn:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Hướng dẫn Triển khai

### Tính năng 1: Tải Bản Trình Chiếu

Tải một bản trình chiếu là bước đầu tiên cho bất kỳ nhiệm vụ thao tác nào.

#### Tổng quan
Tính năng này trình bày cách tải một tệp PowerPoint hiện có bằng Aspose.Slides cho Java.

#### Triển khai Từng Bước
**Load Presentation**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```
**Explanation:**  
- `Presentation` được khởi tạo với đường dẫn tới tệp `.pptx` của bạn.  
- Luôn giải phóng đối tượng `Presentation` để giải phóng tài nguyên gốc.

### Tính năng 2: Thêm Slide Biểu Đồ Tròn

Thêm biểu đồ có thể nâng cao đáng kể việc trình bày dữ liệu, và nhiều nhà phát triển hỏi **how to add chart slide** trong Java.

#### Tổng quan
Tính năng này cho thấy cách thêm một **pie chart slide** (kịch bản “add pie chart slide” cổ điển) vào slide đầu tiên của bản trình chiếu.

#### Triển khai Từng Bước
**Add Pie Chart**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `addChart` chèn một biểu đồ Pie.  
- Các tham số xác định loại biểu đồ và vị trí/kích thước của nó trên slide.

### Tính năng 3: Tạo Excel từ Biểu Đồ

Xuất dữ liệu biểu đồ cho phép bạn **generate excel from chart** để phân tích sâu hơn.

#### Tổng quan
Tính năng này trình bày việc xuất dữ liệu biểu đồ từ bản trình chiếu sang một workbook Excel bên ngoài.

#### Triển khai Từng Bước
**Export Data**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `readWorkbookStream` trích xuất dữ liệu workbook của biểu đồ.  
- Mảng byte được ghi vào tệp `.xlsx` bằng `FileOutputStream`.

### Tính năng 4: Nhúng Biểu Đồ vào Bản Trình Chiếu với Workbook Bên Ngoài

Liên kết một biểu đồ với workbook bên ngoài giúp bạn **embed chart in presentation** và giữ dữ liệu đồng bộ.

#### Tổng quan
Tính năng này trình bày cách đặt đường dẫn workbook bên ngoài để biểu đồ có thể đọc/ghi dữ liệu trực tiếp từ Excel.

#### Triển khai Từng Bước
**Set External Workbook Path**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `setExternalWorkbook` liên kết biểu đồ với tệp Excel, cho phép cập nhật động mà không cần xây dựng lại slide.

## Ứng dụng Thực tiễn

Aspose.Slides cung cấp các giải pháp đa dạng cho nhiều tình huống:

1. **Business Reports:** Tạo báo cáo chi tiết với biểu đồ trực tiếp từ các ứng dụng Java.  
2. **Academic Presentations:** Nâng cao bài giảng với slide biểu đồ tròn tương tác.  
3. **Financial Analysis:** **Export chart to excel** để mô hình tài chính sâu sắc.  
4. **Marketing Analytics:** Trực quan hoá hiệu suất chiến dịch và **generate excel from chart** cho đội phân tích.

## Câu hỏi Thường gặp

**Q: Tôi có thể sử dụng cách tiếp cận này với các loại biểu đồ khác (ví dụ: Bar, Line) không?**  
A: Chắc chắn. Thay `ChartType.Pie` bằng bất kỳ giá trị enum `ChartType` nào khác.

**Q: Tôi có cần thư viện Excel riêng để đọc tệp đã xuất không?**  
A: Không. Tệp `.xlsx` đã xuất là một workbook Excel tiêu chuẩn có thể mở bằng bất kỳ ứng dụng bảng tính nào.

**Q: Workbook bên ngoài ảnh hưởng như thế nào đến kích thước slide?**  
A: Liên kết tới workbook bên ngoài không làm tăng đáng kể kích thước tệp PPTX; biểu đồ tham chiếu workbook tại thời gian chạy.

**Q: Có thể cập nhật dữ liệu Excel và để slide phản ánh thay đổi tự động không?**  
A: Có. Sau khi gọi `setExternalWorkbook`, bất kỳ thay đổi nào được lưu vào workbook sẽ được phản ánh khi mở bản trình chiếu lần tiếp theo.

**Q: Nếu tôi cần xuất nhiều biểu đồ từ cùng một bản trình chiếu thì sao?**  
A: Lặp qua bộ sưu tập biểu đồ của mỗi slide, gọi `readWorkbookStream()` cho từng biểu đồ, và ghi ra các tệp workbook riêng biệt.

---

**Cập nhật lần cuối:** 2026-01-14  
**Kiểm thử với:** Aspose.Slides 25.4 cho Java  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}