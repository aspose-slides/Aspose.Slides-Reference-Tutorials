---
title: Выполнение слияния почты в презентациях
linktitle: Выполнение слияния почты в презентациях
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как выполнить слияние почты в презентациях с помощью Aspose.Slides for .NET, в этом подробном пошаговом руководстве. С легкостью создавайте персонализированные и динамичные презентации.
type: docs
weight: 21
url: /ru/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

В сфере разработки программного обеспечения создание динамичных и персонализированных презентаций является распространенным требованием. Предприятиям часто необходимо создавать презентации, адаптированные к конкретным данным, и именно здесь в игру вступает функция слияния почты. В этом руководстве мы покажем вам процесс слияния почты в презентациях с использованием Aspose.Slides для .NET.

## Введение

Слияние почты — это мощный метод, позволяющий наполнять шаблоны презентаций данными из различных источников, таких как базы данных или файлы XML. В этом руководстве мы сосредоточимся на использовании Aspose.Slides для .NET для пошагового выполнения слияния почты в презентациях.

## Настройка среды

Прежде чем мы углубимся в процесс слияния почты, вам необходимо настроить среду разработки. Убедитесь, что у вас есть следующие предварительные условия:

- Visual Studio или любая другая среда разработки C#.
-  Установлена библиотека Aspose.Slides для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/slides/net/).

## Понимание источника данных

Для слияния почты вам понадобится источник данных. В этом уроке мы будем использовать XML-файл в качестве источника данных. Вот пример того, как может выглядеть ваш источник данных:

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

## Создание шаблона презентации

Чтобы выполнить слияние почты, вам понадобится шаблон презентации (файл PPTX), который определяет макет ваших окончательных презентаций. Вы можете создать этот шаблон с помощью Microsoft PowerPoint или любого другого инструмента по вашему выбору.

## Процесс слияния почты

Теперь давайте углубимся в сам процесс слияния почты с использованием Aspose.Slides для .NET. Разобьем на этапы:

1. Загрузите шаблон презентации.
2. Заполните текстовые поля данными из источника данных.
3. Вставьте изображения в презентацию.
4. Подготовьте и заполните текстовые рамки.
5. Сохраните отдельные презентации.

Вот фрагмент кода C#, который выполняет эти шаги:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Путь к данным.
    // Данные XML являются одним из примеров возможных источников данных MailMerge (среди СУБД и других типов источников данных).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Проверьте, существует ли путь к результату
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // Создание набора данных с использованием данных XML
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Для всех записей в основной таблице создадим отдельную презентацию.
        foreach (DataRow userRow in usersTable.Rows)
        {
            // создать название результата (индивидуального) представления
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Загрузить шаблон презентации
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Заполните текстовые поля данными из основной таблицы базы данных.
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Получить изображение из базы данных
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // вставить изображение в рамку презентации
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Получите и подготовьте текстовый фрейм для заполнения его данными.
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // заполнить данные о персонале
                FillStaffList(textFrame, userRow, staffListTable);

                // заполнить фактические данные плана
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

// Заполняет диаграмму данных из вторичной таблицы planFact.
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

## Сохранение результата

После завершения процесса слияния почты для всех записей в источнике данных у вас будут готовы отдельные презентации. Вы можете сохранить их в нужном месте.

## Заключение

Выполнение слияния почты в презентациях с помощью Aspose.Slides for .NET открывает мир возможностей для создания настраиваемых презентаций на основе данных. Это руководство провело вас через основные шаги, позволяющие добиться этого без проблем.

## Часто задаваемые вопросы

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
О1: Хотя Aspose.Slides для .NET — это мощный выбор, другие библиотеки и инструменты также предлагают аналогичную функциональность. В конечном итоге это зависит от ваших конкретных требований и предпочтений.

**Q2: Can I use different data sources apart from XML files?**
О2: Да, Aspose.Slides для .NET поддерживает различные источники данных, включая базы данных и пользовательские структуры данных.

**Q3: How can I format the merged presentations further?**
A3: Вы можете применить дополнительное форматирование, стили и анимацию к объединенным презентациям, используя богатый набор функций Aspose.Slides.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 О4: Да, вы можете получить бесплатную пробную версию Aspose.Slides для .NET.[здесь](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 A5: Для получения технической поддержки и обсуждения вы можете посетить[Форум Aspose.Slides](https://forum.aspose.com/).

Теперь, когда вы узнали, как выполнять слияние почты в презентациях с помощью Aspose.Slides для .NET, вы можете приступить к созданию динамических презентаций с большим объемом данных для своих проектов. Приятного кодирования!
