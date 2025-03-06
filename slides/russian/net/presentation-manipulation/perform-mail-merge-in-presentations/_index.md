---
title: Выполнение слияния почты в презентациях
linktitle: Выполнение слияния почты в презентациях
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Изучите слияние почты в презентациях с помощью Aspose.Slides для .NET в этом пошаговом руководстве. Создавайте динамичные персонализированные презентации без особых усилий.
weight: 21
url: /ru/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Введение
В мире .NET-разработки создание динамических и персонализированных презентаций является обычным требованием. Одним из мощных инструментов, упрощающих этот процесс, является Aspose.Slides для .NET. В этом уроке мы углубимся в увлекательную область выполнения слияния почты в презентациях с использованием Aspose.Slides для .NET.
## Предварительные условия
Прежде чем мы отправимся в это путешествие, убедитесь, что у вас есть следующие предпосылки:
- Библиотека Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).
- Шаблон документа: подготовьте шаблон презентации (например, PresentationTemplate.pptx), который будет служить основой для слияния почты.
- Источник данных: вам нужен источник данных для слияния почты. В нашем примере мы будем использовать данные XML (TestData.xml), но Aspose.Slides поддерживает различные источники данных, такие как СУБД.
Теперь давайте углубимся в этапы выполнения слияния почты в презентациях с использованием Aspose.Slides для .NET.
## Импортировать пространства имен
Во-первых, убедитесь, что вы импортировали необходимые пространства имен для использования функций, предоставляемых Aspose.Slides:
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
## Шаг 1. Настройте каталог документов
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Проверьте, существует ли путь к результату
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Шаг 2. Создайте набор данных с использованием данных XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Шаг 3. Перебор записей и создание индивидуальных презентаций
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // создать название результата (индивидуального) представления
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Загрузить шаблон презентации
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Заполните текстовые поля данными из основной таблицы
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Получить изображение из базы данных
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Вставьте изображение в рамку презентации.
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Получите и подготовьте текстовый фрейм для заполнения его данными
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Заполните данные о персонале
        FillStaffList(textFrame, userRow, staffListTable);
        // Заполнение фактических данных плана
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Шаг 4. Заполните текстовый фрейм данными в виде списка
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
## Шаг 5. Заполните диаграмму данных из вторичной таблицы PlanFact.
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
    // Добавьте точки данных для серии линий
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
Эти шаги демонстрируют подробное руководство по выполнению слияния почты в презентациях с использованием Aspose.Slides для .NET. Теперь давайте ответим на некоторые часто задаваемые вопросы.
## Часто задаваемые вопросы
### 1. Совместим ли Aspose.Slides для .NET с различными источниками данных?
Да, Aspose.Slides for .NET поддерживает различные источники данных, включая XML, СУБД и другие.
### 2. Могу ли я настроить внешний вид пунктов списка в созданной презентации?
 Конечно! Вы имеете полный контроль над внешним видом пунктов списка, как показано в`FillStaffList` метод.
### 3. Какие типы диаграмм я могу создавать с помощью Aspose.Slides для .NET?
Aspose.Slides for .NET поддерживает широкий спектр диаграмм, включая линейные диаграммы, как показано в нашем примере, гистограммы, круговые диаграммы и многое другое.
### 4. Как мне получить поддержку или обратиться за помощью по Aspose.Slides для .NET?
 Для поддержки и помощи вы можете посетить[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Могу ли я попробовать Aspose.Slides для .NET перед покупкой?
 Конечно! Вы можете воспользоваться бесплатной пробной версией Aspose.Slides для .NET на сайте[здесь](https://releases.aspose.com/).
## Заключение
В этом руководстве мы рассмотрели потрясающие возможности Aspose.Slides для .NET при выполнении слияния почты в презентациях. Следуя пошаговому руководству, вы сможете легко создавать динамичные и персонализированные презентации. Повысьте свой опыт разработки .NET с помощью Aspose.Slides для беспрепятственного создания презентаций.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
