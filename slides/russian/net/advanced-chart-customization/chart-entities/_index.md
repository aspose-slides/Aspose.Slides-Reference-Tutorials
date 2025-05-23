---
"description": "Узнайте, как создавать потрясающие диаграммы с помощью Aspose.Slides для .NET. Поднимите свою визуализацию данных на новый уровень с помощью нашего пошагового руководства."
"linktitle": "Объекты диаграммы и форматирование"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Создание красивых диаграмм с помощью Aspose.Slides для .NET"
"url": "/ru/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Создание красивых диаграмм с помощью Aspose.Slides для .NET


В современном мире, где все основано на данных, эффективная визуализация данных является ключом к передаче информации вашей аудитории. Aspose.Slides для .NET — это мощная библиотека, которая позволяет вам создавать потрясающие презентации и слайды, включая привлекательные диаграммы. В этом руководстве мы проведем вас через процесс создания красивых диаграмм с помощью Aspose.Slides для .NET. Мы разобьем каждый пример на несколько шагов, чтобы помочь вам понять и реализовать сущности диаграмм и форматирование. Итак, начнем!

## Предпосылки

Прежде чем мы приступим к созданию красивых диаграмм с помощью Aspose.Slides для .NET, вам необходимо убедиться в наличии следующих предварительных условий:

1. Aspose.Slides for .NET: Убедитесь, что у вас установлена библиотека Aspose.Slides for .NET. Вы можете загрузить ее с [веб-сайт](https://releases.aspose.com/slides/net/).

2. Среда разработки: у вас должна быть рабочая среда разработки с Visual Studio или любой другой IDE, поддерживающей разработку .NET.

3. Базовые знания C#: для этого руководства необходимо знакомство с программированием на C#.

Теперь, когда все необходимые условия выполнены, давайте приступим к созданию красивых диаграмм с помощью Aspose.Slides для .NET.

## Импорт пространств имен

Сначала вам необходимо импортировать необходимые пространства имен для работы с Aspose.Slides для .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Шаг 1: Создайте презентацию

Начнем с создания новой презентации для работы. Эта презентация послужит холстом для нашей диаграммы.

```csharp
// Путь к каталогу документов.
string dataDir = "Your Document Directory";

// Создайте каталог, если его еще нет.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Создание презентации
Presentation pres = new Presentation();
```

## Шаг 2: Получите доступ к первому слайду

Давайте откроем первый слайд презентации, на котором мы разместим нашу диаграмму.

```csharp
// Доступ к первому слайду
ISlide slide = pres.Slides[0];
```

## Шаг 3: Добавьте образец диаграммы

Теперь добавим на наш слайд образец диаграммы. В этом примере мы создадим линейную диаграмму с маркерами.

```csharp
// Добавление образца диаграммы
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Шаг 4: Задайте название диаграммы

Мы дадим нашей диаграмме название, сделав ее более информативной и визуально привлекательной.

```csharp
// Установка заголовка диаграммы
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Шаг 5: Настройте линии сетки вертикальной оси

На этом этапе мы настроим линии сетки вертикальной оси, чтобы сделать нашу диаграмму более визуально привлекательной.

```csharp
// Настройка формата основных линий сетки для оси значений
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Настройка формата линий дополнительной сетки для оси значений
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Формат числа оси значений настройки
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Шаг 6: Определите диапазон вертикальной оси

На этом этапе мы установим максимальное, минимальное и единичное значения для вертикальной оси.

```csharp
// Установка максимальных и минимальных значений диаграммы
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Шаг 7: Настройте текст вертикальной оси

Теперь настроим внешний вид текста на вертикальной оси.

```csharp
// Настройка свойств текста оси значений
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Установка заголовка оси значений
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Шаг 8: Настройте линии сетки горизонтальной оси

Теперь давайте настроим линии сетки для горизонтальной оси.

```csharp
// Настройка формата основных линий сетки для оси категорий
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Настройка формата линий дополнительной сетки для оси категорий
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Настройка свойств текста оси категорий
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Шаг 9: Настройте метки горизонтальной оси

На этом этапе мы настроим положение и поворот меток горизонтальной оси.

```csharp
// Установка положения метки оси категории
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Установка угла поворота метки оси категории
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Шаг 10: Настройте легенды

Давайте улучшим легенды на нашей диаграмме для лучшей читаемости.

```csharp
// Настройка свойств текста легенды
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Установить отображение легенд диаграммы без перекрытия диаграммы
chart.Legend.Overlay = true;
```

## Шаг 11: Настройте фон диаграммы

Мы настроим цвета фона диаграммы, задней стены и пола.

```csharp
// Настройка цвета задней стенки диаграммы
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Настройка цвета области построения
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Шаг 12: Сохраните презентацию

Наконец, сохраним нашу презентацию с отформатированной диаграммой.

```csharp
// Сохранить презентацию
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

Создание красивых и информативных диаграмм в ваших презентациях теперь стало проще, чем когда-либо, с Aspose.Slides для .NET. В этом руководстве мы рассмотрели основные шаги по настройке различных аспектов диаграммы, делая ее визуально привлекательной и информативной. С помощью этих методов вы можете создавать потрясающие диаграммы, которые эффективно доносят ваши данные до вашей аудитории.

Начните экспериментировать с Aspose.Slides для .NET и выведите визуализацию данных на новый уровень!

## Часто задаваемые вопросы

### 1. Что такое Aspose.Slides для .NET?

Aspose.Slides для .NET — это мощная библиотека, которая позволяет разработчикам .NET создавать, изменять и конвертировать презентации Microsoft PowerPoint. Она предоставляет широкий спектр функций для работы со слайдами, фигурами, диаграммами и многим другим.

### 2. Где я могу скачать Aspose.Slides для .NET?

Вы можете загрузить Aspose.Slides для .NET с сайта [здесь](https://releases.aspose.com/slides/net/).

### 3. Существует ли бесплатная пробная версия Aspose.Slides для .NET?

Да, вы можете получить бесплатную пробную версию Aspose.Slides для .NET от [здесь](https://releases.aspose.com/).

### 4. Как получить временную лицензию на Aspose.Slides для .NET?

Если вам нужна временная лицензия, вы можете получить ее здесь: [эта ссылка](https://purchase.aspose.com/temporary-license/).

### 5. Существует ли сообщество или форум поддержки Aspose.Slides для .NET?

Да, вы можете найти сообщество Aspose.Slides и форум поддержки [здесь](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}