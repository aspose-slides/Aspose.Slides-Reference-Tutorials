---
title: Расширенная настройка диаграммы в Aspose.Slides
linktitle: Расширенная настройка диаграммы в Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Изучите расширенную настройку диаграмм в Aspose.Slides для .NET. Создавайте визуально привлекательные диаграммы с помощью пошаговых инструкций.
type: docs
weight: 10
url: /ru/net/advanced-chart-customization/advanced-chart-customization/
---

Создание визуально привлекательных и информативных диаграмм является важной частью представления данных во многих приложениях. Aspose.Slides для .NET предоставляет надежные инструменты для настройки диаграмм, позволяющие точно настроить каждый аспект ваших диаграмм. В этом уроке мы рассмотрим расширенные методы настройки диаграмм с использованием Aspose.Slides для .NET.

## Предварительные условия

Прежде чем погрузиться в расширенную настройку диаграмм с помощью Aspose.Slides для .NET, убедитесь, что у вас есть следующие предварительные условия:

1. Библиотека Aspose.Slides для .NET: вам необходимо установить и правильно настроить библиотеку Aspose.Slides в вашем проекте .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).

2. Среда разработки .NET. У вас должна быть настроена среда разработки .NET, включая Visual Studio или любую другую IDE по вашему выбору.

3. Базовые знания C#: Знакомство с языком программирования C# будет полезно, поскольку мы будем писать код C# для работы с Aspose.Slides.

Теперь давайте разобьем расширенную настройку диаграммы на несколько этапов, которые помогут вам пройти весь процесс.

## Шаг 1. Создайте презентацию

Сначала создайте новую презентацию с помощью Aspose.Slides.

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

На этом этапе мы запускаем новую презентацию, в которой будет храниться наша диаграмма.

## Шаг 2. Доступ к первому слайду

Затем откройте первый слайд презентации, куда вы хотите добавить диаграмму.

```csharp
// Доступ к первому слайду
ISlide slide = pres.Slides[0];
```

Этот фрагмент кода позволяет работать с первым слайдом презентации.

## Шаг 3. Добавление образца диаграммы

Теперь давайте добавим на слайд образец диаграммы. В этом примере мы создадим линейную диаграмму с маркерами.

```csharp
// Добавление образца диаграммы
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Здесь мы указываем тип диаграммы (LineWithMarkers), ее положение и размеры на слайде.

## Шаг 4: Установка названия диаграммы

Давайте зададим заголовок диаграмме, чтобы обеспечить контекст.

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

Этот код задает заголовок диаграммы, определяя ее текст, внешний вид и стиль шрифта.

## Шаг 5. Настройте основные линии сетки

Теперь давайте настроим основные линии сетки для оси значений.

```csharp
// Настройка формата основных линий сетки для оси значений
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

На этом этапе настраивается внешний вид основных линий сетки на оси значений.

## Шаг 6: Настройте второстепенные линии сетки

Аналогичным образом мы можем настроить второстепенные линии сетки для оси значений.

```csharp
// Настройка формата второстепенных линий сетки для оси значений
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Этот код регулирует внешний вид второстепенных линий сетки на оси значений.

## Шаг 7: Определите формат номера оси значений

Настройте числовой формат для оси значений.

```csharp
// Настройка формата номера оси значения
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Этот шаг позволяет форматировать числа, отображаемые на оси значений.

## Шаг 8: Установите максимальное и минимальное значения диаграммы

Определите максимальное и минимальное значения для диаграммы.

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

Здесь вы указываете диапазон значений, которые должна отображать ось диаграммы.

## Шаг 9. Настройка свойств текста оси значений

Вы также можете настроить текстовые свойства оси значений.

```csharp
// Настройка свойств текста оси значений
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Этот код позволяет настроить стиль шрифта и внешний вид меток оси значений.

## Шаг 10: Добавьте заголовок оси значений

Если для вашей диаграммы требуется заголовок оси значений, вы можете добавить его на этом шаге.

```csharp
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

На этом шаге вы можете задать заголовок для оси значений.

