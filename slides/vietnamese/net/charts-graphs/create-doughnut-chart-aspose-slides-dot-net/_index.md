---
"date": "2025-04-15"
"description": "Tìm hiểu cách tạo và tùy chỉnh biểu đồ hình tròn dễ dàng trong bài thuyết trình PowerPoint bằng Aspose.Slides cho .NET. Nâng cao bài thuyết trình dữ liệu trực quan của bạn với hướng dẫn toàn diện này."
"title": "Cách tạo biểu đồ hình bánh rán trong PowerPoint bằng Aspose.Slides cho .NET&#58; Hướng dẫn từng bước"
"url": "/vi/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ hình bánh rán trong PowerPoint bằng Aspose.Slides cho .NET: Hướng dẫn từng bước

## Giới thiệu

Việc cải thiện bài thuyết trình PowerPoint của bạn bằng biểu đồ hình bánh rán hấp dẫn về mặt thị giác có thể cải thiện đáng kể cách bạn trình bày dữ liệu. Aspose.Slides for .NET cung cấp một cách hiệu quả để tạo và tùy chỉnh các biểu đồ này. Hướng dẫn này sẽ hướng dẫn bạn qua các bước sử dụng Aspose.Slides for .NET để thêm biểu đồ hình bánh rán có thể tùy chỉnh, bao gồm cả việc điều chỉnh kích thước lỗ, vào các slide PowerPoint của bạn.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho .NET
- Các bước để thêm biểu đồ hình tròn vào trang chiếu của bạn
- Các kỹ thuật để định hình kích thước lỗ của biểu đồ hình tròn của bạn
- Ứng dụng thực tế và cân nhắc hiệu suất

Hãy bắt đầu với những gì bạn cần trước khi bắt đầu nhé!

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đáp ứng các yêu cầu sau:

### Thư viện và phiên bản bắt buộc
- Aspose.Slides cho .NET (phiên bản mới nhất)
- Visual Studio hoặc bất kỳ IDE tương thích nào hỗ trợ phát triển .NET

### Yêu cầu thiết lập môi trường
- Môi trường Windows có cài đặt .NET Framework
- Kiến thức cơ bản về lập trình C#

## Thiết lập Aspose.Slides cho .NET

Để bắt đầu, bạn sẽ cần cài đặt thư viện Aspose.Slides. Sau đây là cách bạn có thể thực hiện bằng nhiều phương pháp khác nhau:

**Sử dụng .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Sử dụng Package Manager Console:**
```powershell
Install-Package Aspose.Slides
```

**Giao diện người dùng của Trình quản lý gói NuGet:**
Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất trực tiếp thông qua giao diện NuGet của IDE.

### Các bước xin cấp giấy phép
1. **Dùng thử miễn phí:** Bắt đầu bằng cách tải xuống bản dùng thử miễn phí để đánh giá các tính năng.
2. **Giấy phép tạm thời:** Nếu bạn cần thêm thời gian, hãy yêu cầu Aspose cấp giấy phép tạm thời.
3. **Mua:** Để sử dụng lâu dài, hãy cân nhắc mua phiên bản đầy đủ.

Sau khi cài đặt, hãy khởi tạo dự án của bạn bằng thiết lập cơ bản này:
```csharp
using Aspose.Slides;

// Khởi tạo một đối tượng Presentation mới
Presentation presentation = new Presentation();
```

## Hướng dẫn thực hiện

Chúng ta hãy chia nhỏ quy trình tạo biểu đồ hình tròn bằng Aspose.Slides cho .NET thành các bước dễ quản lý.

### Tạo biểu đồ hình bánh rán

#### Tổng quan
Chúng ta sẽ bắt đầu bằng cách thêm biểu đồ hình tròn vào trang chiếu PowerPoint của bạn, thiết lập vị trí và kích thước của biểu đồ.

**Thêm biểu đồ:**
```csharp
using Aspose.Slides.Charts;

// Truy cập trang chiếu đầu tiên trong bài thuyết trình (mặc định, trang chiếu này sẽ được tạo sẵn)
ISlide slide = presentation.Slides[0];

// Thêm biểu đồ hình tròn vào slide ở vị trí (50, 50) với chiều rộng và chiều cao là 400 đơn vị
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Các thông số:** `ChartType.Doughnut`, vị trí x: 50, vị trí y: 50, chiều rộng: 400, chiều cao: 400.

### Thiết lập kích thước lỗ

#### Tổng quan
Tiếp theo, chúng ta sẽ định cấu hình kích thước lỗ của biểu đồ hình tròn để làm cho nó hấp dẫn về mặt thị giác.

**Cấu hình kích thước lỗ:**
```csharp
// Đặt kích thước lỗ cho biểu đồ hình bánh rán thành 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Cấu hình khóa:** `DoughnutHoleSize` xác định mức độ "cắt bỏ" của phần trung tâm. Giá trị từ 0 đến 100 biểu thị phần trăm.

