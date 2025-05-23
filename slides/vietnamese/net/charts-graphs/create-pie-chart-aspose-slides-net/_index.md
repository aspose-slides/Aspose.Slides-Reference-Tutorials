---
"date": "2025-04-15"
"description": "Tìm hiểu cách thêm biểu đồ hình tròn vào bài thuyết trình của bạn theo chương trình với Aspose.Slides cho .NET, giúp tăng cường khả năng trực quan hóa dữ liệu một cách dễ dàng."
"title": "Tạo biểu đồ hình tròn trong PowerPoint bằng Aspose.Slides cho .NET"
"url": "/vi/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và thêm biểu đồ hình tròn vào bài thuyết trình bằng Aspose.Slides cho .NET
## Giới thiệu
Việc tạo ra các bài thuyết trình hấp dẫn thường liên quan đến nhiều thứ hơn là chỉ văn bản; các yếu tố trực quan như biểu đồ có thể tăng cường đáng kể tác động của việc kể chuyện dữ liệu của bạn. Nếu bạn đang muốn thêm biểu đồ hình tròn động vào bài thuyết trình PowerPoint của mình theo chương trình, **Aspose.Slides cho .NET** là một công cụ mạnh mẽ giúp cho nhiệm vụ này trở nên liền mạch và hiệu quả. Hướng dẫn này sẽ hướng dẫn bạn cách thêm biểu đồ hình tròn vào slide thuyết trình và cấu hình nó với các nguồn dữ liệu bên ngoài.