## Шаг 11. Настройте основные линии сетки для оси категорий

Теперь давайте сосредоточимся на основных линиях сетки оси категорий.

```csharp
// Настройка формата основных линий сетки для оси категорий
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Этот код настраивает внешний вид основных линий сетки на оси категорий.

## Шаг 12. Настройте второстепенные линии сетки для оси категорий

Подобно оси значений, вы можете настроить второстепенные линии сетки для оси категорий.

```csharp
//Настройка формата второстепенных линий сетки для оси категорий
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Здесь вы настраиваете внешний вид второстепенных линий сетки на оси категорий.

## Шаг 13. Настройка свойств текста оси категорий

Настройте свойства текста для меток оси категорий.

```csharp
// Настройка свойств текста оси категорий
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Этот код позволяет настроить стиль шрифта и внешний вид меток оси категорий.

## Шаг 14. Добавьте заголовок оси категории

При необходимости вы также можете добавить заголовок к оси категорий.

```csharp
// Настройка заголовка категории
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

На этом этапе вы можете задать заголовок для оси категорий.

## Шаг 15: Дополнительные настройки

Вы можете изучить дополнительные настройки, такие как легенды, цвета задней стенки диаграммы, пола и области графика. Эти настройки позволяют повысить визуальную привлекательность вашей диаграммы.

```csharp
// Дополнительные настройки (необязательно)

// Настройка свойств текста легенды
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Установите легенды диаграммы без перекрытия диаграммы
chart.Legend.Overlay = true;

// Построение первого ряда на вторичной оси значений (при необходимости)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Настройка цвета задней стенки диаграммы
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Настройка цвета пола диаграммы
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Настройка цвета области графика
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Сохранить презентацию
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Эти дополнительные настройки не являются обязательными и могут применяться в зависимости от ваших конкретных требований к дизайну диаграммы.

## Заключение

В этом пошаговом руководстве мы рассмотрели расширенную настройку диаграмм с помощью Aspose.Slides для .NET. Вы узнали, как создать презентацию, добавить диаграмму и точно настроить ее внешний вид, включая линии сетки, метки осей и другие визуальные элементы. Благодаря мощным возможностям настройки, предоставляемым Aspose.Slides, вы можете создавать диаграммы, которые эффективно передают ваши данные и привлекают аудиторию.

 Если у вас есть какие-либо вопросы или вы столкнулись с какими-либо проблемами при работе с Aspose.Slides for .NET, изучите документацию.[здесь](https://reference.aspose.com/slides/net/) или обратитесь за помощью в Aspose.Slides[Форум](https://forum.aspose.com/).

## Часто задаваемые вопросы

### Какие версии .NET поддерживаются Aspose.Slides для .NET?
Aspose.Slides для .NET поддерживает различные версии .NET, включая .NET Framework и .NET Core. Полный список поддерживаемых версий можно найти в документации.

### Могу ли я создавать диаграммы из источников данных, таких как файлы Excel, с помощью Aspose.Slides для .NET?
Да, Aspose.Slides for .NET позволяет создавать диаграммы из внешних источников данных, таких как электронные таблицы Excel. Вы можете изучить документацию для получения подробных примеров.

### Как добавить пользовательские метки данных в серию диаграмм?
 Чтобы добавить пользовательские метки данных в серию диаграмм, вы можете получить доступ к`DataLabels` свойство серии и настройте метки по мере необходимости. Образцы кода и примеры см. в документации.

### Можно ли экспортировать диаграмму в другие форматы файлов, например PDF или изображения?
Да, Aspose.Slides for .NET предоставляет возможность экспорта вашей презентации с диаграммами в различные форматы, включая PDF и форматы изображений. Вы можете использовать библиотеку, чтобы сохранить свою работу в желаемом выходном формате.

### Где я могу найти дополнительные руководства и примеры для Aspose.Slides для .NET?
 Вы можете найти множество учебных пособий, примеров кода и документации на сайте Aspose.Slides.[Веб-сайт](https://reference.aspose.com/slides/net/).