---
title: 在演示文稿中执行邮件合并
linktitle: 在演示文稿中执行邮件合并
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 在本分步指南中学习如何使用 Aspose.Slides for .NET 在演示文稿中进行邮件合并。轻松创建动态、个性化的演示文稿。
weight: 21
url: /zh/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介绍
在 .NET 开发领域，创建动态和个性化的演示文稿是一项常见要求。一个可以简化此过程的强大工具是 Aspose.Slides for .NET。在本教程中，我们将深入探讨使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并的迷人领域。
## 先决条件
在我们踏上这一旅程之前，请确保您已满足以下先决条件：
- Aspose.Slides for .NET 库：确保已安装 Aspose.Slides for .NET 库。您可以从以下位置下载[这里](https://releases.aspose.com/slides/net/).
- 文档模板：准备一个演示模板（例如，PresentationTemplate.pptx），作为邮件合并的基础。
- 数据源：您需要一个数据源来进行邮件合并。在我们的示例中，我们将使用 XML 数据 (TestData.xml)，但 Aspose.Slides 支持各种数据源，如 RDBMS。
现在，让我们深入了解使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并的步骤。
## 导入命名空间
首先，确保您导入必要的命名空间以利用 Aspose.Slides 提供的功能：
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
## 步骤 1：设置文档目录
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
//检查结果路径是否存在
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 步骤 2：使用 XML 数据创建数据集
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 步骤 3：循环记录并创建单独的演示文稿
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    //创建结果（个人）演示名称
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    //加载演示模板
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        //使用主表中的数据填充文本框
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        //从数据库获取图像
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //将图像插入演示文稿的图片框中
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        //获取并准备文本框架以填充数据
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        //填写员工资料
        FillStaffList(textFrame, userRow, staffListTable);
        //填充计划事实数据
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## 步骤 4：使用列表形式填充文本框
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
## 步骤 5：从辅助 PlanFact 表填充数据图表
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
    //添加线系列的数据点
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
这些步骤展示了使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并的全面指南。现在，让我们来解决一些常见问题。
## 经常问的问题
### 1. Aspose.Slides for .NET 是否兼容不同的数据源？
是的，Aspose.Slides for .NET 支持各种数据源，包括 XML、RDBMS 等。
### 2. 我可以自定义生成的演示文稿中项目符号的外观吗？
当然！您可以完全控制项目符号的外观，如`FillStaffList`方法。
### 3. 我可以使用 Aspose.Slides for .NET 创建哪些类型的图表？
Aspose.Slides for .NET 支持各种图表，包括我们示例中所示的折线图、条形图、饼图等。
### 4. 如何获得 Aspose.Slides for .NET 的支持或寻求帮助？
如需支持和帮助，您可以访问[Aspose.Slides 论坛](https://forum.aspose.com/c/slides/11).
### 5. 购买之前我可以试用 Aspose.Slides for .NET 吗？
当然可以！您可以从以下网站免费试用 Aspose.Slides for .NET[这里](https://releases.aspose.com/).
## 结论
在本教程中，我们探索了 Aspose.Slides for .NET 在演示文稿中执行邮件合并的精彩功能。通过遵循分步指南，您可以轻松创建动态和个性化的演示文稿。使用 Aspose.Slides 提升您的 .NET 开发体验，实现无缝演示文稿生成。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
