---
date: '2026-02-09'
description: Học cách tạo biểu đồ và xuất biểu đồ sang Excel bằng Aspose.Slides cho
  Java. Thành thạo trực quan hoá dữ liệu, các slide báo cáo kinh doanh và tạo sổ làm
  việc.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Cách tạo biểu đồ với Aspose.Slides Java
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách Tạo Biểu Đồ Sử Dụng Aspose.Slides cho Java

**Nắm Vững Các Kỹ Thuật Trực Quan Dữ Liệu với Aspose.Slides cho Java**

Trong bối cảnh dữ liệu chi phối ngày nay, *how to create chart* một cách lập trình là một kỹ năng có thể biến các con số thô thành những câu chuyện hình ảnh hấp dẫn. Cho dù bạn đang xây dựng một bộ slide báo cáo kinh doanh hay một bảng điều khiển phân tích tương tác, Aspose.Slides cho Java cung cấp cho bạn khả năng tạo, tùy chỉnh và xuất biểu đồ trực tiếp từ mã của mình. Trong hướng dẫn này, bạn sẽ học cách tạo các đối tượng biểu đồ, xuất dữ liệu biểu đồ sang Excel, và liên kết biểu đồ với các workbook bên ngoài để quản lý dữ liệu liền mạch.

## Câu Trả Lời Nhanh
- **Thư viện cần thiết là gì?** Aspose.Slides for Java (v25.4+).  
- **Tôi có thể xuất dữ liệu biểu đồ sang Excel không?** Có – sử dụng `readWorkbookStream()` và ghi các byte vào một tệp *.xlsx*.  
- **Phiên bản Java nào được yêu cầu?** JDK 16 hoặc cao hơn.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép vĩnh viễn cần thiết cho môi trường sản xuất.  
- **Loại biểu đồ nào được minh họa?** Biểu đồ Pie, nhưng cùng một cách tiếp cận cũng áp dụng cho Bar, Line và các loại biểu đồ khác.

## Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API thuần Java cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi các bản trình bày PowerPoint mà không cần Microsoft Office. Nó hỗ trợ đầy đủ các loại biểu đồ, ràng buộc dữ liệu và khả năng xuất, làm cho nó trở thành lựa chọn lý tưởng cho các dự án **data visualization java**.

## Tại sao nên sử dụng Aspose.Slides để tạo biểu đồ và xuất biểu đồ sang Excel?
- **Không cần cài đặt Office** – hoạt động trên bất kỳ máy chủ hoặc môi trường đám mây nào.  
- **Thư viện biểu đồ phong phú** – hàng chục loại biểu đồ và kiểm soát đầy đủ về kiểu dáng.  
- **Xuất Excel trực tiếp** – tạo một workbook bên ngoài cho việc phân tích tiếp theo.  
- **Hướng tới hiệu năng** – tiêu thụ bộ nhớ thấp và xử lý nhanh cho các bộ slide lớn.

## Yêu Cầu Trước
Trước khi chúng ta bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:

### Thư viện và Phiên bản Yêu Cầu
- **Aspose.Slides cho Java** phiên bản 25.4 trở lên

### Yêu Cầu Thiết Lập Môi Trường
- Java Development Kit (JDK) 16 hoặc cao hơn  
- Một IDE như IntelliJ IDEA hoặc Eclipse (hoặc bất kỳ trình soạn thảo văn bản nào bạn thích)

### Kiến Thức Yêu Cầu
- Kiến thức cơ bản về lập trình Java  
- Quen thuộc với các công cụ xây dựng Maven hoặc Gradle

## Cài Đặt Aspose.Slides cho Java
Thêm thư viện vào dự án của bạn bằng hệ thống xây dựng yêu thích.

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