### Lưu bài thuyết trình của bạn

Cuối cùng, hãy lưu những thay đổi của bạn vào một tệp PowerPoint mới:
```csharp
// Xác định đường dẫn nơi bản trình bày sẽ được lưu
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Lưu bản trình bày đã sửa đổi ở định dạng PPTX
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Ghi chú:** Thay thế `YOUR_OUTPUT_DIRECTORY` với vị trí tập tin bạn mong muốn.

### Mẹo khắc phục sự cố

- Đảm bảo Aspose.Slides được cài đặt và nhập đúng cách.
- Xác minh xem đường dẫn thư mục đầu ra có tồn tại hay không trước khi lưu bản trình bày.

## Ứng dụng thực tế

Biểu đồ hình tròn được tạo bằng Aspose.Slides cho .NET có thể được sử dụng trong nhiều trường hợp khác nhau:

1. **Báo cáo kinh doanh:** Minh họa dữ liệu tài chính như phân bổ ngân sách hoặc phân phối doanh số.
2. **Phân tích tiếp thị:** Hiển thị phần trăm thị phần giữa các thương hiệu khác nhau.
3. **Tài liệu giáo dục:** Sử dụng để giải thích các khái niệm thống kê theo cách trực quan hấp dẫn.

Tích hợp Aspose.Slides với các hệ thống khác để tạo và phân phối báo cáo tự động trong môi trường doanh nghiệp.

## Cân nhắc về hiệu suất

Khi làm việc với các bài thuyết trình lớn hoặc nhiều biểu đồ, hãy cân nhắc những mẹo sau:

- Tối ưu hóa quá trình xử lý dữ liệu trước khi thêm vào slide.
- Sử dụng lại các đối tượng trình bày khi có thể để tiết kiệm bộ nhớ.
- Cập nhật thường xuyên thư viện Aspose.Slides của bạn để được hưởng lợi từ những cải tiến về hiệu suất.

## Phần kết luận

Bạn đã học cách tạo và tùy chỉnh biểu đồ hình tròn bằng Aspose.Slides cho .NET. Công cụ đa năng này tăng cường sức hấp dẫn trực quan cho bài thuyết trình của bạn, giúp dữ liệu dễ hiểu hơn chỉ trong nháy mắt.

**Các bước tiếp theo:**
Khám phá các loại biểu đồ khác có trong Aspose.Slides hoặc tìm hiểu sâu hơn về các tính năng nâng cao như hoạt ảnh.

Bạn đã sẵn sàng thử chưa? Hãy vào phần tài nguyên bên dưới và bắt đầu thử nghiệm nhé!

## Phần Câu hỏi thường gặp

1. **Aspose.Slides for .NET được sử dụng để làm gì?**  
   Đây là thư viện dùng để tạo, chỉnh sửa và chuyển đổi các bài thuyết trình PowerPoint theo chương trình.

2. **Làm thế nào để tôi có thể thay đổi màu sắc của các phần bánh rán?**  
   Sử dụng `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` để điều chỉnh thuộc tính tô.

3. **Tôi có thể tạo nhiều biểu đồ trong một bài thuyết trình không?**  
   Có, bạn có thể thêm nhiều biểu đồ tùy theo nhu cầu bằng cách lặp lại các bước tạo biểu đồ trên các slide hoặc vị trí khác nhau.

4. **Làm thế nào để tôi cấp phép Aspose.Slides cho .NET để sử dụng cho mục đích thương mại?**  
   Mua giấy phép thông qua trang web chính thức của Aspose để sử dụng cho mục đích thương mại.

5. **Tôi phải làm gì nếu bài thuyết trình của tôi không lưu đúng cách?**  
   Kiểm tra quyền truy cập đường dẫn tệp và đảm bảo tham chiếu dự án của bạn được cập nhật.

## Tài nguyên

- [Tài liệu Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Tải xuống Aspose.Slides cho .NET](https://releases.aspose.com/slides/net/)
- [Mua giấy phép](https://purchase.aspose.com/buy)
- [Phiên bản dùng thử miễn phí](https://releases.aspose.com/slides/net/)
- [Yêu cầu cấp giấy phép tạm thời](https://purchase.aspose.com/temporary-license/)
- [Diễn đàn hỗ trợ](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}