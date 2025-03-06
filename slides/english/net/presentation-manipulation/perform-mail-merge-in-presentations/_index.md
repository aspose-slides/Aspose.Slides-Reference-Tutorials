---
title: Perform Mail Merge in Presentations
linktitle: Perform Mail Merge in Presentations
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Learn mail merge in presentations using Aspose.Slides for .NET in this step-by-step guide. Create dynamic, personalized presentations effortlessly.
weight: 21
url: /net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Perform Mail Merge in Presentations

## Introduction
In the world of .NET development, creating dynamic and personalized presentations is a common requirement. One powerful tool that simplifies this process is Aspose.Slides for .NET. In this tutorial, we'll delve into the fascinating realm of performing mail merge in presentations using Aspose.Slides for .NET.
## Prerequisites
Before we embark on this journey, make sure you have the following prerequisites in place:
- Aspose.Slides for .NET Library: Ensure you have the Aspose.Slides for .NET library installed. You can download it from [here](https://releases.aspose.com/slides/net/).
- Document Template: Prepare a presentation template (e.g., PresentationTemplate.pptx) that will serve as the base for mail merge.
- Data Source: You need a data source for mail merge. In our example, we'll use XML data (TestData.xml), but Aspose.Slides supports various data sources like RDBMS.
Now, let's dive into the steps of performing mail merge in presentations using Aspose.Slides for .NET.
## Import Namespaces
Firstly, ensure you import the necessary namespaces to leverage the functionalities provided by Aspose.Slides:
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
## Step 1: Set Up Your Document Directory
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Check if result path exists
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Step 2: Create a DataSet Using XML Data
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Step 3: Loop Through Records and Create Individual Presentations
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // create result (individual) presentation name
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Load presentation template
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Fill text boxes with data from the main table
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Get image from the database
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Insert image into the picture frame of the presentation
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Get and prepare the text frame for filling it with data
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Fill staff data
        FillStaffList(textFrame, userRow, staffListTable);
        // Fill plan fact data
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Step 4: Fill Text Frame with Data as a List
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
## Step 5: Fill Data Chart from the Secondary PlanFact Table
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
    // Add data points for line series
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
These steps demonstrate a comprehensive guide on performing mail merge in presentations using Aspose.Slides for .NET. Now, let's address some frequently asked questions.
## Frequently Asked Questions
### 1. Is Aspose.Slides for .NET compatible with different data sources?
Yes, Aspose.Slides for .NET supports various data sources, including XML, RDBMS, and more.
### 2. Can I customize the appearance of bullet points in the generated presentation?
Certainly! You have full control over the appearance of bullet points, as demonstrated in the `FillStaffList` method.
### 3. What types of charts can I create using Aspose.Slides for .NET?
Aspose.Slides for .NET supports a wide range of charts, including line charts as shown in our example, bar charts, pie charts, and more.
### 4. How do I get support or seek assistance with Aspose.Slides for .NET?
For support and assistance, you can visit the [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 5. Can I try Aspose.Slides for .NET before purchasing?
Certainly! You can avail of a free trial of Aspose.Slides for .NET from [here](https://releases.aspose.com/).
## Conclusion
In this tutorial, we explored the exciting capabilities of Aspose.Slides for .NET in performing mail merge in presentations. By following the step-by-step guide, you can create dynamic and personalized presentations effortlessly. Elevate your .NET development experience with Aspose.Slides for seamless presentation generation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
