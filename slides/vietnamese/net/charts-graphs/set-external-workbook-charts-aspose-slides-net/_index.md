---
"date": "2025-04-15"
"description": "Tìm hiểu cách thiết lập biểu đồ với sổ làm việc Excel bên ngoài bằng Aspose.Slides cho .NET, nâng cao khả năng trình bày và quản lý dữ liệu của bạn."
"title": "Cách thiết lập sổ làm việc bên ngoài làm nguồn dữ liệu biểu đồ trong Aspose.Slides .NET"
"url": "/vi/net/charts-graphs/set-external-workbook-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách sử dụng Aspose.Slides .NET để thiết lập một sổ làm việc bên ngoài làm nguồn dữ liệu biểu đồ
## Giới thiệu
Tạo biểu đồ hấp dẫn trực quan trong các bài thuyết trình là rất quan trọng để truyền đạt hiệu quả các thông tin chi tiết dựa trên dữ liệu. Quản lý dữ liệu biểu đồ riêng biệt với các tệp thuyết trình có thể rất phức tạp. Với Aspose.Slides for .NET, bạn có thể liên kết một sổ làm việc bên ngoài làm nguồn dữ liệu cho biểu đồ của mình, hợp lý hóa quy trình làm việc và giữ cho dữ liệu của bạn được sắp xếp. Hướng dẫn này sẽ hướng dẫn bạn triển khai tính năng "Đặt dữ liệu biểu đồ từ sổ làm việc bên ngoài" bằng Aspose.Slides .NET.

**Những gì bạn sẽ học được:**
- Cách sử dụng Aspose.Slides cho .NET để thiết lập sổ làm việc bên ngoài làm nguồn dữ liệu cho biểu đồ.
- Các bước để thêm và cấu hình biểu đồ vào bản trình bày của bạn với dữ liệu bên ngoài.
- Tích hợp các tính năng của Aspose.Slides vào các dự án .NET của bạn.