Hoặc bạn có thể [tải phiên bản mới nhất trực tiếp](https://releases.aspose.com/slides/java/).

### Các Bước Nhận Giấy Phép
Aspose.Slides cung cấp giấy phép dùng thử miễn phí để khám phá toàn bộ khả năng của nó. Bạn cũng có thể xin giấy phép tạm thời hoặc mua một giấy phép cho việc sử dụng kéo dài. Thực hiện các bước sau:

1. Truy cập [trang mua Aspose](https://purchase.aspose.com/buy) để lấy giấy phép của bạn.  
2. Đối với bản dùng thử miễn phí, tải xuống từ [Releases](https://releases.aspose.com/slides/java/).  
3. Xin giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

Khi đã có tệp giấy phép, khởi tạo nó trong ứng dụng Java của bạn:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Hướng Dẫn Từng Bước

### Cách tạo biểu đồ – Tải một Bản Trình Bày
Việc tải một tệp PowerPoint hiện có là bước đầu tiên trước khi bạn có thể thêm hoặc chỉnh sửa biểu đồ.

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

**Giải thích:**  
- `Presentation` đại diện cho tệp PowerPoint.  
- Luôn gọi `dispose()` để giải phóng tài nguyên gốc.

### Cách tạo biểu đồ – Thêm Biểu Đồ Pie vào Slide
Bây giờ chúng ta sẽ chèn một biểu đồ Pie, rất phù hợp để hiển thị dữ liệu tỷ lệ.

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

**Giải thích:**  
- `addChart` chèn biểu đồ vào slide đầu tiên.  
- Các tham số xác định loại biểu đồ, vị trí X/Y và kích thước.

### Cách xuất biểu đồ sang Excel – Xuất Dữ Liệu Biểu Đồ
Việc xuất dữ liệu biểu đồ cho phép các nhà phân tích làm việc với các con số trong Excel, tạo ra những hiểu biết sâu hơn.

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

**Giải thích:**  
- `readWorkbookStream()` trích xuất workbook Excel nền tảng của biểu đồ dưới dạng mảng byte.  
- Mảng byte này được ghi vào `externalWorkbook1.xlsx`, cung cấp cho bạn một tệp Excel sẵn sàng sử dụng.

### Cách tạo biểu đồ – Đặt Workbook Ngoài để Dữ Liệu Động
Liên kết một biểu đồ với workbook bên ngoài cho phép bạn cập nhật biểu đồ chỉ bằng cách chỉnh sửa tệp Excel.

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

**Giải thích:**  
- `setExternalWorkbook` gắn biểu đồ với tệp Excel được chỉ định, cho phép cập nhật dữ liệu trực tiếp mà không cần xây dựng lại slide.

## Ứng Dụng Thực Tế
Aspose.Slides cung cấp các giải pháp đa dạng cho nhiều tình huống thực tế:

1. **Business Report Slides:** Tự động tạo các biểu đồ hiệu suất quý từ các pipeline dữ liệu của bạn.  
2. **Academic Presentations:** Chuyển dữ liệu nghiên cứu thành các hình ảnh trực quan rõ ràng mà không cần vẽ biểu đồ thủ công.  
3. **Financial Analysis:** Xuất dữ liệu biểu đồ sang Excel để các kiểm toán viên xác minh số liệu.  
4. **Marketing Analytics:** Trực quan hoá các chỉ số chiến dịch và chia sẻ workbook có thể chỉnh sửa với các bên liên quan.

## Các Vấn Đề Thường Gặp & Khắc Phục
- **`FileNotFoundException`** – Kiểm tra xem `dataDir` có trỏ tới thư mục hợp lệ và đường dẫn xuất có thể ghi được không.  
- **Memory leaks** – Luôn gọi `pres.dispose()` trong khối `finally` để giải phóng tài nguyên gốc.  
- **Chart not appearing** – Đảm bảo chỉ số slide (`get_Item(0)`) khớp với một slide thực sự tồn tại.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng loại biểu đồ khác (ví dụ: Bar, Line) với cùng một đoạn mã không?**  
A: Có. Thay `ChartType.Pie` bằng bất kỳ giá trị enum `ChartType` nào khác như `ChartType.Bar` hoặc `ChartType.Line`.

**Q: Có thể cập nhật workbook bên ngoài sau khi biểu đồ đã được tạo không?**  
A: Chắc chắn. Chỉnh sửa tệp Excel trực tiếp; biểu đồ liên kết sẽ phản ánh các thay đổi khi mở lại bản trình bày.

**Q: Tôi có cần giấy phép riêng cho tính năng xuất Excel không?**  
A: Không. Khả năng xuất Excel đã được bao gồm trong giấy phép tiêu chuẩn của Aspose.Slides cho Java.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides cho Java hỗ trợ JDK 16 và mới hơn; các phiên bản cũ hơn có thể hoạt động nhưng không được kiểm tra chính thức.

**Q: Làm thế nào để nhúng workbook Excel đã tạo vào trong tệp PPTX?**  
A: Sử dụng `chart.getChartData().setExternalWorkbook(null)` để nhúng workbook, hoặc giữ liên kết bên ngoài để cập nhật động.

---

**Cập Nhật Cuối Cùng:** 2026-02-09  
**Đã Kiểm Tra Với:** Aspose.Slides cho Java 25.4 (jdk16 classifier)  
**Tác Giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}