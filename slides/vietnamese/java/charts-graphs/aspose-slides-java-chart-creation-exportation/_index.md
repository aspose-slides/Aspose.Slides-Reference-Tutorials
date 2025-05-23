---
"date": "2025-04-17"
"description": "Học cách tạo và xuất biểu đồ bằng Aspose.Slides trong Java. Nắm vững các kỹ thuật trực quan hóa dữ liệu với hướng dẫn từng bước và ví dụ mã."
"title": "Aspose.Slides Java&#58; Tạo và Xuất Biểu đồ để Trực quan hóa Dữ liệu"
"url": "/vi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tạo và xuất biểu đồ bằng Aspose.Slides Java

**Kỹ thuật trực quan hóa dữ liệu chính với Aspose.Slides cho Java**

Trong bối cảnh dữ liệu ngày nay, trực quan hóa dữ liệu hiệu quả là điều cần thiết để đưa ra quyết định sáng suốt. Tích hợp các chức năng biểu đồ vào ứng dụng Java của bạn có thể chuyển đổi dữ liệu thô thành những câu chuyện trực quan hấp dẫn. Hướng dẫn này sẽ hướng dẫn bạn cách tạo và xuất biểu đồ bằng Aspose.Slides for Java, đảm bảo bài thuyết trình của bạn vừa mang tính thông tin vừa hấp dẫn về mặt trực quan.

**Những gì bạn sẽ học được:**
- Tải và thao tác các tập tin trình bày một cách dễ dàng
- Thêm nhiều loại biểu đồ khác nhau vào slide của bạn
- Xuất dữ liệu biểu đồ sang sổ làm việc bên ngoài một cách liền mạch
- Thiết lập đường dẫn sổ làm việc bên ngoài để quản lý dữ liệu hiệu quả

Chúng ta hãy bắt đầu nhé!

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị sẵn các thiết lập sau:

### Thư viện và phiên bản bắt buộc
- **Aspose.Slides cho Java** phiên bản 25.4 trở lên

### Yêu cầu thiết lập môi trường
- Bộ phát triển Java (JDK) 16 trở lên
- Một trình soạn thảo mã hoặc IDE như IntelliJ IDEA hoặc Eclipse

### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình Java
- Quen thuộc với hệ thống xây dựng Maven hoặc Gradle

## Thiết lập Aspose.Slides cho Java
Để bắt đầu sử dụng Aspose.Slides, bạn cần đưa nó vào dự án của mình. Sau đây là cách thực hiện:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Tốt nghiệp**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ngoài ra, bạn có thể [tải xuống phiên bản mới nhất trực tiếp](https://releases.aspose.com/slides/java/).

### Các bước xin cấp giấy phép
Aspose.Slides cung cấp giấy phép dùng thử miễn phí để khám phá toàn bộ khả năng của nó. Bạn cũng có thể đăng ký giấy phép tạm thời hoặc mua giấy phép để sử dụng lâu dài. Thực hiện theo các bước sau:
1. Ghé thăm [Trang mua hàng Aspose](https://purchase.aspose.com/buy) để có được giấy phép của bạn.
2. Để dùng thử miễn phí, hãy tải xuống từ [Phát hành](https://releases.aspose.com/slides/java/).
3. Xin giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).

Sau khi có tệp giấy phép, hãy khởi tạo nó trong ứng dụng Java của bạn:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Hướng dẫn thực hiện
### Tính năng 1: Tải bài trình bày
Tải bản trình bày là bước đầu tiên của bất kỳ tác vụ thao tác nào.

#### Tổng quan
Tính năng này trình bày cách tải tệp PowerPoint hiện có bằng Aspose.Slides for Java.

#### Thực hiện từng bước
**Thêm biểu đồ vào trang chiếu**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Đặt đường dẫn đến thư mục tài liệu của bạn
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Tải một bài thuyết trình hiện có
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Dọn dẹp tài nguyên
        if (pres != null) pres.dispose();
    }
}
```
**Giải thích:**
- `Presentation` được khởi tạo với đường dẫn đến `.pptx` tài liệu.
- Luôn luôn vứt bỏ `Presentation` phản đối việc cung cấp tài nguyên miễn phí.

### Tính năng 2: Thêm biểu đồ vào trang chiếu
Việc thêm biểu đồ có thể cải thiện đáng kể việc trình bày dữ liệu.

#### Tổng quan
Tính năng này hướng dẫn cách thêm biểu đồ hình tròn vào trang chiếu đầu tiên của bài thuyết trình.

#### Thực hiện từng bước
**Thêm biểu đồ vào trang chiếu**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Đặt đường dẫn đến thư mục tài liệu của bạn
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Thêm biểu đồ hình tròn tại vị trí (50, 50) với chiều rộng 400 và chiều cao 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Giải thích:**
- `addChart` phương pháp này được sử dụng để chèn biểu đồ hình tròn.
- Các tham số bao gồm loại biểu đồ và vị trí/kích thước của biểu đồ trên trang chiếu.

### Tính năng 3: Xuất dữ liệu biểu đồ sang sổ làm việc bên ngoài
Việc xuất dữ liệu cho phép phân tích sâu hơn bên ngoài PowerPoint.

#### Tổng quan
Tính năng này minh họa cách xuất dữ liệu biểu đồ từ bản trình bày sang bảng tính Excel bên ngoài.

#### Thực hiện từng bước
**Xuất dữ liệu**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Đặt đường dẫn đến thư mục tài liệu và thư mục đầu ra của bạn
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Truy cập biểu đồ của slide đầu tiên
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Xác định đường dẫn cho sổ làm việc bên ngoài
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Xuất dữ liệu biểu đồ sang luồng Excel
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
- `readWorkbookStream` trích xuất dữ liệu biểu đồ.
- Dữ liệu được ghi vào tệp Excel bằng cách sử dụng `FileOutputStream`.

### Tính năng 4: Thiết lập sổ làm việc bên ngoài cho dữ liệu biểu đồ
Việc liên kết biểu đồ với sổ làm việc bên ngoài có thể hợp lý hóa việc quản lý dữ liệu.

#### Tổng quan
Tính năng này minh họa cách thiết lập đường dẫn sổ làm việc bên ngoài để lưu trữ dữ liệu biểu đồ.

#### Thực hiện từng bước
**Đặt Đường dẫn Sổ làm việc Bên ngoài**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Đặt đường dẫn đến thư mục tài liệu của bạn
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Truy cập biểu đồ của slide đầu tiên
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Xác định và thiết lập đường dẫn cho sổ làm việc bên ngoài
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Giải thích:**
- `setExternalWorkbook` liên kết biểu đồ với tệp Excel, cho phép cập nhật dữ liệu động.

## Ứng dụng thực tế
Aspose.Slides cung cấp các giải pháp đa năng cho nhiều tình huống khác nhau:

1. **Báo cáo kinh doanh:** Tạo báo cáo chi tiết có biểu đồ trực tiếp từ ứng dụng Java.
2. **Bài thuyết trình học thuật:** Tăng cường nội dung giáo dục bằng biểu đồ tương tác.
3. **Phân tích tài chính:** Xuất dữ liệu tài chính sang Excel để phân tích chuyên sâu.
4. **Phân tích tiếp thị:** Trực quan hóa hiệu suất chiến dịch bằng biểu đồ động.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}