### Những gì bạn sẽ học được
- Cách tạo bài thuyết trình mới bằng Aspose.Slides cho .NET
- Thêm biểu đồ hình tròn vào trang chiếu đầu tiên của bạn
- Đặt URL sổ làm việc bên ngoài làm nguồn dữ liệu cho biểu đồ của bạn
- Lưu bài thuyết trình của bạn ở định dạng PPTX
Hãy cùng tìm hiểu cách bạn có thể dễ dàng đạt được điều này bằng cách bắt đầu với các điều kiện tiên quyết.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị những thứ sau:
- **Aspose.Slides cho .NET** thư viện đã cài đặt. Bạn sẽ cần phiên bản tương thích với .NET Framework hoặc .NET Core/.NET 5+.
- Kiến thức cơ bản về lập trình C# và quen thuộc với Visual Studio IDE.
- Môi trường phát triển được thiết lập trên máy của bạn (Windows, macOS hoặc Linux).
## Thiết lập Aspose.Slides cho .NET
### Hướng dẫn cài đặt
Aspose.Slides cho .NET có thể được thêm vào dự án của bạn bằng nhiều phương pháp khác nhau:
**.NETCLI**
```shell
dotnet add package Aspose.Slides
```
**Bảng điều khiển quản lý gói**
```powershell
Install-Package Aspose.Slides
```
**Giao diện người dùng của Trình quản lý gói NuGet**
1. Mở Trình quản lý gói NuGet trong Visual Studio.
2. Tìm kiếm "Aspose.Slides".
3. Cài đặt phiên bản mới nhất.
### Mua lại giấy phép
Để sử dụng Aspose.Slides, bạn có thể bắt đầu bằng giấy phép dùng thử miễn phí để khám phá các tính năng của nó mà không có giới hạn. Đối với môi trường sản xuất, hãy cân nhắc mua giấy phép thương mại hoặc lấy giấy phép tạm thời để thử nghiệm mở rộng. Truy cập [Trang mua hàng của Aspose](https://purchase.aspose.com/buy) để biết thêm chi tiết.
### Khởi tạo cơ bản
Để sử dụng Aspose.Slides trong dự án của bạn, bạn cần khởi tạo nó bằng giấy phép nếu có:
```csharp
// Khởi tạo thư viện
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Hướng dẫn thực hiện
Bây giờ bạn đã thiết lập xong, chúng ta hãy cùng tìm hiểu từng tính năng theo từng bước.
### Tạo và Thêm Biểu đồ vào Bài thuyết trình
#### Tổng quan
Chúng ta sẽ bắt đầu bằng cách tạo một bài thuyết trình và thêm biểu đồ hình tròn vào trang chiếu đầu tiên.
#### Các bước thực hiện:
1. **Khởi tạo bài trình bày**
   Bắt đầu bằng cách tạo một phiên bản của `Presentation` lớp đại diện cho tệp PowerPoint của bạn.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Đây là nơi chúng ta sẽ thêm biểu đồ.
   }
   ```
2. **Thêm biểu đồ hình tròn**
   Sử dụng `Shapes.AddChart` phương pháp chèn biểu đồ hình tròn tại các tọa độ cụ thể trên trang chiếu của bạn.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Thiết lập sổ làm việc bên ngoài cho dữ liệu biểu đồ
#### Tổng quan
Bây giờ chúng ta hãy cấu hình biểu đồ hình tròn để sử dụng dữ liệu từ một bảng tính bên ngoài.
#### Các bước thực hiện:
1. **Truy cập dữ liệu biểu đồ**
   Truy xuất giao diện dữ liệu biểu đồ nơi bạn sẽ chỉ định URL nguồn dữ liệu bên ngoài.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Đặt URL Sổ làm việc bên ngoài**
   Đặt URL cho nguồn dữ liệu của bạn bằng cách sử dụng `SetExternalWorkbook`. Ví dụ này sử dụng URL giữ chỗ, cần được thay thế bằng đường dẫn nguồn dữ liệu thực tế của bạn.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://đường dẫn/không/tồn tại", sai);
   ```
### Lưu bài thuyết trình vào tệp
#### Tổng quan
Cuối cùng, lưu bản trình bày ở định dạng PPTX vào vị trí bạn mong muốn.
#### Các bước thực hiện:
1. **Lưu bài thuyết trình**
   Sử dụng `Save` phương pháp của `Presentation` lớp để ghi tập tin vào đĩa.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Ứng dụng thực tế
- **Báo cáo kinh doanh**: Tự động tạo biểu đồ để đánh giá hiệu suất hàng quý.
- **Bảng dữ liệu**: Tích hợp với các nguồn dữ liệu để cập nhật báo cáo trực quan theo thời gian thực.
- **Nội dung giáo dục**: Tạo các bài thuyết trình năng động lấy dữ liệu mới nhất từ các nghiên cứu hoặc bài báo khoa học bên ngoài.
Bằng cách tích hợp Aspose.Slides, bạn có thể tự động hóa và nâng cao quy trình tạo bài thuyết trình trên nhiều miền khác nhau.
## Cân nhắc về hiệu suất
Khi làm việc với các tập dữ liệu lớn hoặc nhiều biểu đồ:
- Tối ưu hóa việc sử dụng tài nguyên bằng cách quản lý bộ nhớ hiệu quả trong .NET.
- Xử lý `Presentation` các đối tượng để giải phóng tài nguyên một cách hợp lý.
- Sử dụng các hoạt động không đồng bộ khi có thể để cải thiện khả năng phản hồi của ứng dụng.
## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách lập trình tạo bản trình bày với biểu đồ hình tròn bằng Aspose.Slides for .NET. Bây giờ bạn có các công cụ để tự động tạo biểu đồ và quản lý các nguồn dữ liệu bên ngoài một cách hiệu quả.
### Các bước tiếp theo
Khám phá thêm bằng cách tùy chỉnh kiểu biểu đồ, thêm nhiều loại biểu đồ hơn hoặc tích hợp các thành phần Aspose khác như Aspose.Cells để nâng cao khả năng xử lý dữ liệu.
## Phần Câu hỏi thường gặp
1. **Aspose.Slides là gì?**  
   Một thư viện mạnh mẽ để thao tác các bài thuyết trình PowerPoint theo chương trình trong .NET.
2. **Tôi có thể sử dụng Aspose.Slides mà không cần giấy phép không?**  
   Có, nhưng có giới hạn. Hãy cân nhắc dùng thử miễn phí hoặc mua giấy phép để có đầy đủ tính năng.
3. **Làm thế nào để cập nhật dữ liệu biểu đồ một cách linh hoạt?**  
   Sử dụng sổ làm việc bên ngoài và đặt URL của chúng trong `SetExternalWorkbook` phương pháp.
4. **Aspose.Slides có thể sử dụng trên nhiều nền tảng không?**  
   Có, nó hỗ trợ .NET Framework và .NET Core/.NET 5+ trên Windows, macOS và Linux.
5. **Những loại biểu đồ nào khác được hỗ trợ?**  
   Ngoài biểu đồ hình tròn, bạn có thể tạo biểu đồ thanh, biểu đồ đường và nhiều biểu đồ khác bằng Aspose.Slides.
## Tài nguyên
- [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Tải xuống phiên bản mới nhất](https://releases.aspose.com/slides/net/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Dùng thử miễn phí](https://releases.aspose.com/slides/net/)
- [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11)
Hãy bắt đầu tích hợp Aspose.Slides vào dự án của bạn ngay hôm nay để nâng cao và tự động hóa các bài thuyết trình PowerPoint của bạn!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}