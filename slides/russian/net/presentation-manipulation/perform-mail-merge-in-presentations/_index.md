---
"description": "Изучите слияние писем в презентациях с помощью Aspose.Slides для .NET в этом пошаговом руководстве. Создавайте динамичные, персонализированные презентации без усилий."
"linktitle": "Выполнение слияния писем в презентациях"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Выполнение слияния писем в презентациях"
"url": "/ru/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Выполнение слияния писем в презентациях

## Введение
В мире разработки .NET создание динамических и персонализированных презентаций является общим требованием. Одним из мощных инструментов, упрощающих этот процесс, является Aspose.Slides для .NET. В этом руководстве мы погрузимся в увлекательную сферу выполнения слияния почты в презентациях с использованием Aspose.Slides для .NET.
## Предпосылки
Прежде чем отправиться в это путешествие, убедитесь, что у вас выполнены следующие предварительные условия:
- Библиотека Aspose.Slides for .NET: Убедитесь, что у вас установлена библиотека Aspose.Slides for .NET. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/net/).
- Шаблон документа: подготовьте шаблон презентации (например, PresentationTemplate.pptx), который послужит основой для слияния писем.
- Источник данных: Вам нужен источник данных для слияния почты. В нашем примере мы будем использовать данные XML (TestData.xml), но Aspose.Slides поддерживает различные источники данных, такие как RDBMS.
Теперь давайте рассмотрим этапы выполнения слияния писем в презентациях с использованием Aspose.Slides для .NET.
## Импорт пространств имен
Во-первых, убедитесь, что вы импортируете необходимые пространства имен для использования функций, предоставляемых Aspose.Slides:
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
## Шаг 1: Настройте каталог документов
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Проверьте, существует ли путь к результату
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Шаг 2: Создание набора данных с использованием XML-данных
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Шаг 3: Просмотрите записи и создайте отдельные презентации
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // создать результат (индивидуальный) название презентации
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Загрузить шаблон презентации
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Заполните текстовые поля данными из основной таблицы.
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Получить изображение из базы данных
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Вставьте изображение в рамку презентации
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Получить и подготовить текстовую рамку для заполнения ее данными
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Заполнить данные о персонале
        FillStaffList(textFrame, userRow, staffListTable);
        // Заполнить план фактических данных
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Шаг 4: Заполните текстовый фрейм данными в виде списка
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
## Шаг 5: Заполните диаграмму данных из вторичной таблицы PlanFact
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
    // Добавить точки данных для линейного ряда
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
Эти шаги демонстрируют всеобъемлющее руководство по выполнению слияния почты в презентациях с использованием Aspose.Slides для .NET. Теперь давайте рассмотрим некоторые часто задаваемые вопросы.
## Часто задаваемые вопросы
### 1. Совместим ли Aspose.Slides для .NET с различными источниками данных?
Да, Aspose.Slides для .NET поддерживает различные источники данных, включая XML, СУБД и другие.
### 2. Могу ли я настроить внешний вид маркированных списков в созданной презентации?
Конечно! У вас есть полный контроль над внешним видом пунктов списка, как показано в `FillStaffList` метод.
### 3. Какие типы диаграмм можно создавать с помощью Aspose.Slides для .NET?
Aspose.Slides для .NET поддерживает широкий спектр диаграмм, включая линейные диаграммы, как показано в нашем примере, столбчатые диаграммы, круговые диаграммы и многое другое.
### 4. Как получить поддержку или обратиться за помощью по Aspose.Slides для .NET?
Для поддержки и помощи вы можете посетить [Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Могу ли я попробовать Aspose.Slides для .NET перед покупкой?
Конечно! Вы можете воспользоваться бесплатной пробной версией Aspose.Slides для .NET от [здесь](https://releases.aspose.com/).
## Заключение
В этом руководстве мы изучили захватывающие возможности Aspose.Slides для .NET в выполнении слияния писем в презентациях. Следуя пошаговому руководству, вы сможете создавать динамичные и персонализированные презентации без усилий. Повысьте свой опыт разработки .NET с помощью Aspose.Slides для бесшовной генерации презентаций.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}