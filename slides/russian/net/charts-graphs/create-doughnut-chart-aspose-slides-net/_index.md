---
"date": "2025-04-15"
"description": "Узнайте, как создавать динамические кольцевые диаграммы с помощью Aspose.Slides для .NET. Следуйте этому руководству для пошаговых инструкций, включая настройку и расширенные функции."
"title": "Пошаговое руководство&#58; создание кольцевой диаграммы с помощью Aspose.Slides .NET | Диаграммы и графики"
"url": "/ru/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Пошаговое руководство: создание кольцевой диаграммы с помощью Aspose.Slides .NET

## Введение

Представьте, что вам поручено представить результаты анализа данных вашей команде или клиентам, и вам нужен увлекательный способ визуализации информации. Познакомьтесь с кольцевой диаграммой — универсальным инструментом, который может преобразовать сырые числа в легко усваиваемые идеи. С Aspose.Slides для .NET создание пользовательской кольцевой диаграммы на слайдах презентации становится простым и эффективным. Это руководство проведет вас через использование Aspose.Slides для создания визуально привлекательной кольцевой диаграммы, дополненной индивидуальными конфигурациями серий.

**Что вы узнаете:**
- Настройка среды разработки с помощью Aspose.Slides для .NET
- Создание и настройка кольцевых диаграмм в презентациях
- Реализация расширенных функций, таких как названия категорий и линии указателей
- Оптимизация производительности для больших наборов данных

Давайте рассмотрим предварительные условия, необходимые для начала работы.

## Предпосылки

Перед реализацией этой функции убедитесь, что ваша среда разработки настроена правильно. Это руководство предполагает базовые знания программирования .NET и знакомство с Visual Studio или аналогичной IDE.

### Требуемые библиотеки и версии
- **Aspose.Slides для .NET**: Убедитесь в совместимости с последней версией, проверив их [официальная документация](https://reference.aspose.com/slides/net/).

### Требования к настройке среды
- Рабочая среда .NET.
- Доступ к редактору кода, например Visual Studio.

### Необходимые знания
- Базовые знания C# и .NET Framework.
- Знакомство с концепциями программного обеспечения для создания презентаций (необязательно, но полезно).

## Настройка Aspose.Slides для .NET

Чтобы начать использовать Aspose.Slides в вашем проекте, вам нужно установить его через NuGet. Вот доступные методы:

**Использование .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Использование менеджера пакетов:**
```powershell
Install-Package Aspose.Slides
```

**Пользовательский интерфейс менеджера пакетов NuGet:**
Найдите «Aspose.Slides» и установите последнюю версию.

### Этапы получения лицензии

1. **Бесплатная пробная версия**: Начните с [бесплатная пробная версия](https://releases.aspose.com/slides/net/) для изучения основных функций.
2. **Временная лицензия**: Получите временную лицензию, если вам нужен доступ ко всем функциям для ознакомительных целей, посетив [здесь](https://purchase.aspose.com/temporary-license/).
3. **Покупка**: Для коммерческого использования приобретите лицензию у [Сайт Aspose](https://purchase.aspose.com/buy).

После установки и лицензирования инициализируйте Aspose.Slides в своем проекте:
```csharp
using Aspose.Slides;

// Инициализация Aspose.Slides для .NET
var presentation = new Presentation();
```

## Руководство по внедрению

### Создание новой презентации и добавление кольцевой диаграммы

#### Обзор
Начнем с создания новой презентации и добавления кольцевой диаграммы на первый слайд. В этом разделе рассматривается загрузка существующей презентации, доступ к слайдам и вставка диаграмм.

**Шаг 1: Загрузите или создайте презентацию**
Сначала укажите каталог документов и загрузите существующую презентацию:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Если у вас нет существующего файла, создайте новый с помощью `new Presentation()`.

**Шаг 2: Получите доступ к первому слайду**
Получите доступ к первому слайду, куда мы добавим нашу диаграмму:
```csharp
ISlide slide = pres.Slides[0];
```

**Шаг 3: Добавьте кольцевую диаграмму**
Добавьте кольцевую диаграмму с указанными координатами и размерами:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Настройка рабочей книги данных

#### Обзор
В этом разделе объясняется, как настроить книгу данных, связанную с вашей кольцевой диаграммой.

**Шаг 4: Доступ к существующим данным и их очистка**
Получите доступ к рабочей книге данных диаграммы. Затем очистите все существующие серии или категории:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Шаг 5: Отключите легенду и добавьте серию**
Отключите легенду, чтобы сохранить чистоту диаграммы, затем добавьте до 15 серий с пользовательскими конфигурациями:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Добавление категорий и точек данных

#### Обзор
Теперь давайте заполним диаграмму категориями и точками данных для каждой серии.

**Шаг 6: Добавьте категории**
Выполните цикл, чтобы добавить 15 категорий:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Шаг 7: Заполнение точек данных**
Добавьте точки данных для каждой серии в текущей категории:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Настроить внешний вид
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Настроить формат этикетки для последней серии
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Настроить отображение метки
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Сохранение презентации

**Шаг 8: Сохраните файл.**
Наконец, сохраните презентацию в указанном каталоге:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}