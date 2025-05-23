---
"date": "2025-04-15"
"description": "Tìm hiểu cách tạo biểu đồ hình tròn động và hấp dẫn về mặt hình ảnh trong bài thuyết trình PowerPoint bằng thư viện Aspose.Slides for .NET mạnh mẽ."
"title": "Cách tạo biểu đồ hình bánh rán trong PowerPoint bằng Aspose.Slides cho .NET"
"url": "/vi/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cách tạo biểu đồ hình bánh rán trong PowerPoint bằng Aspose.Slides cho .NET
Tạo biểu đồ hấp dẫn trực quan là điều cần thiết để trình bày dữ liệu hiệu quả. Biểu đồ hình bánh rán hoàn hảo để minh họa các phần của tổng thể, khiến chúng trở nên lý tưởng để trực quan hóa dữ liệu dựa trên phần trăm. Hướng dẫn này sẽ hướng dẫn bạn cách tạo biểu đồ hình bánh rán động trong PowerPoint bằng thư viện Aspose.Slides for .NET mạnh mẽ.

## Giới thiệu
Các bài thuyết trình thường yêu cầu biểu diễn trực quan các tập dữ liệu phức tạp trong khi biểu đồ thanh hoặc biểu đồ đường truyền thống có thể không đáp ứng được. Biểu đồ hình tròn nổi lên như một công cụ đa năng để truyền đạt dữ liệu dựa trên phần trăm một cách hiệu quả với phong cách và sự rõ ràng. Trong hướng dẫn này, chúng ta sẽ khám phá cách Aspose.Slides for .NET đơn giản hóa quy trình tạo các biểu đồ này trực tiếp trong PowerPoint.

**Những gì bạn sẽ học được:**
- Thiết lập Aspose.Slides cho .NET
- Hướng dẫn từng bước để tạo biểu đồ hình tròn
- Thêm chuỗi và danh mục vào biểu đồ của bạn
- Cấu hình nhãn dữ liệu để tăng cường độ rõ ràng
- Lưu bản trình bày cuối cùng

Hãy cùng tìm hiểu cách bạn có thể tận dụng Aspose.Slides cho .NET để nâng cao bài thuyết trình của mình bằng biểu đồ hình tròn tùy chỉnh.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị những điều sau:
- **Aspose.Slides cho thư viện .NET**: Có sẵn thông qua NuGet hoặc tải xuống trực tiếp.
- **Môi trường phát triển**Visual Studio được khuyến nghị cho các dự án .NET.
- Kiến thức cơ bản về C# và quen thuộc với cấu trúc của PowerPoint.

## Thiết lập Aspose.Slides cho .NET
Để bắt đầu tạo biểu đồ, trước tiên bạn cần thiết lập thư viện Aspose.Slides trong dự án của mình. Sau đây là một số cách để cài đặt:

**Sử dụng .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Sử dụng Package Manager Console:**

```powershell
Install-Package Aspose.Slides
```

**Thông qua Giao diện người dùng của Trình quản lý gói NuGet:**
Tìm kiếm "Aspose.Slides" và cài đặt phiên bản mới nhất.

Sau khi cài đặt, bạn có thể bắt đầu thiết lập dự án của mình. Nếu bạn mới sử dụng Aspose.Slides, hãy cân nhắc việc lấy giấy phép tạm thời hoặc dùng thử miễn phí để khám phá toàn bộ khả năng của nó mà không có giới hạn.

### Khởi tạo dự án của bạn
Sau đây là cách bạn có thể khởi tạo Aspose.Slides trong ứng dụng của mình:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Tạo một thể hiện của lớp Presentation
        Presentation presentation = new Presentation();
        
        // Mã của bạn để thao tác trình bày ở đây
        
        // Lưu bài thuyết trình
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Hướng dẫn thực hiện
### Tạo biểu đồ hình bánh rán
#### Tổng quan
Đầu tiên, chúng ta sẽ tạo một biểu đồ hình tròn rỗng trong slide PowerPoint. Đây là nền tảng để thêm dữ liệu và tùy chỉnh giao diện của dữ liệu.

**Bước 1: Thêm biểu đồ hình tròn**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Thêm biểu đồ hình tròn vào trang chiếu đầu tiên ở vị trí (10, 10) với kích thước (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Xóa các chuỗi và danh mục hiện có
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Tắt chú giải để có giao diện sạch hơn
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Giải thích:**
- **thêmBiểu đồ**: Chèn biểu đồ hình tròn mới vào trang chiếu.
- **lấyChartDataWorkbook**: Cung cấp quyền truy cập vào các ô dữ liệu trong biểu đồ để thao tác.

### Thêm Series và Categories
#### Tổng quan
Tiếp theo, chúng tôi sẽ điền dữ liệu có ý nghĩa vào biểu đồ của bạn bằng cách thêm chuỗi và danh mục.

**Bước 2: Thêm Chuỗi Dữ liệu**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Thêm loạt bài
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Tùy chỉnh lỗ bánh rán và góc bắt đầu
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Thêm danh mục
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Định dạng phần tô và đường của điểm dữ liệu
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Giải thích:**
- **thêm vào**: Chèn chuỗi và danh mục mới vào biểu đồ.
- **thiết lậpDoughnutHoleSize**Cấu hình kích thước của lỗ bánh rán, tăng cường tính hấp dẫn về mặt thị giác.

### Cấu hình nhãn dữ liệu
#### Tổng quan
Nhãn dữ liệu cung cấp ngữ cảnh cho dữ liệu biểu đồ của bạn. Hãy nâng cao khả năng đọc bằng cách tùy chỉnh chúng.

**Bước 3: Tùy chỉnh nhãn dữ liệu**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Tùy chỉnh nhãn dữ liệu
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Giải thích:**
- **Nhãn IData**: Tùy chỉnh nhãn dữ liệu để rõ ràng và trình bày hơn.
- **thiết lậpCenterText**, **Hiển thị phần trăm**: Cải thiện khả năng đọc nhãn bằng cách căn giữa văn bản và hiển thị phần trăm.

## Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách tạo biểu đồ hình bánh rán động trong PowerPoint bằng Aspose.Slides for .NET. Thư viện mạnh mẽ này cho phép tùy chỉnh rộng rãi, cho phép bạn điều chỉnh biểu đồ chính xác theo nhu cầu trình bày của mình.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}