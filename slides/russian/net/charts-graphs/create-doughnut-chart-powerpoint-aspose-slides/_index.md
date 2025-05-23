---
"date": "2025-04-15"
"description": "Узнайте, как создавать динамичные и визуально привлекательные кольцевые диаграммы в презентациях PowerPoint с помощью мощной библиотеки Aspose.Slides для .NET."
"title": "Как создать кольцевую диаграмму в PowerPoint с помощью Aspose.Slides для .NET"
"url": "/ru/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать кольцевую диаграмму в PowerPoint с помощью Aspose.Slides для .NET
Создание визуально привлекательных диаграмм необходимо для эффективной презентации данных. Кольцевые диаграммы идеально подходят для иллюстрации частей целого, что делает их идеальными для визуализации данных на основе процентов. Это руководство проведет вас через создание динамической кольцевой диаграммы в PowerPoint с использованием мощной библиотеки Aspose.Slides для .NET.

## Введение
Презентации часто требуют визуального представления сложных наборов данных, для которых традиционные столбчатые или линейные диаграммы могут оказаться недостаточными. Кольцевая диаграмма выступает в качестве универсального инструмента для эффективной передачи процентных данных со стилем и ясностью. В этом руководстве мы рассмотрим, как Aspose.Slides for .NET упрощает процесс создания этих диаграмм непосредственно в PowerPoint.

**Что вы узнаете:**
- Настройка Aspose.Slides для .NET
- Пошаговая инструкция по созданию кольцевой диаграммы
- Добавление серий и категорий в вашу диаграмму
- Настройка меток данных для большей ясности
- Сохранение финальной презентации

Давайте рассмотрим, как можно использовать Aspose.Slides для .NET для улучшения ваших презентаций с помощью пользовательских кольцевых диаграмм.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:
- **Библиотека Aspose.Slides для .NET**: Доступно через NuGet или путем прямой загрузки.
- **Среда разработки**Visual Studio рекомендуется для проектов .NET.
- Базовые знания C# и знакомство со структурой PowerPoint.

## Настройка Aspose.Slides для .NET
Чтобы начать создавать диаграммы, вам сначала нужно настроить библиотеку Aspose.Slides в вашем проекте. Вот несколько способов ее установки:

**Использование .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Использование консоли диспетчера пакетов:**

```powershell
Install-Package Aspose.Slides
```

**Через пользовательский интерфейс диспетчера пакетов NuGet:**
Найдите «Aspose.Slides» и установите последнюю версию.

После установки вы можете начать настройку своего проекта. Если вы новичок в Aspose.Slides, рассмотрите возможность получения временной лицензии или бесплатной пробной версии, чтобы изучить все его возможности без ограничений.

### Инициализируйте свой проект
Вот как можно инициализировать Aspose.Slides в вашем приложении:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Создать экземпляр класса Presentation
        Presentation presentation = new Presentation();
        
        // Ваш код для управления презентацией находится здесь
        
        // Сохранить презентацию
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Руководство по внедрению
### Создание кольцевой диаграммы
#### Обзор
Сначала мы создадим пустую кольцевую диаграмму на слайде PowerPoint. Это послужит основой для добавления данных и настройки ее внешнего вида.

**Шаг 1: Добавьте кольцевую диаграмму**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Добавьте кольцевую диаграмму на первый слайд в позицию (10, 10) с размером (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Очистить существующие серии и категории
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Отключите легенду для более четкого вида
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Объяснение:**
- **добавитьДиаграмму**: Вставляет новую кольцевую диаграмму на слайд.
- **getChartDataWorkbook**: Предоставляет доступ к ячейкам данных в диаграмме для манипулирования.

### Добавление серий и категорий
#### Обзор
Далее мы заполним вашу диаграмму значимыми данными, добавив серии и категории.

**Шаг 2: Добавьте ряд данных**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Добавить серию
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Настройка отверстия для бублика и начального угла
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Добавить категории
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Форматирование заливки и линии точки данных
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Объяснение:**
- **добавлять**: Вставляет новые серии и категории в диаграмму.
- **setDoughnutHoleSize**Задает размер отверстия в бублике, улучшая его визуальную привлекательность.

### Настройка меток данных
#### Обзор
Метки данных обеспечивают контекст для данных вашей диаграммы. Давайте улучшим читаемость, настроив их.

**Шаг 3: Настройте метки данных**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Настройка меток данных
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Объяснение:**
- **IDataLabel**: Настраивает метки данных для ясности и наглядности.
- **setCenterText**, **показыватьПроцент**: Улучшите читаемость этикетки, выровняв текст по центру и показав проценты.

## Заключение
Следуя этому руководству, вы узнали, как создать динамическую кольцевую диаграмму в PowerPoint с помощью Aspose.Slides для .NET. Эта мощная библиотека обеспечивает обширную настройку, позволяя вам точно адаптировать ваши диаграммы к потребностям вашей презентации.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}