Chúng ta hãy bắt đầu bằng cách thiết lập các điều kiện tiên quyết cần thiết.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập xong những điều sau:
### Thư viện bắt buộc
- **Aspose.Slides cho .NET**Thư viện này hỗ trợ tạo và thao tác các bài thuyết trình PowerPoint trong các ứng dụng .NET. Đảm bảo khả năng tương thích với môi trường phát triển của bạn.
### Yêu cầu thiết lập môi trường
- Môi trường phát triển AC# như Visual Studio.
- Một sổ làm việc bên ngoài (ví dụ: `externalWorkbook.xlsx`) chứa dữ liệu biểu đồ.
### Điều kiện tiên quyết về kiến thức
- Hiểu biết cơ bản về lập trình C# và các khái niệm về .NET framework.
- Quen thuộc với việc lập trình các bài thuyết trình trên PowerPoint.
## Thiết lập Aspose.Slides cho .NET
Để tích hợp Aspose.Slides vào dự án của bạn, hãy sử dụng một trong các phương pháp cài đặt sau:
**.NETCLI**
```bash
dotnet add package Aspose.Slides
```
**Trình quản lý gói**
```powershell
Install-Package Aspose.Slides
```
**Giao diện người dùng của Trình quản lý gói NuGet**
- Mở NuGet Package Manager trong IDE của bạn.
- Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.
### Mua lại giấy phép
Để sử dụng đầy đủ Aspose.Slides, bạn có thể cần phải có giấy phép. Sau đây là cách thực hiện:
- **Dùng thử miễn phí**:Bắt đầu với giấy phép tạm thời để khám phá tất cả các tính năng mà không có giới hạn.
- **Giấy phép tạm thời**: Nộp đơn trên trang web Aspose để đánh giá.
- **Mua**: Để sử dụng lâu dài, hãy mua gói đăng ký.
**Khởi tạo cơ bản:**
```csharp
// Khởi tạo giấy phép Aspose.Slides nếu bạn có
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```
## Hướng dẫn thực hiện
### Thiết lập sổ làm việc bên ngoài cho biểu đồ
Tính năng này cho phép bạn liên kết dữ liệu biểu đồ với sổ làm việc Excel bên ngoài, đảm bảo mọi cập nhật trong sổ làm việc đều tự động phản ánh trong bản trình bày của bạn.
#### Bước 1: Khởi tạo bài thuyết trình và thêm biểu đồ
Tạo một phiên bản trình bày mới và thêm biểu đồ hình tròn vào trang chiếu đầu tiên.
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public class Feature_SetExternalWorkbook {
    public static void Run() {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        using (Presentation pres = new Presentation()) {
            // Thêm biểu đồ hình tròn vào trang chiếu đầu tiên ở vị trí 50,50 với kích thước 400x600
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
```
#### Bước 2: Truy cập dữ liệu biểu đồ và thiết lập sổ làm việc bên ngoài
Truy cập bộ sưu tập dữ liệu biểu đồ để chỉ định sổ làm việc bên ngoài của bạn làm nguồn dữ liệu.
```csharp
            // Truy cập dữ liệu biểu đồ để thao tác.
            IChartData chartData = chart.ChartData;
            
            // Thiết lập sổ làm việc bên ngoài có chứa dữ liệu biểu đồ.
            chartData.SetExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```
#### Bước 3: Thêm Chuỗi và Điểm Dữ liệu từ Sổ làm việc Bên ngoài
Thêm một chuỗi mới vào biểu đồ của bạn, liên kết nó với các ô cụ thể trong sổ làm việc bên ngoài cho cả danh mục và giá trị.
```csharp
            // Thêm một chuỗi mới bằng cách sử dụng dữ liệu từ ô B1 trong sổ làm việc bên ngoài
            chartData.Series.Add(chartData.ChartDataWorkbook.GetCell(0, "B1"), ChartType.Pie);

            // Thêm các điểm dữ liệu cho chuỗi từ các ô B2, B3 và B4
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B2"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B3"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B4"));

            // Xác định danh mục cho chuỗi bằng cách sử dụng dữ liệu từ các ô A2, A3 và A4
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A2"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A3"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A4"));

            // Lưu bản trình bày với tên tệp đã chỉ định
            pres.Save(dataDir + "Presentation_with_externalWorkbook.pptx");
        }
    }
}
```
### Mẹo khắc phục sự cố
- Đảm bảo đường dẫn đến sổ làm việc bên ngoài là chính xác và có thể truy cập được.
- Xác minh rằng các tham chiếu ô trong mã của bạn khớp với các tham chiếu ô trong tệp Excel.
## Ứng dụng thực tế
Sau đây là một số trường hợp mà việc thiết lập sổ làm việc bên ngoài cho biểu đồ có thể cực kỳ hữu ích:
1. **Báo cáo tài chính**: Tự động cập nhật biểu đồ khi dữ liệu tài chính trong bảng tính thay đổi.
2. **Bảng điều khiển quản lý dự án**Liên kết số liệu tiến độ được lưu trữ trong các sổ làm việc riêng biệt với các trang trình bày.
3. **Phân tích tiếp thị**: Cập nhật các bài thuyết trình với dữ liệu hiệu suất chiến dịch mới nhất.
## Cân nhắc về hiệu suất
Khi làm việc với Aspose.Slides, hãy cân nhắc những mẹo sau để có hiệu suất tối ưu:
- Giảm thiểu các cuộc gọi sổ làm việc bên ngoài bằng cách tải trước dữ liệu cần thiết nếu có thể.
- Sử dụng các biện pháp quản lý bộ nhớ hiệu quả trong .NET để xử lý các bài thuyết trình lớn.
- Cập nhật thường xuyên thư viện Aspose.Slides của bạn để được hưởng lợi từ các bản tối ưu hóa và sửa lỗi.
## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách thiết lập sổ làm việc bên ngoài làm nguồn dữ liệu biểu đồ bằng Aspose.Slides cho .NET. Khả năng này nâng cao khả năng quản lý dữ liệu và đảm bảo rằng các bài thuyết trình của bạn luôn cập nhật với bất kỳ thay đổi dữ liệu cơ bản nào.
**Các bước tiếp theo:**
- Khám phá các tính năng bổ sung của Aspose.Slides để nâng cao hơn nữa bài thuyết trình của bạn.
- Thử nghiệm với nhiều loại biểu đồ và cấu hình dữ liệu khác nhau.
Chúng tôi khuyến khích bạn thử áp dụng các kỹ thuật này vào các dự án của mình. Để tìm hiểu thêm, hãy tìm hiểu sâu hơn [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/) hoặc khám phá diễn đàn của họ để được cộng đồng hỗ trợ.
## Phần Câu hỏi thường gặp
1. **Làm thế nào để liên kết một bảng tính ngoài đang nằm trên ổ đĩa mạng?**
   - Đảm bảo thiết lập đúng quyền và đường dẫn để truy cập từ môi trường ứng dụng của bạn.
2. **Tôi có thể cập nhật dữ liệu biểu đồ theo thời gian thực không?**
   - Mặc dù Aspose.Slides không hỗ trợ trực tiếp các bản cập nhật theo thời gian thực nhưng việc làm mới thường xuyên có thể mô phỏng hiệu ứng này.
3. **Có giới hạn số lượng sổ làm việc bên ngoài mà tôi có thể liên kết không?**
   - Không có giới hạn cố hữu nào, nhưng hiệu suất có thể thay đổi tùy theo khả năng của hệ thống và độ phức tạp của bảng tính.
4. **Tôi phải làm sao để khắc phục sự cố nếu biểu đồ của tôi không hiển thị dữ liệu chính xác?**
   - Kiểm tra tham chiếu ô trong mã của bạn để đảm bảo tính chính xác so với tệp Excel.
5. **Những định dạng nào được hỗ trợ cho sổ làm việc ngoài?**
   - Aspose.Slides chủ yếu hỗ trợ `.xlsx` các tệp, nhưng đảm bảo khả năng tương thích dựa trên cài đặt sổ làm việc cụ thể của bạn.
## Tài nguyên
- [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Tải xuống Aspose.Slides](https://releases.aspose.com/slides/net/)
- [Mua giấy phép Aspose.Slides](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí để đánh giá](https://releases.aspose.com/slides/net/)
- [Yêu cầu Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/slides/14)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}