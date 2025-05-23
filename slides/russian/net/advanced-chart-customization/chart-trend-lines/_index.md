---
"description": "Узнайте, как добавлять различные линии тренда в диаграммы с помощью Aspose.Slides для .NET в этом пошаговом руководстве. Улучшайте свои навыки визуализации данных с легкостью!"
"linktitle": "График трендовых линий"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Изучение линий тренда диаграммы в Aspose.Slides для .NET"
"url": "/ru/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Изучение линий тренда диаграммы в Aspose.Slides для .NET


В мире визуализации и представления данных включение диаграмм может быть мощным способом эффективной передачи информации. Aspose.Slides для .NET предоставляет богатый набор инструментов для работы с диаграммами, включая возможность добавлять линии тренда к вашим диаграммам. В этом руководстве мы углубимся в процесс добавления линий тренда к диаграмме шаг за шагом с помощью Aspose.Slides для .NET. 

## Предпосылки

Прежде чем начать работу с Aspose.Slides для .NET, вам необходимо убедиться в наличии следующих предварительных условий:

1. Aspose.Slides for .NET: Для доступа к библиотеке и ее использования у вас должен быть установлен Aspose.Slides for .NET. Библиотеку можно получить из [страница загрузки](https://releases.aspose.com/slides/net/).

2. Среда разработки: у вас должна быть настроена среда разработки, желательно с использованием интегрированной среды разработки .NET, например Visual Studio.

3. Базовые знания C#: фундаментальное понимание программирования на C# будет полезным, поскольку мы будем использовать C# для работы с Aspose.Slides для .NET.

Теперь, когда мы рассмотрели предварительные условия, давайте шаг за шагом разберем процесс добавления линий тренда на диаграмму.

## Импорт пространств имен

Во-первых, убедитесь, что вы импортировали необходимые пространства имен в свой проект C#. Эти пространства имен необходимы для работы с Aspose.Slides для .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Шаг 1: Создайте презентацию

На этом этапе мы создаем пустую презентацию для работы.

```csharp
// Путь к каталогу документов.
string dataDir = "Your Document Directory";

// Создайте каталог, если его еще нет.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Создание пустой презентации
Presentation pres = new Presentation();
```

## Шаг 2: Добавьте диаграмму на слайд

Далее мы добавляем на слайд кластеризованную столбчатую диаграмму.

```csharp
// Создание кластеризованной столбчатой диаграммы
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Шаг 3: Добавьте линии тренда на график

Теперь мы добавляем в серию графиков различные типы линий тренда.

### Добавление экспоненциальной линии тренда

```csharp
// Добавление экспоненциальной линии тренда для серии графиков 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Добавление линейной линии тренда

```csharp
// Добавление линейной линии тренда для серии диаграмм 1
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

### Добавление линии тренда скользящей средней

```csharp
// Добавление линии тренда скользящей средней для серии графиков 2
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

### Добавление линии тренда мощности

```csharp
// Добавление линии тренда мощности для серии диаграмм 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Шаг 4: Сохраните презентацию

После добавления линий тренда на диаграмму сохраните презентацию.

```csharp
// Сохранение презентации
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно добавили различные линии тренда на свою диаграмму с помощью Aspose.Slides для .NET.

## Заключение

Aspose.Slides для .NET — это универсальная библиотека, которая позволяет вам легко создавать и управлять диаграммами. Следуя этому пошаговому руководству, вы сможете добавлять различные типы линий тренда в свои диаграммы, улучшая визуальное представление ваших данных.

### Часто задаваемые вопросы

### Где я могу найти документацию по Aspose.Slides для .NET?
Вы можете получить доступ к документации [здесь](https://reference.aspose.com/slides/net/).

### Как загрузить Aspose.Slides для .NET?
Вы можете загрузить Aspose.Slides для .NET со страницы загрузки [здесь](https://releases.aspose.com/slides/net/).

### Существует ли бесплатная пробная версия Aspose.Slides для .NET?
Да, вы можете попробовать Aspose.Slides для .NET бесплатно, посетив сайт [эта ссылка](https://releases.aspose.com/).

### Где можно приобрести Aspose.Slides для .NET?
Чтобы приобрести Aspose.Slides для .NET, посетите страницу покупки [здесь](https://purchase.aspose.com/buy).

### Нужна ли мне временная лицензия для Aspose.Slides для .NET?
Вы можете получить временную лицензию на Aspose.Slides для .NET по адресу [эта ссылка](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}