---
title: 在演示文稿中执行邮件合并
linktitle: 在演示文稿中执行邮件合并
second_title: Aspose.Slides .NET PowerPoint 处理 API
description: 在此综合分步指南中了解如何使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并。轻松创建个性化的动态演示文稿。
type: docs
weight: 21
url: /zh/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

在软件开发领域，创建动态和个性化的演示文稿是一个常见的要求。企业通常需要生成针对特定数据定制的演示文稿，这就是邮件合并功能发挥作用的地方。在本教程中，我们将指导您完成使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并的过程。

## 介绍

邮件合并是一项功能强大的技术，允许您使用来自各种来源（例如数据库或 XML 文件）的数据填充演示模板。在本教程中，我们将重点介绍如何使用 Aspose.Slides for .NET 在演示文稿中逐步执行邮件合并。

## 设置您的环境

在我们深入研究邮件合并过程之前，您需要设置开发环境。确保您具备以下先决条件：

- Visual Studio 或任何其他 C# 开发环境。
- 安装了 Aspose.Slides for .NET 库。你可以下载它[这里](https://releases.aspose.com/slides/net/).

## 了解数据源

对于邮件合并，您需要一个数据源。在本教程中，我们将使用 XML 文件作为数据源。以下是您的数据源的外观示例：

```xml
<!-- TestData.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<MailMerge>
    <TestTable>
        <Id>1</Id>
        <Code>105</Code>
        <Name>Samuel Ellington</Name>
        <Department>Legal Department</Department> <Img></Img>
    </TestTable>
    <StaffList>
        <Id>18</Id>
        <UserId>1</UserId>
        <Name>Amelia Walker</Name>
    </StaffList>
    <Plan_Fact>
        <Id>1</Id>
        <UserId>1</UserId>
        <OnDate>2020/01</OnDate>
        <PlanData>2,0</PlanData>
        <FactData>2,8</FactData>
    </Plan_Fact>
</MailMerge>
```

## 创建演示模板

要执行邮件合并，您需要一个演示文稿模板（PPTX 文件）来定义最终演示文稿的布局。您可以使用 Microsoft PowerPoint 或您选择的任何其他工具创建此模板。

## 邮件合并过程

现在，让我们深入了解使用 Aspose.Slides for .NET 的实际邮件合并过程。我们将其分为几个步骤：

1. 加载演示模板。
2. 使用数据源中的数据填充文本框。
3. 将图像插入演示文稿中。
4. 准备并填充文本框。
5. 保存个人演示文稿。

下面是完成这些步骤的 C# 代码片段：

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    //数据的路径。
    // XML 数据是可能的 MailMerge 数据源（RDBMS 和其他类型的数据源中）的示例之一。
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    //检查结果路径是否存在
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    //使用 XML 数据创建 DataSet
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        //对于主表中的所有记录，我们将创建一个单独的演示文稿
        foreach (DataRow userRow in usersTable.Rows)
        {
            //创建结果（个人）演示文稿名称
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //加载演示模板
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                //使用数据库主表中的数据填充文本框
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                //从数据库中获取图像
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                //将图像插入演示文稿的相框
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                //获取 abd 准备文本框架以填充数据
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                //填写人员资料
                FillStaffList(textFrame, userRow, staffListTable);

                //填写计划事实数据
                FillPlanFact(pres, userRow, planFactTable);

                pres.Save(presPath, SaveFormat.Pptx);
            }
        }
    }

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

//从辅助 planFact 表中填充数据图表
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";

    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();

    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 1,
            double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2,
            double.Parse(selRows[0]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1,
            double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2,
            double.Parse(selRows[1]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[2]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[3]["FactData"].ToString())));

    chart.ChartData.SetRange(range);
}		
```

## 保存结果

完成数据源中所有记录的邮件合并过程后，您就可以准备好单独的演示文稿了。您可以将它们保存到您想要的位置。

## 结论

使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并为创建自定义和数据驱动的演示文稿打开了一个可能性的世界。本教程指导您完成无缝实现此目标的基本步骤。

## 常见问题解答

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
A1：虽然 Aspose.Slides for .NET 是一个强大的选择，但其他库和工具也提供类似的功能。这最终取决于您的具体要求和偏好。

**Q2: Can I use different data sources apart from XML files?**
A2：是的，Aspose.Slides for .NET 支持各种数据源，包括数据库和自定义数据结构。

**Q3: How can I format the merged presentations further?**
A3：您可以使用 Aspose.Slides 丰富的功能集将其他格式、样式和动画应用到合并的演示文稿中。

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 A4：是的，您可以免费试用 Aspose.Slides for .NET[这里](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 A5: 如需技术支持和讨论，您可以访问[Aspose.Slides 论坛](https://forum.aspose.com/).

现在您已经了解了如何使用 Aspose.Slides for .NET 在演示文稿中执行邮件合并，您可以开始为您的项目创建动态且数据丰富的演示文稿。快乐编码！
