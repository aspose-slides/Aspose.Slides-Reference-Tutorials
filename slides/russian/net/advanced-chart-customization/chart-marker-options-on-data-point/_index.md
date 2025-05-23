---
"description": "Узнайте, как улучшить ваши диаграммы PowerPoint с помощью Aspose.Slides для .NET. Настройте маркеры точек данных с помощью изображений. Создавайте увлекательные презентации."
"linktitle": "Параметры маркера диаграммы на точке данных"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Использование параметров маркера диаграммы в точке данных в Aspose.Slides .NET"
"url": "/ru/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Использование параметров маркера диаграммы в точке данных в Aspose.Slides .NET


При работе с презентациями и визуализацией данных Aspose.Slides for .NET предлагает широкий спектр мощных функций для создания, настройки и управления диаграммами. В этом руководстве мы рассмотрим, как использовать параметры маркеров диаграмм на точках данных для улучшения презентаций диаграмм. Это пошаговое руководство проведет вас через весь процесс, начиная с предварительных условий и импорта пространств имен, и заканчивая разбиением каждого примера на несколько шагов.

## Предпосылки

Прежде чем мы углубимся в использование параметров маркеров диаграммы для точек данных, убедитесь, что выполнены следующие предварительные условия:

- Aspose.Slides for .NET: Убедитесь, что у вас установлен Aspose.Slides for .NET. Вы можете загрузить его с [веб-сайт](https://releases.aspose.com/slides/net/).

- Образец презентации: Для этого урока мы будем использовать образец презентации с именем «Test.pptx». Эта презентация должна быть в вашем каталоге документов.

Теперь начнем с импорта необходимых пространств имен.

## Импорт пространств имен

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Мы импортировали требуемые пространства имен и инициализировали нашу презентацию. Теперь давайте перейдем к использованию опций маркера диаграммы на точках данных.

## Шаг 1: Создание диаграммы по умолчанию

```csharp

// Путь к каталогу документов.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Создание диаграммы по умолчанию
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Мы создаем диаграмму по умолчанию типа «LineWithMarkers» на слайде в указанном месте и размере.

## Шаг 2: Получение индекса рабочего листа данных диаграммы по умолчанию

```csharp
// Получение индекса рабочего листа данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;
```

Здесь мы получаем индекс рабочего листа данных диаграммы по умолчанию.

## Шаг 3: Получение рабочего листа данных диаграммы

```csharp
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Для работы с данными диаграммы мы извлекаем рабочую книгу данных диаграммы.

## Шаг 4: Изменение серии диаграмм

```csharp
// Удалить демо-серию
chart.ChartData.Series.Clear();

// Добавить новую серию
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

На этом этапе мы удаляем все существующие демонстрационные серии и добавляем в диаграмму новую серию под названием «Серия 1».

## Шаг 5: Настройка заливки изображения для точек данных

```csharp
// Установить картинку для маркеров
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Возьмем первую серию диаграмм.
IChartSeries series = chart.ChartData.Series[0];

// Добавить новые точки данных с заливкой изображением
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

Мы устанавливаем маркеры изображений для точек данных, что позволяет вам настраивать способ отображения каждой точки данных на диаграмме.

## Шаг 6: Изменение размера маркера серии диаграммы

```csharp
// Изменение размера маркера серии диаграммы
series.Marker.Size = 15;
```

Здесь мы настраиваем размер маркера серии диаграммы, чтобы сделать его визуально привлекательным.

## Шаг 7: Сохранение презентации

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Наконец, сохраняем презентацию с новыми настройками диаграммы.

## Заключение

Aspose.Slides for .NET позволяет вам создавать потрясающие презентации диаграмм с различными параметрами настройки. В этом руководстве мы сосредоточились на использовании параметров маркеров диаграмм на точках данных для улучшения визуального представления ваших данных. С Aspose.Slides for .NET вы можете вывести свои презентации на новый уровень, сделав их более интересными и информативными.

Если у вас есть вопросы или вам нужна помощь с Aspose.Slides для .NET, посетите [Документация Aspose.Slides](https://reference.aspose.com/slides/net/) или обратитесь к [Сообщество Aspose](https://forum.aspose.com/) за поддержку.

## Часто задаваемые вопросы (FAQ)

### Можно ли использовать пользовательские изображения в качестве маркеров для точек данных в Aspose.Slides для .NET?
Да, вы можете использовать пользовательские изображения в качестве маркеров для точек данных в Aspose.Slides для .NET, как показано в этом руководстве.

### Как изменить тип диаграммы в Aspose.Slides для .NET?
Вы можете изменить тип диаграммы, указав другой `ChartType` при создании диаграммы, например «Гистограмма», «Круговая диаграмма» или «Площадь».

### Совместим ли Aspose.Slides для .NET с последними версиями PowerPoint?
Aspose.Slides для .NET предназначен для работы с различными форматами PowerPoint и регулярно обновляется для обеспечения совместимости с последними версиями PowerPoint.

### Где я могу найти больше учебных пособий и ресурсов по Aspose.Slides для .NET?
Вы можете изучить дополнительные руководства и ресурсы в [Документация Aspose.Slides](https://reference.aspose.com/slides/net/).

### Доступна ли пробная версия Aspose.Slides для .NET?
Да, вы можете попробовать Aspose.Slides для .NET, загрузив бесплатную пробную версию с сайта [здесь](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}