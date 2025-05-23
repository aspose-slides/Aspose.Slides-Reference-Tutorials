---
"date": "2025-04-15"
"description": "Узнайте, как создавать визуально привлекательные процентные столбчатые диаграммы с накоплением, используя Aspose.Slides для .NET. Следуйте этому пошаговому руководству для четкой визуализации данных."
"title": "Как создать процентные столбчатые диаграммы с накоплением в .NET с помощью Aspose.Slides"
"url": "/ru/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать процентную столбчатую диаграмму с накоплением с помощью Aspose.Slides для .NET

## Введение

В сфере визуализации данных четкое и эффективное представление информации имеет решающее значение для принятия эффективных решений. Для интуитивного отображения сложных наборов данных идеальными являются процентные столбчатые диаграммы с накоплением. Это руководство проведет вас через создание таких диаграмм с помощью Aspose.Slides для .NET, надежной библиотеки, разработанной для управления файлами презентаций.

Следуя этому руководству, вы узнаете:
- Настройка данных диаграммы и настройка числовых форматов.
- Добавление серий и настройка их внешнего вида.
- Форматирование меток для улучшения читабельности.

Готовы окунуться? Давайте начнем с необходимых предварительных условий!

## Предпосылки

Перед созданием процентных столбчатых диаграмм с накоплением убедитесь, что ваша среда настроена правильно. Вам потребуется:

### Требуемые библиотеки, версии и зависимости
- **Aspose.Slides для .NET**: Убедитесь, что эта библиотека установлена.

### Требования к настройке среды
- Среда разработки с установленным .NET SDK.
- Visual Studio или любая совместимая IDE для запуска кода C#.

### Необходимые знания
- Базовые знания программирования на C#.
- Знакомство с настройкой проектов .NET и управлением пакетами.

## Настройка Aspose.Slides для .NET

Чтобы начать создавать диаграммы с помощью Aspose.Slides, сначала установите библиотеку одним из следующих способов:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Менеджер пакетов**
```powershell
Install-Package Aspose.Slides
```

**Пользовательский интерфейс диспетчера пакетов NuGet**
- Найдите «Aspose.Slides» и установите последнюю версию.

### Этапы получения лицензии

Начните с бесплатной пробной версии, загрузив временную лицензию с сайта [Сайт Aspose](https://purchase.aspose.com/temporary-license/). Для дальнейшего использования рассмотрите возможность приобретения полной лицензии. 

После настройки запустите Aspose.Slides в своем проекте:
```csharp
using Aspose.Slides;
```

## Руководство по внедрению

Подготовив среду, давайте разберем создание процентной столбчатой диаграммы с накоплением на этапы.

### Создание и настройка диаграммы

#### Обзор
Создайте экземпляр `Presentation` класс, который необходим для работы со слайдами. Затем добавьте и настройте на слайде столбчатую диаграмму с накоплением.

#### Добавление столбчатой диаграммы с накоплением
```csharp
// Создать экземпляр класса Presentation
document = new Presentation();

// Получить ссылку на первый слайд
slide = document.Slides[0];

// Добавить диаграмму PercentsStackedColumn в позицию (20, 20) размером (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Настройка числового формата
Убедитесь, что ваши данные отображаются в процентах:
```csharp
// Настроить числовой формат для вертикальной оси
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Установить процентный формат числа
```

#### Добавление рядов данных и точек
Очистите существующие данные серий и добавьте новые:
```csharp
// Очистить все существующие данные серий
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Доступ к рабочей книге данных диаграммы
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Добавить новый ряд данных «Reds»
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Установить цвет заливки для серии на красный
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Настройте свойства формата этикетки для серии «Reds»
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Установить процентный формат
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Добавить еще одну серию "Блюз"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Установить цвет заливки для серии на синий
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Установить процентный формат
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Сохранение презентации
Сохраните вашу презентацию в файл:
```csharp
// Сохраните презентацию в формате PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Советы по устранению неполадок
- Убедитесь, что все пространства имен импортированы правильно.
- Проверьте наличие опечаток в именах свойств и вызовах методов.
- Проверьте, существуют ли пути для сохранения файлов и имеют ли они правильные разрешения.

## Практические применения

Вот несколько сценариев, в которых могут оказаться полезными процентные столбчатые диаграммы с накоплением:
1. **Анализ продаж**: Визуализируйте эффективность продукта в разных регионах как долю от общего объема продаж.
2. **Распределение бюджета**: Покажите, как отделы распределяют свой бюджет по отношению к общим расходам компании.
3. **Исследование рынка**: Сравните предпочтения потребителей в отношении различных категорий продуктов с течением времени.
4. **Образовательные данные**: Отображение распределения оценок учащихся по разным предметам.
5. **Статистика здравоохранения**: Представлять демографические данные пациентов с различными заболеваниями.

## Соображения производительности

Для оптимальной производительности примите во внимание:
- Ограничение количества точек данных необходимым.
- Предварительная загрузка данных для минимизации времени выполнения обработки.
- Использование эффективных методов управления памятью с Aspose.Slides для .NET.

## Заключение

Поздравляем! Вы успешно научились создавать процентную столбчатую диаграмму с накоплением с помощью Aspose.Slides для .NET. Этот инструмент улучшает презентации, делая сложные данные более понятными и визуально привлекательными.

Следующие шаги? Изучите другие типы диаграмм, доступные в Aspose.Slides, или интегрируйте эту функциональность в более крупные приложения. Удачного кодирования!

## Раздел часто задаваемых вопросов

**В1: Могу ли я использовать Aspose.Slides бесплатно?**
A1: Да, вы можете начать с бесплатной пробной версии, чтобы протестировать функции Aspose.Slides.

**В2: Какие типы диаграмм поддерживаются Aspose.Slides для .NET?**
A2: Он поддерживает различные диаграммы, такие как круговые, линейчатые, столбчатые, линейные и другие.

**В3: Как начать работу с Aspose.Slides для .NET?**
A3: Установите библиотеку с помощью NuGet или .NET CLI, как описано выше. Следуйте нашей документации, чтобы создать свою первую диаграмму.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}