---
"date": "2025-04-15"
"description": "Узнайте, как автоматизировать создание круговых диаграмм в презентациях .NET с помощью Aspose.Slides, улучшив визуализацию данных без особых усилий."
"title": "Как создавать и настраивать круговые диаграммы в презентациях .NET с помощью Aspose.Slides"
"url": "/ru/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создавать и настраивать круговые диаграммы в презентациях .NET с помощью Aspose.Slides

## Введение
Создание увлекательных и информативных презентаций имеет решающее значение для эффективной коммуникации, независимо от того, представляете ли вы данные на работе или демонстрируете последние результаты своего проекта. Один из эффективных способов визуализации данных — круговые диаграммы, которые могут кратко представлять части целого. Однако ручное создание этих диаграмм в программном обеспечении для презентаций, таком как PowerPoint, может занять много времени и может не обладать гибкостью, необходимой для динамических обновлений.

Вот где в игру вступает Aspose.Slides for .NET. Эта комплексная библиотека позволяет вам создавать, изменять и оформлять презентации программным способом, что делает ее бесценным инструментом для разработчиков, желающих автоматизировать свой рабочий процесс и обеспечить единообразие презентаций.

В этом уроке мы рассмотрим, как использовать Aspose.Slides для .NET для создания и настройки круговых диаграмм в ваших презентациях. Вы узнаете, как:
- **Создайте презентацию и получите доступ к слайдам**
- **Добавляйте и настраивайте круговые диаграммы**
- **Настройте данные и серии диаграмм**
- **Стиль секторов круговой диаграммы**
- **Добавить пользовательские метки**
- **Настройте свойства отображения и сохраните презентацию.**

Готовы с легкостью окунуться в создание потрясающих круговых диаграмм? Давайте начнем!

## Предпосылки
Прежде чем начать, убедитесь, что у вас выполнены следующие настройки:

### Необходимые библиотеки
- Aspose.Slides для .NET (рекомендуется версия 21.11 или более поздняя)

### Настройка среды
- Среда разработки, работающая на .NET Framework или .NET Core/5+/6+
- Редактор кода, такой как Visual Studio

### Необходимые знания
- Базовые знания программирования на C#
- Знакомство с объектно-ориентированными концепциями

## Настройка Aspose.Slides для .NET
Для начала вам нужно установить библиотеку Aspose.Slides. Это можно сделать любым из следующих способов:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Консоль менеджера пакетов**
```powershell
Install-Package Aspose.Slides
```

**Пользовательский интерфейс диспетчера пакетов NuGet**
- Откройте свой проект в Visual Studio.
- Перейдите в «Инструменты» > «Диспетчер пакетов NuGet» > «Управление пакетами NuGet для решения».
- Найдите «Aspose.Slides» и установите последнюю версию.

### Этапы получения лицензии
Чтобы использовать Aspose.Slides, вы можете начать с бесплатной пробной версии, загрузив временную лицензию. Посетить [Сайт Aspose](https://purchase.aspose.com/temporary-license/) чтобы получить его. Для постоянного использования рассмотрите возможность приобретения полной лицензии.

### Базовая инициализация и настройка
После установки инициализируйте класс Presentation, представляющий ваш файл PPTX:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Руководство по внедрению
Мы разобьем процесс создания круговой диаграммы на управляемые разделы. Каждый раздел предназначен для фокусировки на определенной функции, что позволяет вам постепенно наращивать свои знания.

### Создайте презентацию и получите доступ к слайдам
**Обзор:** Начните с создания новой презентации и доступа к ее первому слайду. Это подготавливает почву для добавления диаграмм и других элементов.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Создать экземпляр класса Presentation, представляющего файл PPTX
    Presentation presentation = new Presentation();
    
    // Доступ к первому слайду
    ISlide slides = presentation.Slides[0];
}
```

### Добавить и настроить круговую диаграмму
**Обзор:** Узнайте, как добавить круговую диаграмму на слайд и задать ее заголовок в соответствии с контекстом.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Создать экземпляр класса Presentation, представляющего файл PPTX
    Presentation presentation = new Presentation();
    
    // Доступ к первому слайду
    ISlide slides = presentation.Slides[0];
    
    // Добавить диаграмму с данными по умолчанию на слайд
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Настройка диаграммы Название
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Настройте данные и серии диаграмм
**Обзор:** Настройте категории и серии данных в соответствии с вашими конкретными требованиями.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Создать экземпляр класса Presentation, представляющего файл PPTX
    Presentation presentation = new Presentation();
    
    // Доступ к первому слайду
    ISlide slides = presentation.Slides[0];
    
    // Добавить диаграмму с данными по умолчанию на слайд
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Установить первую серию для показа значений
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Установка индекса листа данных диаграммы
    int defaultWorksheetIndex = 0;
    
    // Получение рабочего листа данных диаграммы
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Удалить созданные по умолчанию серии и категории
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Добавление новых категорий
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Добавление новых серий
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Сейчас заполняем данные серий
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Настройте стили секторов круговой диаграммы
**Обзор:** Оформите отдельные сектора круговой диаграммы, чтобы повысить ее визуальную привлекательность и подчеркнуть ключевые точки данных.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Создать экземпляр класса Presentation, представляющего файл PPTX
    Presentation presentation = new Presentation();
    
    // Доступ к первому слайду
    ISlide slides = presentation.Slides[0];
    
    // Добавить диаграмму с данными по умолчанию на слайд
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Получить ряд из диаграммы
    IChartSeries series = chart.ChartData.Series[0];
    
    // Настройка стилей секторов для каждой точки данных в серии
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Установка границы сектора
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Установка границы сектора
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Установка границы сектора
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Добавить пользовательские метки в круговую диаграмму
**Обзор:** Улучшите свою круговую диаграмму, добавив пользовательские метки для более четкого представления данных.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // При необходимости отрегулируйте положение этикетки.
    }
}
```

### Заключение
Теперь вы узнали, как создавать и настраивать круговые диаграммы в презентациях .NET с помощью Aspose.Slides. Эта автоматизация может значительно улучшить ваши усилия по визуализации данных, экономя время и обеспечивая согласованность между презентациями.

Чтобы глубже изучить возможности Aspose.Slides для .NET, рассмотрите возможность изучения дополнительных функций, таких как создание других типов диаграмм или интеграция более сложных элементов дизайна в слайды.

Удачного кодирования!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}