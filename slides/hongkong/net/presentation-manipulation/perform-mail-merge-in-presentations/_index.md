---
title: 在簡報中執行郵件合併
linktitle: 在簡報中執行郵件合併
second_title: Aspose.Slides .NET PowerPoint 處理 API
description: 在此逐步指南中了解如何使用 Aspose.Slides for .NET 在簡報中合併郵件。輕鬆建立動態、個人化的簡報。
weight: 21
url: /zh-hant/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在 .NET 開發領域，創建動態且個人化的簡報是一項常見要求。 Aspose.Slides for .NET 是簡化此流程的強大工具。在本教程中，我們將深入研究使用 Aspose.Slides for .NET 在簡報中執行郵件合併的迷人領域。
## 先決條件
在我們開始這趟旅程之前，請確保您具備以下先決條件：
- Aspose.Slides for .NET 函式庫：確保您已安裝 Aspose.Slides for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/slides/net/).
- 文件範本：準備一個示範範本（例如，PresentationTemplate.pptx），作為郵件合併的基礎。
- 資料來源：您需要一個用於郵件合併的資料來源。在我們的範例中，我們將使用 XML 資料 (TestData.xml)，但 Aspose.Slides 支援各種資料來源，例如 RDBMS。
現在，讓我們深入了解使用 Aspose.Slides for .NET 在簡報中執行郵件合併的步驟。
## 導入命名空間
首先，確保導入必要的命名空間以利用 Aspose.Slides 提供的功能：
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
## 第 1 步：設定您的文件目錄
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
//檢查結果路徑是否存在
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 步驟 2：使用 XML 資料建立資料集
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 步驟 3： 循環記錄並建立單獨的簡報
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    //建立結果（個人）示範名稱
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    //載入示範模板
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        //使用主表中的資料填充文字框
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        //從資料庫取得影像
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //將影像插入簡報的圖片框中
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        //取得並準備文字框架以填充數據
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        //填寫人員資料
        FillStaffList(textFrame, userRow, staffListTable);
        //填寫計劃事實數據
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## 步驟 4：用資料填充文字框架作為列表
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
## 步驟 5：從輔助 PlanFact 表填寫資料圖表
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
    //為線系列新增資料點
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
這些步驟示範了使用 Aspose.Slides for .NET 在簡報中執行郵件合併的綜合指南。現在，我們來解決一些常見問題。
## 經常問的問題
### 1. Aspose.Slides for .NET 是否相容於不同的資料來源？
是的，Aspose.Slides for .NET 支援各種資料來源，包括 XML、RDBMS 等。
### 2. 我可以自訂產生的簡報中項目符號的外觀嗎？
當然！您可以完全控制項目符號點的外觀，例如`FillStaffList`方法。
### 3. 我可以使用 Aspose.Slides for .NET 建立哪些類型的圖表？
Aspose.Slides for .NET 支援多種圖表，包括我們範例中所示的折線圖、長條圖、圓餅圖等。
### 4. 如何獲得 Aspose.Slides for .NET 的支援或尋求協助？
如需支援和協助，您可以訪問[Aspose.Slides 論壇](https://forum.aspose.com/c/slides/11).
### 5. 我可以在購買前試用 Aspose.Slides for .NET 嗎？
當然！您可以從以下位置免費試用 Aspose.Slides for .NET[這裡](https://releases.aspose.com/).
## 結論
在本教程中，我們探索了 Aspose.Slides for .NET 在簡報中執行郵件合併的令人興奮的功能。透過遵循逐步指南，您可以輕鬆建立動態且個人化的簡報。使用 Aspose.Slides 提升您的 .NET 開發體驗，實現無縫簡報產生。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
