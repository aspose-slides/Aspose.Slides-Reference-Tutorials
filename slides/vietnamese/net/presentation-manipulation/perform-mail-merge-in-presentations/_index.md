---
title: Thực hiện trộn thư trong bài thuyết trình
linktitle: Thực hiện trộn thư trong bài thuyết trình
second_title: API xử lý Aspose.Slides .NET PowerPoint
description: Tìm hiểu cách phối thư trong bản trình bày bằng Aspose.Slides cho .NET trong hướng dẫn từng bước này. Tạo các bài thuyết trình năng động, được cá nhân hóa một cách dễ dàng.
type: docs
weight: 21
url: /vi/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## Giới thiệu
Trong thế giới phát triển .NET, việc tạo các bản trình bày năng động và được cá nhân hóa là một yêu cầu chung. Một công cụ mạnh mẽ giúp đơn giản hóa quá trình này là Aspose.Slides for .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào lĩnh vực thực hiện trộn thư hấp dẫn trong bản trình bày bằng Aspose.Slides cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu cuộc hành trình này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Aspose.Slides for .NET Library: Đảm bảo bạn đã cài đặt thư viện Aspose.Slides for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/slides/net/).
- Mẫu Tài liệu: Chuẩn bị một mẫu bản trình bày (ví dụ: Bản trình bàyTemplate.pptx) sẽ dùng làm cơ sở cho việc trộn thư.
- Nguồn dữ liệu: Bạn cần một nguồn dữ liệu để trộn thư. Trong ví dụ của chúng tôi, chúng tôi sẽ sử dụng dữ liệu XML (TestData.xml), nhưng Aspose.Slides hỗ trợ nhiều nguồn dữ liệu khác nhau như RDBMS.
Bây giờ, hãy đi sâu vào các bước thực hiện trộn thư trong bản trình bày bằng Aspose.Slides cho .NET.
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
## Bước 2: Tạo tập dữ liệu bằng dữ liệu XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Bước 3: Lặp lại các bản ghi và tạo bản trình bày riêng lẻ
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // tạo tên trình bày kết quả (cá nhân)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Tải mẫu thuyết trình
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Điền vào các hộp văn bản dữ liệu từ bảng chính
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Lấy hình ảnh từ cơ sở dữ liệu
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Chèn hình ảnh vào khung ảnh của bài thuyết trình
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Nhận và chuẩn bị khung văn bản để điền dữ liệu vào đó
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
## Bước 4: Điền dữ liệu vào khung văn bản dưới dạng danh sách
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
## Bước 5: Điền vào biểu đồ dữ liệu từ Bảng PlanFact thứ cấp
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
    // Thêm điểm dữ liệu cho chuỗi dòng
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
Các bước này thể hiện hướng dẫn toàn diện về cách thực hiện trộn thư trong bản trình bày bằng Aspose.Slides cho .NET. Bây giờ, hãy giải quyết một số câu hỏi thường gặp.
## Các câu hỏi thường gặp
### 1. Aspose.Slides cho .NET có tương thích với các nguồn dữ liệu khác nhau không?
Có, Aspose.Slides for .NET hỗ trợ nhiều nguồn dữ liệu khác nhau, bao gồm XML, RDBMS, v.v.
### 2. Tôi có thể tùy chỉnh hình thức của dấu đầu dòng trong bản trình bày được tạo không?
 Chắc chắn! Bạn có toàn quyền kiểm soát sự xuất hiện của các dấu đầu dòng, như được minh họa trong`FillStaffList` phương pháp.
### 3. Tôi có thể tạo những loại biểu đồ nào bằng Aspose.Slides cho .NET?
Aspose.Slides for .NET hỗ trợ nhiều loại biểu đồ, bao gồm biểu đồ dạng đường như trong ví dụ của chúng tôi, biểu đồ thanh, biểu đồ hình tròn, v.v.
### 4. Làm cách nào để nhận được hỗ trợ hoặc tìm kiếm trợ giúp với Aspose.Slides cho .NET?
 Để được hỗ trợ và trợ giúp, bạn có thể truy cập[Diễn đàn Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Tôi có thể dùng thử Aspose.Slides cho .NET trước khi mua không?
 Chắc chắn! Bạn có thể tận dụng bản dùng thử miễn phí Aspose.Slides cho .NET từ[đây](https://releases.aspose.com/).
## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá các khả năng thú vị của Aspose.Slides dành cho .NET trong việc thực hiện trộn thư trong bản trình bày. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng tạo các bản trình bày sinh động và được cá nhân hóa. Nâng cao trải nghiệm phát triển .NET của bạn với Aspose.Slides để tạo bản trình bày liền mạch.