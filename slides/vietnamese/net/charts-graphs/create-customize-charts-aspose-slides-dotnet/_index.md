---
"date": "2025-04-15"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ bằng Aspose.Slides cho .NET, bao gồm hiển thị phần trăm dưới dạng nhãn dữ liệu. Làm theo hướng dẫn từng bước này."
"title": "Cách tạo và tùy chỉnh biểu đồ với Aspose.Slides .NET&#58; Hiển thị phần trăm dưới dạng nhãn"
"url": "/vi/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo và tùy chỉnh biểu đồ với Aspose.Slides .NET: Hiển thị phần trăm dưới dạng nhãn

## Giới thiệu

Trình bày dữ liệu hiệu quả là rất quan trọng trong nhiều lĩnh vực và biểu đồ đóng vai trò quan trọng bằng cách biến thông tin phức tạp thành hình ảnh trực quan rõ ràng. Việc tạo biểu đồ hoàn hảo liên quan đến các tác vụ tùy chỉnh như hiển thị phần trăm trên nhãn—một tác vụ dễ dàng hơn với Aspose.Slides for .NET. Thư viện này đơn giản hóa quy trình tạo và sửa đổi biểu đồ trong bản trình bày PowerPoint.

Trong hướng dẫn này, bạn sẽ học cách sử dụng Aspose.Slides for .NET để tạo biểu đồ cột xếp chồng từ đầu và tùy chỉnh bằng cách hiển thị giá trị phần trăm dưới dạng nhãn dữ liệu. Bằng cách làm theo các bước này, bạn sẽ cải thiện các slide của mình bằng các biểu diễn dữ liệu chính xác và hấp dẫn về mặt trực quan.

**Những gì bạn sẽ học được:**
- Khởi tạo Aspose.Slides cho .NET
- Tạo biểu đồ cột xếp chồng
- Tính toán và hiển thị phần trăm trên nhãn dữ liệu
- Tối ưu hóa hiệu suất biểu đồ thực hành tốt nhất

Trước khi bắt đầu triển khai, hãy đảm bảo bạn đã sẵn sàng mọi thứ để bắt đầu.

## Điều kiện tiên quyết

Để thực hiện hướng dẫn này một cách hiệu quả, hãy đảm bảo rằng bạn có:
- **Bộ công cụ phát triển .NET Core** được cài đặt trên máy của bạn.
- Hiểu biết cơ bản về phát triển ứng dụng C# và .NET.
- Visual Studio hoặc IDE tương tự để viết và chạy mã C#.

Bạn sẽ cần Aspose.Slides cho .NET để tạo biểu đồ, vì vậy hãy đảm bảo thiết lập như mô tả bên dưới.

## Thiết lập Aspose.Slides cho .NET

Aspose.Slides for .NET là một thư viện mạnh mẽ cho phép bạn làm việc với các bài thuyết trình PowerPoint theo chương trình. Sau đây là cách thêm nó vào dự án của bạn:

### Cài đặt

**.NETCLI:**
```bash
dotnet add package Aspose.Slides
```

**Bảng điều khiển quản lý gói:**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet:** 
- Mở NuGet Package Manager và tìm kiếm "Aspose.Slides". Cài đặt phiên bản mới nhất.

### Mua lại giấy phép

