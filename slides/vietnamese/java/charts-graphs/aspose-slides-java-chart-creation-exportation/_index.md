---
date: '2026-06-03'
description: Tìm hiểu cách xuất biểu đồ sang Excel và tạo biểu đồ Java bằng Aspose.Slides
  for Java. Nắm vững data visualization, business report slides, và workbook generation.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Xuất biểu đồ sang Excel và tạo biểu đồ với Aspose.Slides
url: /vi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Xuất biểu đồ sang Excel và tạo biểu đồ với Aspose.Slides

**Nắm vững các kỹ thuật trực quan hoá dữ liệu với Aspose.Slides cho Java**

Trong bối cảnh dữ liệu chi phối ngày nay, *export chart to excel* một cách lập trình là kỹ năng có thể biến các con số thô thành những câu chuyện hình ảnh hấp dẫn. Dù bạn đang xây dựng một bộ slide báo cáo kinh doanh hay một bảng điều khiển phân tích tương tác, Aspose.Slides cho Java cung cấp cho bạn khả năng tạo, tùy chỉnh và xuất biểu đồ trực tiếp từ mã của mình. Trong hướng dẫn này, bạn sẽ học cách tạo đối tượng biểu đồ, xuất dữ liệu biểu đồ sang Excel và liên kết biểu đồ với các workbook bên ngoài để quản lý dữ liệu một cách liền mạch.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Slides cho Java (v25.4+).  
- **Tôi có thể xuất dữ liệu biểu đồ sang Excel không?** Có – sử dụng `readWorkbookStream()` và ghi các byte vào tệp *.xlsx*.  
- **Phiên bản Java nào được yêu cầu?** JDK 16 hoặc cao hơn.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc đánh giá; giấy phép vĩnh viễn cần thiết cho môi trường sản xuất.  
- **Loại biểu đồ nào được trình bày?** Biểu đồ Pie, nhưng cùng một cách tiếp cận cũng hoạt động cho Bar, Line và các loại biểu đồ khác.

## Aspose.Slides cho Java là gì?
Aspose.Slides cho Java là một API thuần Java cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi các bản trình bày PowerPoint mà không cần Microsoft Office. Nó cung cấp một bộ lớp phong phú để thao tác slide, tạo biểu đồ và chuyển đổi định dạng, hỗ trợ giải pháp báo cáo tự động. Nó hỗ trợ **hơn 50 loại biểu đồ**, ràng buộc dữ liệu đầy đủ và xuất trực tiếp sang Excel, làm cho nó trở thành lựa chọn lý tưởng cho các dự án **data visualization java**.

## Tại sao nên sử dụng Aspose.Slides để tạo biểu đồ và xuất biểu đồ sang Excel?
Xuất biểu đồ sang Excel nhanh chóng và đáng tin cậy. Aspose.Slides loại bỏ nhu cầu cài đặt Office, cung cấp **hơn 50 kiểu biểu đồ tích hợp**, và xử lý các bản trình bày **lên tới 300 MB trong vòng dưới 30 giây** trên phần cứng máy chủ tiêu chuẩn. Bạn còn nhận được khả năng tạo workbook Excel gốc, cho phép các nhà phân tích downstream làm việc với dữ liệu thô mà không cần sao chép‑dán thủ công.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:

### Thư viện và phiên bản yêu cầu
- **Aspose.Slides cho Java** phiên bản 25.4 trở lên (hỗ trợ JDK 16+)

### Yêu cầu thiết lập môi trường
- Java Development Kit (JDK) 16 hoặc cao hơn  
- Một IDE như IntelliJ IDEA hoặc Eclipse (hoặc bất kỳ trình soạn thảo văn bản nào bạn thích)

### Kiến thức tiên quyết
- Kỹ năng lập trình Java cơ bản  
- Quen thuộc với công cụ xây dựng Maven hoặc Gradle

## Cài đặt Aspose.Slides cho Java
Thêm thư viện vào dự án của bạn bằng hệ thống build yêu thích.

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

### Các bước lấy giấy phép
Aspose.Slides cung cấp giấy phép dùng thử miễn phí để khám phá toàn bộ khả năng. Bạn cũng có thể đăng ký giấy phép tạm thời hoặc mua giấy phép cho việc sử dụng lâu dài. Thực hiện các bước sau:

1. Truy cập [trang mua Aspose](https://purchase.aspose.com/buy) để lấy giấy phép của bạn.  
2. Đối với bản dùng thử miễn phí, tải xuống từ [Releases](https://releases.aspose.com/slides/java/).  
3. Đăng ký giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

Khi đã có tệp giấy phép, khởi tạo nó trong ứng dụng Java của bạn:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Hướng dẫn từng bước

### Cách tạo biểu đồ – Tải một bản trình bày
Tải một tệp PowerPoint hiện có trước khi bạn có thể thêm hoặc chỉnh sửa biểu đồ.  
Lớp `Presentation` đại diện cho một tệp PowerPoint trong bộ nhớ, cung cấp các slide, shape và đối tượng biểu đồ.  
Tải tệp của bạn bằng `new Presentation("input.pptx")`, sau đó làm việc với slide đầu tiên bằng `presentation.getSlides().get_Item(0)`. Luôn gọi `presentation.dispose()` trong khối `finally` để giải phóng tài nguyên gốc.

### Cách tạo biểu đồ – Thêm biểu đồ Pie vào Slide
Chèn một biểu đồ Pie, phù hợp để hiển thị dữ liệu tỷ lệ phần trăm.  
Giao diện `IChart` là điểm vào chính để thao tác biểu đồ; `addChart` tạo một biểu đồ mới trên slide mục tiêu. Cung cấp loại biểu đồ (`ChartType.Pie`), tọa độ X/Y và chiều rộng/chiều cao. Sau khi tạo, bạn có thể tùy chỉnh tiêu đề, chú giải và chuỗi dữ liệu thông qua đối tượng `ChartData`.

### Cách xuất biểu đồ sang Excel – Xuất dữ liệu biểu đồ
Xuất dữ liệu biểu đồ cho phép các nhà phân tích làm việc với các con số trong Excel, tạo điều kiện cho việc khai thác sâu hơn.  
`readWorkbookStream()` trả về workbook Excel nền của biểu đồ dưới dạng mảng byte. Gọi `chart.getChartData().readWorkbookStream()` để lấy workbook và ghi mảng này vào tệp có tên `externalWorkbook1.xlsx` bằng I/O chuẩn của Java. Tệp Excel kết quả chứa chính xác dữ liệu được biểu đồ sử dụng, sẵn sàng cho phân tích tiếp theo.

### Cách tạo biểu đồ – Đặt Workbook bên ngoài cho dữ liệu động
Liên kết một biểu đồ với workbook bên ngoài để cho phép cập nhật dữ liệu trực tiếp mà không cần xây dựng lại slide.  
`setExternalWorkbook()` ràng buộc biểu đồ với tệp Excel bên ngoài để cập nhật dữ liệu động. Sử dụng `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` để liên kết biểu đồ với tệp bên ngoài. Khi workbook Excel được chỉnh sửa, biểu đồ sẽ tự động phản ánh các thay đổi lần tiếp theo khi mở bản trình bày, hỗ trợ các kịch bản báo cáo động.

## Ứng dụng thực tiễn
Aspose.Slides cung cấp các giải pháp đa dạng cho nhiều tình huống thực tế:

1. **Slide báo cáo kinh doanh:** Tự động tạo biểu đồ hiệu suất quý từ các pipeline dữ liệu của bạn.  
2. **Bài thuyết trình học thuật:** Biến dữ liệu nghiên cứu thành các hình ảnh trực quan mà không cần vẽ biểu đồ thủ công.  
3. **Phân tích tài chính:** Xuất dữ liệu biểu đồ sang Excel để kiểm toán viên xác minh số liệu, giảm lỗi thủ công.  
4. **Phân tích marketing:** Trực quan hoá các chỉ số chiến dịch và chia sẻ workbook có thể chỉnh sửa với các bên liên quan để ra quyết định hợp tác.  
5. **Tự động tạo Dashboard:** Kết hợp API tạo biểu đồ với các job lên lịch để tạo bộ slide cập nhật mỗi buổi sáng.

## Các vấn đề thường gặp & Khắc phục
- **`FileNotFoundException`** – Kiểm tra `dataDir` có trỏ tới thư mục hợp lệ và đường dẫn xuất có quyền ghi.  
- **Rò rỉ bộ nhớ** – Luôn gọi `presentation.dispose()` trong khối `finally` để giải phóng tài nguyên gốc.  
- **Biểu đồ không hiển thị** – Đảm bảo chỉ số slide (`get_Item(0)`) tồn tại và kích thước biểu đồ nằm trong giới hạn slide.  
- **Xuất Excel tạo ra tệp rỗng** – Xác nhận biểu đồ thực sự chứa chuỗi dữ liệu trước khi gọi `readWorkbookStream()`.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng loại biểu đồ khác (ví dụ: Bar, Line) với cùng một đoạn mã không?**  
A: Có. Thay `ChartType.Pie` bằng bất kỳ giá trị enum `ChartType` nào khác như `ChartType.Bar` hoặc `ChartType.Line`.

**Q: Có thể cập nhật workbook bên ngoài sau khi biểu đồ đã được tạo không?**  
A: Chắc chắn. Sửa trực tiếp tệp Excel; biểu đồ liên kết sẽ phản ánh các thay đổi lần tiếp theo khi mở bản trình bày.

**Q: Tôi có cần giấy phép riêng cho tính năng xuất Excel không?**  
A: Không. Khả năng xuất Excel đã được bao gồm trong giấy phép tiêu chuẩn của Aspose.Slides cho Java.

**Q: Các phiên bản Java nào được hỗ trợ?**  
A: Aspose.Slides cho Java hỗ trợ JDK 16 trở lên; các phiên bản cũ hơn có thể hoạt động nhưng không được kiểm tra chính thức.

**Q: Làm sao tôi có thể nhúng workbook Excel đã tạo vào trong tệp PPTX?**  
A: Sử dụng `chart.getChartData().setExternalWorkbook(null)` để nhúng workbook, hoặc giữ liên kết bên ngoài để cập nhật động.

---

**Cập nhật lần cuối:** 2026-06-03  
**Kiểm tra với:** Aspose.Slides cho Java 25.4 (JDK 16 classifier)  
**Tác giả:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Tạo biểu đồ trong Java với Aspose.Slides – Thêm & Xác thực Biểu đồ](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Khôi phục dữ liệu Workbook từ Biểu đồ PowerPoint bằng Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Cách cập nhật phạm vi dữ liệu biểu đồ PowerPoint bằng Aspose.Slides cho Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}