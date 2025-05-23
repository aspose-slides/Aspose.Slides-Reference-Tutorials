---
"description": "Tìm hiểu cách trộn thư trong bài thuyết trình bằng Aspose.Slides cho .NET trong hướng dẫn từng bước này. Tạo bài thuyết trình năng động, được cá nhân hóa một cách dễ dàng."
"linktitle": "Thực hiện trộn thư trong bài thuyết trình"
"second_title": "API xử lý PowerPoint Aspose.Slides .NET"
"title": "Thực hiện trộn thư trong bài thuyết trình"
"url": "/vi/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Thực hiện trộn thư trong bài thuyết trình

## Giới thiệu
Trong thế giới phát triển .NET, việc tạo các bài thuyết trình năng động và được cá nhân hóa là một yêu cầu phổ biến. Một công cụ mạnh mẽ giúp đơn giản hóa quy trình này là Aspose.Slides for .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào lĩnh vực hấp dẫn của việc thực hiện trộn thư trong các bài thuyết trình bằng Aspose.Slides for .NET.
## Điều kiện tiên quyết
Trước khi bắt đầu hành trình này, hãy đảm bảo bạn đã đáp ứng đủ các điều kiện tiên quyết sau:
- Aspose.Slides cho Thư viện .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides cho .NET. Bạn có thể tải xuống từ [đây](https://releases.aspose.com/slides/net/).
- Mẫu tài liệu: Chuẩn bị mẫu trình bày (ví dụ: PresentationTemplate.pptx) dùng làm cơ sở cho việc trộn thư.
- Nguồn dữ liệu: Bạn cần một nguồn dữ liệu để trộn thư. Trong ví dụ của chúng tôi, chúng tôi sẽ sử dụng dữ liệu XML (TestData.xml), nhưng Aspose.Slides hỗ trợ nhiều nguồn dữ liệu khác nhau như RDBMS.
Bây giờ, chúng ta hãy cùng tìm hiểu các bước thực hiện trộn thư trong bài thuyết trình bằng Aspose.Slides cho .NET.
## Nhập không gian tên
Trước tiên, hãy đảm bảo bạn nhập các không gian tên cần thiết để tận dụng các chức năng do Aspose.Slides cung cấp:
```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Export;
using DataTable = System.Data.DataTable;
```
## Bước 1: Thiết lập thư mục tài liệu của bạn
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Kiểm tra xem đường dẫn kết quả có tồn tại không
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Bước 2: Tạo một DataSet bằng cách sử dụng dữ liệu XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Bước 3: Lặp qua các bản ghi và tạo các bài thuyết trình riêng lẻ
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // tạo kết quả (cá nhân) tên trình bày
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Tải mẫu trình bày
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Điền dữ liệu từ bảng chính vào hộp văn bản
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Lấy hình ảnh từ cơ sở dữ liệu
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Chèn hình ảnh vào khung hình của bài thuyết trình
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Nhận và chuẩn bị khung văn bản để điền dữ liệu vào
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Điền dữ liệu nhân viên
        FillStaffList(textFrame, userRow, staffListTable);
        // Điền dữ liệu thực tế kế hoạch
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Bước 4: Điền Khung Văn Bản với Dữ Liệu dưới dạng Danh Sách
```csharp
static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}
```
## Bước 5: Điền biểu đồ dữ liệu từ bảng PlanFact thứ cấp
```csharp
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";
    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();
    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;
    // Thêm điểm dữ liệu cho chuỗi đường
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries
(cellsFactory.GetCell(worksheetIndex, 1, 1, double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2, double.Parse(selRows[0]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1, double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2, double.Parse(selRows[1]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[2]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[3]["FactData"].ToString())));
    chart.ChartData.SetRange(range);
}
```
Các bước này trình bày hướng dẫn toàn diện về cách thực hiện trộn thư trong bài thuyết trình bằng Aspose.Slides cho .NET. Bây giờ, chúng ta hãy giải quyết một số câu hỏi thường gặp.
## Những câu hỏi thường gặp
### 1. Aspose.Slides cho .NET có tương thích với các nguồn dữ liệu khác nhau không?
Có, Aspose.Slides for .NET hỗ trợ nhiều nguồn dữ liệu khác nhau, bao gồm XML, RDBMS, v.v.
### 2. Tôi có thể tùy chỉnh giao diện của các dấu đầu dòng trong bản trình bày đã tạo không?
Chắc chắn rồi! Bạn có toàn quyền kiểm soát sự xuất hiện của các dấu đầu dòng, như đã trình bày trong `FillStaffList` phương pháp.
### 3. Tôi có thể tạo loại biểu đồ nào bằng Aspose.Slides cho .NET?
Aspose.Slides for .NET hỗ trợ nhiều loại biểu đồ, bao gồm biểu đồ đường như trong ví dụ của chúng tôi, biểu đồ thanh, biểu đồ hình tròn, v.v.
### 4. Làm thế nào để tôi nhận được hỗ trợ hoặc tìm kiếm trợ giúp với Aspose.Slides cho .NET?
Để được hỗ trợ và trợ giúp, bạn có thể truy cập [Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Tôi có thể dùng thử Aspose.Slides cho .NET trước khi mua không?
Chắc chắn rồi! Bạn có thể tận dụng bản dùng thử miễn phí Aspose.Slides cho .NET từ [đây](https://releases.aspose.com/).
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá các khả năng thú vị của Aspose.Slides cho .NET trong việc thực hiện trộn thư trong các bài thuyết trình. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng tạo các bài thuyết trình năng động và được cá nhân hóa. Nâng cao trải nghiệm phát triển .NET của bạn với Aspose.Slides để tạo bài thuyết trình liền mạch.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}