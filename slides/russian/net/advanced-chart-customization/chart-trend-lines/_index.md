---
title: Исследование линий тренда диаграммы в Aspose.Slides для .NET
linktitle: График линий тренда
second_title: Aspose.Slides .NET API обработки PowerPoint
description: В этом пошаговом руководстве вы узнаете, как добавлять различные линии тренда на диаграммы с помощью Aspose.Slides для .NET. Совершенствуйте свои навыки визуализации данных с легкостью!
type: docs
weight: 12
url: /ru/net/advanced-chart-customization/chart-trend-lines/
---

В мире визуализации и представления данных включение диаграмм может стать мощным способом эффективной передачи информации. Aspose.Slides для .NET предоставляет многофункциональный набор инструментов для работы с диаграммами, включая возможность добавлять линии тренда к вашим диаграммам. В этом уроке мы поэтапно углубимся в процесс добавления линий тренда на диаграмму с использованием Aspose.Slides для .NET. 

## Предварительные условия

Прежде чем мы начнем работать с Aspose.Slides для .NET, вам необходимо убедиться, что у вас есть следующие предварительные условия:

1. Aspose.Slides для .NET: Чтобы получить доступ к библиотеке и использовать ее, у вас должен быть установлен Aspose.Slides для .NET. Вы можете получить библиотеку по адресу[страница загрузки](https://releases.aspose.com/slides/net/).

2. Среда разработки. У вас должна быть настроена среда разработки, предпочтительно с использованием интегрированной среды разработки .NET, такой как Visual Studio.

3. Базовые знания C#. Фундаментальное понимание программирования на C# будет полезно, поскольку мы будем использовать C# для работы с Aspose.Slides для .NET.

Теперь, когда мы рассмотрели предварительные условия, давайте шаг за шагом разберем процесс добавления линий тренда на график.

## Импорт пространств имен

Сначала убедитесь, что вы импортировали необходимые пространства имен в свой проект C#. Эти пространства имен необходимы для работы с Aspose.Slides для .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Шаг 1. Создайте презентацию

На этом этапе мы создаем пустую презентацию для работы.

```csharp
// Путь к каталогу документов.
string dataDir = "Your Document Directory";

// Создайте каталог, если он еще не существует.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Создание пустой презентации
Presentation pres = new Presentation();
```

## Шаг 2. Добавьте диаграмму на слайд

Затем мы добавляем на слайд кластеризованную столбчатую диаграмму.

```csharp
// Создание кластеризованной гистограммы
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Шаг 3. Добавьте линии тренда на график

Теперь мы добавляем в серию диаграмм различные типы линий тренда.

### Добавление экспоненциальной линии тренда

```csharp
// Добавление экспоненциальной линии тренда для серии диаграмм 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Добавление линии линейного тренда

```csharp
// Добавление линии линейного тренда для серии диаграмм 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Добавление логарифмической линии тренда

```csharp
// Добавление логарифмической линии тренда для серии диаграмм 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Добавление линии тренда скользящего среднего

```csharp
// Добавление линии тренда скользящего среднего для серии графиков 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Добавление полиномиальной линии тренда

```csharp
// Добавление полиномиальной линии тренда для серии диаграмм 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Добавление линии тренда Power

```csharp
// Добавление линии тренда силы для серии диаграмм 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Шаг 4. Сохраните презентацию

После добавления линий тренда на диаграмму сохраните презентацию.

```csharp
// Сохранение презентации
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно добавили на диаграмму различные линии тренда с помощью Aspose.Slides для .NET.

## Заключение

Aspose.Slides for .NET — это универсальная библиотека, которая позволяет легко создавать диаграммы и манипулировать ими. Следуя этому пошаговому руководству, вы сможете добавлять на диаграммы различные типы линий тренда, улучшая визуальное представление ваших данных.

### Часто задаваемые вопросы

### Где я могу найти документацию по Aspose.Slides для .NET?
 Вы можете получить доступ к документации[здесь](https://reference.aspose.com/slides/net/).

### Как загрузить Aspose.Slides для .NET?
 Вы можете скачать Aspose.Slides для .NET со страницы загрузки.[здесь](https://releases.aspose.com/slides/net/).

### Доступна ли бесплатная пробная версия Aspose.Slides для .NET?
 Да, вы можете бесплатно попробовать Aspose.Slides для .NET, посетив[эта ссылка](https://releases.aspose.com/).

### Где я могу приобрести Aspose.Slides для .NET?
 Чтобы приобрести Aspose.Slides для .NET, посетите страницу покупки.[здесь](https://purchase.aspose.com/buy).

### Нужна ли мне временная лицензия на Aspose.Slides для .NET?
 Вы можете получить временную лицензию на Aspose.Slides для .NET на сайте[эта ссылка](https://purchase.aspose.com/temporary-license/).