---
title: Блок-диаграмма в слайдах Java
linktitle: Блок-диаграмма в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать коробчатые диаграммы в презентациях Java с помощью Aspose.Slides. Пошаговое руководство и исходный код включены для эффективной визуализации данных.
type: docs
weight: 10
url: /ru/java/chart-elements/box-chart-java-slides/
---

## Введение в ящичную диаграмму в Aspose.Slides для Java

В этом уроке мы познакомим вас с процессом создания коробчатой диаграммы с использованием Aspose.Slides для Java. Ящичковые диаграммы полезны для визуализации статистических данных с различными квартилями и выбросами. Мы предоставим пошаговые инструкции вместе с исходным кодом, которые помогут вам начать работу.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена и настроена библиотека Aspose.Slides для Java.
- Настроена среда разработки Java.

## Шаг 1. Инициализируйте презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

На этом этапе мы инициализируем объект презентации, используя путь к существующему файлу PowerPoint («test.pptx» в этом примере).

## Шаг 2. Создайте коробчатую диаграмму

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

На этом этапе мы создаем фигуру прямоугольной диаграммы на первом слайде презентации. Мы также удаляем из диаграммы все существующие категории и серии.

## Шаг 3: Определите категории

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 На этом этапе мы определяем категории для коробчатой диаграммы. Мы используем`IChartDataWorkbook` чтобы добавить категории и пометить их соответствующим образом.

## Шаг 4: Создайте серию

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Здесь мы создаем серию BoxAndWhisker для диаграммы и настраиваем различные параметры, такие как метод квартилей, средняя линия, средние маркеры, внутренние точки и точки выбросов.

## Шаг 5: Добавьте точки данных

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

На этом этапе мы добавляем точки данных в серию BoxAndWhisker. Эти точки данных представляют собой статистические данные для диаграммы.

## Шаг 6. Сохраните презентацию

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Наконец, мы сохраняем презентацию с коробчатой диаграммой в новый файл PowerPoint с именем «BoxAndWhisker.pptx».

Поздравляем! Вы успешно создали ящичную диаграмму с помощью Aspose.Slides для Java. Вы можете дополнительно настроить диаграмму, настроив различные свойства и добавив дополнительные точки данных по мере необходимости.

## Полный исходный код для коробчатой диаграммы в слайдах Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы узнали, как создать ящичную диаграмму с помощью Aspose.Slides для Java. Ящичковые диаграммы — ценные инструменты для визуализации статистических данных, включая квартили и выбросы. Мы предоставили пошаговое руководство вместе с исходным кодом, которое поможет вам приступить к созданию коробчатых диаграмм в ваших Java-приложениях.

## Часто задаваемые вопросы

### Как изменить внешний вид коробчатой диаграммы?

Вы можете настроить внешний вид коробчатой диаграммы, изменив такие свойства, как стили линий, цвета и шрифты. Подробную информацию о настройке диаграмм см. в документации Aspose.Slides for Java.

### Могу ли я добавить дополнительные ряды данных в прямоугольную диаграмму?

 Да, вы можете добавить несколько рядов данных в ящичную диаграмму, создав дополнительные`IChartSeries` объекты и добавление к ним точек данных.

### Что означает QuartileMethodType.Exclusive?

`QuartileMethodType.Exclusive` Параметр указывает, что расчеты квартилей должны выполняться с использованием эксклюзивного метода. Вы можете выбрать различные методы расчета квартилей в зависимости от ваших данных и требований.