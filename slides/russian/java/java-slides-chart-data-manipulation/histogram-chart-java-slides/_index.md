---
title: Гистограмма в слайдах Java
linktitle: Гистограмма в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать гистограммы в презентациях PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом для визуализации данных.
type: docs
weight: 19
url: /ru/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Введение в гистограмму в слайдах Java с использованием Aspose.Slides

В этом уроке мы проведем вас через процесс создания гистограммы в презентации PowerPoint с использованием API Aspose.Slides для Java. Гистограмма используется для представления распределения данных в течение непрерывного интервала.

## Предварительные условия

 Прежде чем начать, убедитесь, что у вас установлена библиотека Aspose.Slides for Java. Вы можете скачать его с сайта[Веб-сайт Aspose](https://releases.aspose.com/slides/java/).

## Шаг 1. Инициализируйте свой проект

Создайте проект Java и включите библиотеку Aspose.Slides в зависимости вашего проекта.

## Шаг 2. Импортируйте необходимые библиотеки

```java
import com.aspose.slides.*;
```

## Шаг 3. Загрузите существующую презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Обязательно замените`"Your Document Directory"` с фактическим путем к вашему документу PowerPoint.

## Шаг 4. Создайте гистограмму

Теперь давайте создадим гистограмму на слайде презентации.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Добавьте точки данных в ряд
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Установите для типа агрегации по горизонтальной оси значение «Автоматически».
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Сохранить презентацию
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 В этом коде мы сначала удаляем из диаграммы все существующие категории и серии. Затем мы добавляем точки данных в ряд, используя`getDataPoints().addDataPointForHistogramSeries` метод. Наконец, мы устанавливаем тип агрегации по горизонтальной оси на «Автоматический» и сохраняем презентацию.

## Полный исходный код гистограммы в слайдах Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы рассмотрели, как создать гистограмму в презентации PowerPoint с помощью API Aspose.Slides для Java. Гистограммы — ценные инструменты для визуализации распределения данных за непрерывный интервал и могут стать мощным дополнением к вашим презентациям, особенно при работе со статистическим или аналитическим контентом.

## Часто задаваемые вопросы

### Как установить Aspose.Slides для Java?

 Вы можете скачать библиотеку Aspose.Slides для Java с сайта[здесь](https://releases.aspose.com/slides/java/). Следуйте инструкциям по установке, представленным на их сайте.

### Для чего используется гистограмма?

Гистограмма используется для визуализации распределения данных за непрерывный интервал. Он обычно используется в статистике для представления частотных распределений.

### Могу ли я настроить внешний вид гистограммы?

Да, вы можете настроить внешний вид диаграммы, включая ее цвета, метки и оси, с помощью API Aspose.Slides.