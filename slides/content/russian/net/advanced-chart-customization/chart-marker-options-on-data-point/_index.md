---
title: Использование параметров маркера диаграммы для точки данных в Aspose.Slides .NET
linktitle: Параметры маркера диаграммы в точке данных
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как улучшить диаграммы PowerPoint с помощью Aspose.Slides для .NET. Настройте маркеры точек данных с помощью изображений. Создавайте интересные презентации.
type: docs
weight: 11
url: /ru/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

При работе с презентациями и визуализацией данных Aspose.Slides for .NET предлагает широкий спектр мощных функций для создания, настройки и управления диаграммами. В этом уроке мы рассмотрим, как использовать параметры маркеров диаграммы для точек данных, чтобы улучшить представление диаграмм. Это пошаговое руководство проведет вас через весь процесс, начиная с предварительных требований и импорта пространств имен и заканчивая разбивкой каждого примера на несколько шагов.

## Предварительные условия

Прежде чем мы углубимся в использование параметров маркеров диаграммы для точек данных, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Slides для .NET: убедитесь, что у вас установлен Aspose.Slides для .NET. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/slides/net/).

- Пример презентации. В этом руководстве мы будем использовать образец презентации под названием «Test.pptx». Эта презентация должна быть в вашем каталоге документов.

Теперь давайте начнем с импорта необходимых пространств имен.

## Импортировать пространства имен

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Мы импортировали необходимые пространства имен и инициализировали нашу презентацию. Теперь давайте продолжим использовать параметры маркера диаграммы для точек данных.

## Шаг 1. Создание диаграммы по умолчанию

```csharp

// Путь к каталогу документов.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Создание диаграммы по умолчанию
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Мы создаем диаграмму по умолчанию типа «LineWithMarkers» на слайде в указанном месте и размере.

## Шаг 2. Получение индекса рабочего листа данных диаграммы по умолчанию

```csharp
// Получение индекса таблицы данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;
```

Здесь мы получаем индекс рабочего листа данных диаграммы по умолчанию.

## Шаг 3. Получение таблицы данных диаграммы

```csharp
// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Мы извлекаем книгу данных диаграммы для работы с данными диаграммы.

## Шаг 4. Изменение серии диаграмм

```csharp
// Удалить демонстрационную серию
chart.ChartData.Series.Clear();

// Добавить новую серию
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

На этом этапе мы удаляем все существующие демонстрационные серии и добавляем на диаграмму новую серию с именем «Серия 1».

## Шаг 5. Настройка заполнения изображения для точек данных

```csharp
// Установите картинку для маркеров
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Возьмите первую серию диаграмм
IChartSeries series = chart.ChartData.Series[0];

// Добавьте новые точки данных с заливкой изображения
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Мы устанавливаем маркеры изображений для точек данных, что позволяет вам настроить отображение каждой точки данных на диаграмме.

## Шаг 6. Изменение размера маркера серии диаграммы

```csharp
// Изменение размера маркера серии диаграммы
series.Marker.Size = 15;
```

Здесь мы настраиваем размер маркера серии диаграммы, чтобы сделать его визуально привлекательным.

## Шаг 7: Сохранение презентации

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию с новыми настройками диаграммы.

## Заключение

Aspose.Slides for .NET дает вам возможность создавать потрясающие презентации в виде диаграмм с различными вариантами настройки. В этом руководстве мы сосредоточились на использовании параметров маркеров диаграммы для точек данных, чтобы улучшить визуальное представление ваших данных. С помощью Aspose.Slides для .NET вы можете поднять свои презентации на новый уровень, сделав их более привлекательными и информативными.

Если у вас есть какие-либо вопросы или вам нужна помощь с Aspose.Slides для .NET, посетите[Документация Aspose.Slides](https://reference.aspose.com/slides/net/) или обратитесь в[Сообщество Aspose](https://forum.aspose.com/) для поддержки.

## Часто задаваемые вопросы (FAQ)

### Могу ли я использовать собственные изображения в качестве маркеров для точек данных в Aspose.Slides для .NET?
Да, вы можете использовать собственные изображения в качестве маркеров для точек данных в Aspose.Slides для .NET, как показано в этом руководстве.

### Как изменить тип диаграммы в Aspose.Slides для .NET?
 Вы можете изменить тип диаграммы, указав другой`ChartType` при создании диаграммы, например «Гистограмма», «Круговая диаграмма» или «Площадь».

### Совместим ли Aspose.Slides for .NET с последними версиями PowerPoint?
Aspose.Slides for .NET предназначен для работы с различными форматами PowerPoint и регулярно обновляется для обеспечения совместимости с последними версиями PowerPoint.

### Где я могу найти дополнительные руководства и ресурсы по Aspose.Slides для .NET?
 Вы можете изучить дополнительные руководства и ресурсы в разделе[Документация Aspose.Slides](https://reference.aspose.com/slides/net/).

### Доступна ли пробная версия Aspose.Slides для .NET?
 Да, вы можете попробовать Aspose.Slides для .NET, загрузив бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).