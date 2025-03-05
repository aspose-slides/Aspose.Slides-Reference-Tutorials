---
title: Маркеры по умолчанию на диаграмме в слайдах Java
linktitle: Маркеры по умолчанию на диаграмме в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать слайды Java с маркерами по умолчанию на диаграммах с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом.
type: docs
weight: 16
url: /ru/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Введение в маркеры по умолчанию в диаграмме в слайдах Java

В этом уроке мы рассмотрим, как создать диаграмму с маркерами по умолчанию, используя Aspose.Slides для Java. Маркеры по умолчанию — это символы или фигуры, добавляемые к точкам данных на диаграмме для их выделения. Мы создадим линейную диаграмму с маркерами для визуализации данных.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем Java-проекте.

## Шаг 1. Создайте презентацию

Для начала давайте создадим презентацию и добавим в нее слайд. Затем мы добавим диаграмму на слайд.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Шаг 2. Добавьте линейный график с маркерами

Теперь давайте добавим на слайд линейную диаграмму с маркерами. Мы также удалим из диаграммы все данные по умолчанию.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Шаг 3. Заполнение данных диаграммы

Мы заполним диаграмму примерами данных. В этом примере мы создадим две серии с точками данных и категориями.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Серия 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Серия 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Заполнение данных серии
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Шаг 4. Настройте диаграмму

Вы можете дополнительно настроить диаграмму, например добавить легенду и настроить ее внешний вид.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Шаг 5. Сохраните презентацию

Наконец, сохраните презентацию с диаграммой в нужном месте.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Вот и все! Вы создали линейную диаграмму с маркерами по умолчанию, используя Aspose.Slides для Java.

## Полный исходный код для маркеров по умолчанию в диаграмме в слайдах Java

```java
        // Путь к каталогу документов.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Возьмите вторую серию диаграмм
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Теперь заполняем данные серии
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Заключение

В этом подробном руководстве вы узнали, как создавать слайды Java с маркерами по умолчанию на диаграммах, используя Aspose.Slides для Java. Мы рассмотрели весь процесс: от настройки презентации до настройки внешнего вида диаграммы и сохранения результата.

## Часто задаваемые вопросы

### Как изменить символы маркеров?

Вы можете настроить символы маркеров, задав стиль маркера для каждой точки данных. Использовать`IDataPoint.setMarkerStyle()` чтобы изменить символ маркера.

### Как настроить цвета диаграммы?

 Чтобы изменить цвета диаграммы, вы можете использовать`IChartSeriesFormat` и`IShapeFillFormat` интерфейсы для установки свойств заливки и линии.

### Могу ли я добавлять метки к точкам данных?

 Да, вы можете добавлять метки к точкам данных, используя`IDataPoint.getLabel()` метод и настройте их по мере необходимости.