Để sử dụng Aspose.Slides đầy đủ, hãy bắt đầu bằng bản dùng thử miễn phí. Để sử dụng lâu dài, hãy cân nhắc mua giấy phép tạm thời hoặc mua giấy phép từ [Đặt ra](https://purchase.aspose.com/buy). Thực hiện theo hướng dẫn của họ để thiết lập giấy phép trong môi trường dự án của bạn.

### Khởi tạo cơ bản

Sau khi cài đặt, khởi tạo `Presentation` lớp học để bắt đầu tạo slide:
```csharp
using Aspose.Slides;

// Khởi tạo thể hiện lớp Presentation
tPresentation presentation = new Presentation();
```

Bây giờ, chúng ta hãy chuyển sang triển khai tính năng tạo và tùy chỉnh biểu đồ bằng Aspose.Slides cho .NET.

## Hướng dẫn thực hiện

### Tạo biểu đồ cột xếp chồng

Mục tiêu của chúng tôi là tạo biểu đồ cột xếp chồng và tùy chỉnh biểu đồ bằng cách hiển thị phần trăm dưới dạng nhãn dữ liệu. Sau đây là cách thực hiện:

#### Khởi tạo bài trình bày

Bắt đầu bằng cách tạo một phiên bản của `Presentation`:
```csharp
using Aspose.Slides;

// Khởi tạo thể hiện lớp Presentation
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Thêm biểu đồ vào trang chiếu

Thêm biểu đồ cột xếp chồng vào trang chiếu đầu tiên của bạn theo tọa độ và kích thước đã chỉ định:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Dòng này tạo ra một `StackedColumn` biểu đồ ở vị trí (20, 20) có chiều rộng và chiều cao là 400.

#### Tính tổng giá trị cho phép tính phần trăm

Để hiển thị phần trăm, hãy tính tổng giá trị cho từng danh mục trong toàn bộ chuỗi:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Tổng hợp các giá trị của tất cả các chuỗi cho mỗi danh mục
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Tùy chỉnh nhãn dữ liệu để hiển thị giá trị phần trăm

Tiếp theo, lặp lại từng chuỗi và tùy chỉnh nhãn dữ liệu:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Tính phần trăm
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Xóa văn bản để tránh chồng chéo
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Cấu hình định dạng nhãn để ẩn nhãn dữ liệu mặc định
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Phần này tính toán phần trăm cho mỗi điểm dữ liệu và đặt thành nhãn tùy chỉnh, đảm bảo không trùng lặp với nhãn mặc định.

#### Lưu bài thuyết trình

Cuối cùng, hãy lưu bài thuyết trình của bạn để xem kết quả:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Ứng dụng thực tế

Việc hiển thị phần trăm trong biểu đồ có thể đặc biệt hữu ích trong các trường hợp như:
1. **Báo cáo tài chính:** Hiển thị phân bổ danh mục đầu tư hoặc lợi nhuận đầu tư dưới dạng phần trăm.
2. **Phân tích bán hàng:** Biểu thị dữ liệu thị phần theo phần trăm để làm nổi bật hiệu suất trên khắp các khu vực.
3. **Kết quả khảo sát:** Hiển thị phản hồi khảo sát dưới dạng phần trăm để so sánh trực quan tốt hơn.
4. **Quản lý dự án:** Sử dụng biểu đồ hình tròn có phần trăm để minh họa việc phân bổ nguồn lực.
5. **Giáo dục:** Giải thích các khái niệm thống kê bằng hình ảnh minh họa rõ ràng theo tỷ lệ phần trăm.

Việc tích hợp các biểu đồ tùy chỉnh này vào các hệ thống như CRM hoặc ERP có thể cải thiện bảng thông tin và báo cáo, hỗ trợ quá trình ra quyết định.

## Cân nhắc về hiệu suất

Khi làm việc với Aspose.Slides cho .NET, đặc biệt là với các tập dữ liệu lớn:
- **Quản lý bộ nhớ:** Xử lý các đối tượng trình bày đúng cách để giải phóng bộ nhớ. Sử dụng `using` các tuyên bố khi áp dụng.
- **Xử lý dữ liệu hiệu quả:** Thực hiện các phép tính bên ngoài vòng lặp khi có thể để giảm chi phí tính toán.
- **Cân bằng tải:** Đối với các ứng dụng web, hãy đảm bảo tài nguyên máy chủ được cung cấp đầy đủ cho các yêu cầu tạo biểu đồ đồng thời.

## Phần kết luận

Hướng dẫn này bao gồm việc tạo và tùy chỉnh biểu đồ bằng Aspose.Slides cho .NET bằng cách hiển thị các giá trị phần trăm dưới dạng nhãn. Việc thành thạo các kỹ thuật này cho phép bạn nâng cao bài thuyết trình của mình bằng các biểu diễn dữ liệu chi tiết và hấp dẫn về mặt trực quan.

Bước tiếp theo, hãy khám phá các loại biểu đồ và tùy chọn tùy chỉnh khác có trong Aspose.Slides. Thử nghiệm với các tập dữ liệu khác nhau để biến chúng thành hình ảnh trực quan mạnh mẽ truyền đạt thông tin chi tiết một cách rõ ràng.

## Phần Câu hỏi thường gặp

**Câu hỏi 1: Làm thế nào để xử lý các tập dữ liệu lớn khi tạo biểu đồ bằng Aspose.Slides cho .NET?**
A1: Đối với các tập dữ liệu lớn, hãy tối ưu hóa các phép tính và sử dụng các kỹ thuật quản lý bộ nhớ hiệu quả. Chia nhỏ các tác vụ xử lý để tránh quá tải bộ nhớ.

**Câu hỏi 2: Tôi có thể sử dụng Aspose.Slides cho .NET trong ứng dụng web không?**
A2: Có, có thể tích hợp vào các ứng dụng ASP.NET. Đảm bảo phân bổ tài nguyên máy chủ phù hợp để có hiệu suất tối ưu.

**Câu hỏi 3: Có thể xuất biểu đồ được tạo bằng Aspose.Slides sang các định dạng khác không?**
A3: Hoàn toàn được! Bạn có thể xuất các bài thuyết trình có chứa biểu đồ tùy chỉnh của mình sang nhiều định dạng khác nhau như PDF và tệp hình ảnh bằng các chức năng của thư viện.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}