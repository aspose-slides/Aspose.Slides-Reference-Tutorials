---
title: Создание красивых диаграмм с помощью Aspose.Slides для .NET
linktitle: Объекты диаграммы и форматирование
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как создавать потрясающие диаграммы с помощью Aspose.Slides для .NET. Улучшите свою игру по визуализации данных с помощью нашего пошагового руководства.
type: docs
weight: 13
url: /ru/net/advanced-chart-customization/chart-entities/
---

В современном мире, управляемом данными, эффективная визуализация данных является ключом к передаче информации вашей аудитории. Aspose.Slides for .NET — это мощная библиотека, позволяющая создавать потрясающие презентации и слайды, включая привлекательные диаграммы. В этом уроке мы познакомим вас с процессом создания красивых диаграмм с помощью Aspose.Slides для .NET. Мы разобьем каждый пример на несколько шагов, чтобы помочь вам понять и реализовать объекты диаграммы и форматирование. Итак, начнем!

## Предварительные условия

Прежде чем мы углубимся в создание красивых диаграмм с помощью Aspose.Slides для .NET, вам необходимо убедиться, что у вас есть следующие предварительные условия:

1.  Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides для .NET. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/slides/net/).

2. Среда разработки: у вас должна быть рабочая среда разработки с Visual Studio или любой другой IDE, поддерживающей разработку .NET.

3. Базовые знания C#. Для работы с этим руководством необходимо знание программирования на C#.

Теперь, когда мы подготовили все необходимые условия, давайте приступим к созданию красивых диаграмм с помощью Aspose.Slides для .NET.

## Импортировать пространства имен

Во-первых, вам необходимо импортировать необходимые пространства имен для работы с Aspose.Slides for .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Шаг 1. Создайте презентацию

Начнем с создания новой презентации для работы. Эта презентация послужит основой для нашей диаграммы.

```csharp
// Путь к каталогу документов.
string dataDir = "Your Document Directory";

// Создайте каталог, если он еще не существует.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Создание презентации
Presentation pres = new Presentation();
```

## Шаг 2. Доступ к первому слайду

Давайте откроем первый слайд презентации, на котором мы разместим нашу диаграмму.

```csharp
// Доступ к первому слайду
ISlide slide = pres.Slides[0];
```

## Шаг 3. Добавьте образец диаграммы

Теперь мы добавим образец диаграммы на наш слайд. В этом примере мы создадим линейную диаграмму с маркерами.

```csharp
// Добавление образца диаграммы
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Шаг 4: Установите заголовок диаграммы

Мы дадим нашей диаграмме название, которое сделает ее более информативной и визуально привлекательной.

```csharp
// Установка названия диаграммы
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

## Шаг 5. Настройте линии сетки по вертикальной оси

На этом этапе мы настроим линии сетки по вертикальной оси, чтобы сделать нашу диаграмму более визуально привлекательной.

```csharp
// Настройка формата основных линий сетки для оси значений
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Настройка формата второстепенных линий сетки для оси значений
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Настройка формата номера оси значения
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Шаг 6: Определите диапазон вертикальной оси

На этом этапе мы установим максимальное, минимальное и единичное значения для вертикальной оси.

```csharp
// Установка диаграммы максимальных и минимальных значений
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Шаг 7. Настройте текст по вертикальной оси

Теперь мы настроим внешний вид текста по вертикальной оси.

```csharp
// Настройка свойств текста оси значений
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Название оси значений настройки
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

## Шаг 8. Настройте линии сетки по горизонтальным осям

Теперь давайте настроим линии сетки по горизонтальной оси.

```csharp
// Настройка формата основных линий сетки для оси категорий
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Настройка формата второстепенных линий сетки для оси категорий
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

## Шаг 9. Настройте метки горизонтальной оси

На этом этапе мы настроим положение и поворот меток по горизонтальной оси.

```csharp
// Настройка положения метки оси категорий
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Настройка угла поворота метки оси категории
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Шаг 10: Настройте легенды

Давайте улучшим легенды на нашей диаграмме, чтобы их было легче читать.

```csharp
// Настройка свойств текста легенды
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Установите легенды диаграммы без перекрытия диаграммы
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

//Настройка цвета области графика
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Шаг 12: Сохраните презентацию

Наконец, давайте сохраним нашу презентацию с отформатированной диаграммой.

```csharp
// Сохранить презентацию
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

Создавать красивые и информативные диаграммы в ваших презентациях теперь стало проще, чем когда-либо, с Aspose.Slides для .NET. В этом руководстве мы рассмотрели основные шаги по настройке различных аспектов диаграммы, чтобы сделать ее визуально привлекательной и информативной. С помощью этих методов вы можете создавать потрясающие диаграммы, которые эффективно донесут ваши данные до аудитории.

Начните экспериментировать с Aspose.Slides для .NET и поднимите визуализацию данных на новый уровень!

## Часто задаваемые вопросы

### 1. Что такое Aspose.Slides для .NET?

Aspose.Slides for .NET — это мощная библиотека, которая позволяет .NET-разработчикам создавать, манипулировать и конвертировать презентации Microsoft PowerPoint. Он предоставляет широкий спектр функций для работы со слайдами, фигурами, диаграммами и многим другим.

### 2. Где я могу скачать Aspose.Slides для .NET?

 Вы можете скачать Aspose.Slides для .NET с сайта.[здесь](https://releases.aspose.com/slides/net/).

### 3. Существует ли бесплатная пробная версия Aspose.Slides для .NET?

 Да, вы можете получить бесплатную пробную версию Aspose.Slides для .NET на сайте[здесь](https://releases.aspose.com/).

### 4. Как я могу получить временную лицензию на Aspose.Slides для .NET?

 Если вам нужна временная лицензия, вы можете получить ее у[эта ссылка](https://purchase.aspose.com/temporary-license/).

### 5. Существует ли сообщество или форум поддержки Aspose.Slides для .NET?

 Да, вы можете найти сообщество Aspose.Slides и форум поддержки.[здесь](https://forum.aspose.com/).
