---
"date": "2025-04-15"
"description": "Узнайте, как улучшить свои презентации с помощью диаграмм рассеяния с помощью Aspose.Slides для .NET. Следуйте этому всеобъемлющему руководству, чтобы эффективно создавать и настраивать диаграммы."
"title": "Добавление точечных диаграмм в презентации с помощью Aspose.Slides .NET&#58; Пошаговое руководство"
"url": "/ru/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Добавление точечных диаграмм в презентации с помощью Aspose.Slides .NET: пошаговое руководство

## Введение
Хотите улучшить свои презентации, легко интегрировав диаграммы рассеяния? Благодаря возможностям Aspose.Slides для .NET создание и настройка диаграмм становится легким делом. Это руководство проведет вас через добавление диаграмм рассеяния на слайды с помощью Aspose.Slides для .NET. Освоив эти приемы, вы сможете представлять данные более эффективно и создавать визуально привлекательные презентации.

**Что вы узнаете:**
- Настройка Aspose.Slides для .NET в вашем проекте
- Создание новой презентации и доступ к ее первому слайду
- Добавление на слайды диаграмм рассеяния с плавными линиями
- Очистка существующих серий и добавление новых в диаграммы
- Изменение точек данных и стилей маркеров для улучшения визуализации
- Сохранение презентации в указанном каталоге

Давайте начнем с обзора предварительных условий.

## Предпосылки
Перед внедрением Aspose.Slides для .NET убедитесь, что у вас есть следующее:
- **Библиотека Aspose.Slides для .NET**: Версия 23.7 или более поздняя.
- **Среда разработки**: Visual Studio 2019 или новее с .NET Framework 4.6.1+ или .NET Core/5+.
- **Базовые знания C#**: Знакомство с объектно-ориентированным программированием на языке C#.

## Настройка Aspose.Slides для .NET
Чтобы начать использовать Aspose.Slides, вам нужно установить библиотеку в свой проект. Вот как это сделать:

**Использование .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Использование консоли диспетчера пакетов:**
```powershell
Install-Package Aspose.Slides
```

**Пользовательский интерфейс менеджера пакетов NuGet:**
- Найдите «Aspose.Slides» и установите последнюю версию.

### Приобретение лицензии
Вы можете начать с бесплатной пробной версии или подать заявку на временную лицензию, чтобы изучить все функции. Чтобы купить, выполните следующие действия:
1. Посещать [Купить Aspose.Slides](https://purchase.aspose.com/buy) купить полную лицензию.
2. Для получения временной лицензии посетите [Страница временной лицензии](https://purchase.aspose.com/temporary-license/).

Получив файл лицензии, добавьте его в свой проект, используя:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Руководство по внедрению
Мы разобьем реализацию на логические разделы на основе функций.

### Создать презентацию и добавить слайд
В этом разделе показано, как создать презентацию и получить доступ к ее первому слайду.

#### Обзор
Начните с создания экземпляра `Presentation` класс, который представляет ваш файл PowerPoint. Доступ к слайдам прост с использованием этой объектной модели.

#### Этапы внедрения
**Шаг 1: Инициализация презентации**
```csharp
using Aspose.Slides;

// Создать новую презентацию
t Presentation pres = new Presentation();
```
Этот код инициализирует новый документ презентации.

**Шаг 2: Доступ к первому слайду**
```csharp
// Доступ к первому слайду презентации
ISlide slide = pres.Slides[0];
```
Здесь, `pres.Slides[0]` открывает самый первый слайд. 

### Добавить точечную диаграмму на слайд
Теперь давайте добавим в вашу презентацию точечную диаграмму.

#### Обзор
Добавление диаграмм может помочь вам визуально представить данные в презентациях. Aspose.Slides упрощает включение различных типов диаграмм, включая диаграммы рассеяния.

#### Этапы внедрения
**Шаг 1: Создание и добавление диаграммы рассеяния**
```csharp
using Aspose.Slides.Charts;

// Создайте и добавьте диаграмму рассеивания по умолчанию с плавными линиями
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Этот фрагмент добавляет точечную диаграмму в указанном месте и размере.

### Очистить и добавить ряды к данным диаграммы
#### Обзор
Вам может потребоваться настроить диаграмму, очистив существующие серии и добавив новые. В этом разделе рассматривается эта функциональность.

#### Этапы внедрения
**Шаг 1: Доступ к рабочей книге данных диаграммы**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Очистить все ранее существовавшие серии
chart.ChartData.Series.Clear();
```
Этот код очищает существующие данные, чтобы начать с новых серий.

**Шаг 2: Добавьте новую серию**
```csharp
// Добавить новую серию под названием «Серия 1»
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Добавить еще одну серию под названием «Серия 2»
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Эти шаги добавляют в диаграмму две новые серии.

### Изменить точки данных первой серии и стиль маркера
#### Обзор
Настройте точки данных и стили маркеров для лучшей визуализации диаграмм рассеяния.

#### Этапы внедрения
**Шаг 1: Доступ и добавление точек данных**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Добавьте точки данных (1, 3) и (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Шаг 2: Измените стиль маркера**
```csharp
// Измените тип серии и измените стиль маркера.
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Изменить точки данных второй серии и стиль маркера
#### Обзор
Аналогичным образом настройте вторую серию в соответствии с потребностями вашей презентации.

#### Этапы внедрения
**Шаг 1: Доступ и добавление нескольких точек данных**
```csharp
// Доступ ко второй серии диаграмм
series = chart.ChartData.Series[1];

// Добавить несколько точек данных
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Шаг 2: Измените стиль маркера**
```csharp
// Изменить размер маркера и символ для второй серии
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Сохранить презентацию
Наконец, сохраните презентацию в указанном каталоге.

#### Этапы внедрения
**Шаг 1: Определите каталог**
Убедитесь, что выходной каталог существует. Если нет, создайте его:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Сохранить презентацию
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Этот код сохраняет файл презентации в указанном месте.

## Заключение
Теперь вы успешно добавили диаграммы рассеяния в свои презентации с помощью Aspose.Slides для .NET. Продолжайте изучать дополнительные функции и настройки, доступные в библиотеке, чтобы улучшить свои навыки визуализации данных.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}