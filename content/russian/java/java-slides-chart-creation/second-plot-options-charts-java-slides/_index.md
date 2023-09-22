---
title: Вторые параметры графика для диаграмм в слайдах Java
linktitle: Вторые параметры графика для диаграмм в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как настраивать диаграммы в Java Slides с помощью Aspose.Slides для Java. Изучите варианты второго сюжета и улучшите свои презентации.
type: docs
weight: 12
url: /ru/java/chart-creation/second-plot-options-charts-java-slides/
---

## Введение в параметры второго графика для диаграмм в слайдах Java

В этом уроке мы рассмотрим, как добавить вторые параметры графика к диаграммам с помощью Aspose.Slides для Java. Параметры второго графика позволяют настраивать внешний вид и поведение диаграмм, особенно в таких сценариях, как круговые диаграммы. Для этого мы предоставим пошаговые инструкции и примеры исходного кода. 

## Предварительные условия
Прежде чем мы начнем, убедитесь, что Aspose.Slides for Java установлен и настроен в вашем Java-проекте.

## Шаг 1. Создайте презентацию
Начнем с создания новой презентации:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2. Добавьте диаграмму на слайд
Далее мы добавим диаграмму на слайд. В этом примере мы создадим круговую диаграмму:

```java
// Добавить диаграмму на слайд
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Шаг 3. Настройте свойства диаграммы
Теперь давайте установим различные свойства диаграммы, включая параметры второго графика:

```java
// Показать метки данных для первой серии
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Установите размер второго круга (в процентах)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Разделить пирог по процентам
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

//Установите положение разделения
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Шаг 4. Сохраните презентацию
Наконец, сохраните презентацию с диаграммой и вторыми параметрами графика:

```java
// Записать презентацию на диск
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для вариантов второго графика

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
// Добавить диаграмму на слайд
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Установите разные свойства
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Записать презентацию на диск
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы узнали, как добавить вторые параметры графика к диаграммам в Java Slides с помощью Aspose.Slides для Java. Вы можете настроить различные свойства, чтобы улучшить внешний вид и функциональность диаграмм, сделав презентации более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как изменить размер второй круговой диаграммы на круговой диаграмме?

 Чтобы изменить размер второй круговой диаграммы в круговой диаграмме, используйте`setSecondPieSize` метод, как показано в примере кода выше. Отрегулируйте значение, чтобы указать размер в процентах.

###  Что значит`PieSplitBy` control in a Pie of Pie chart?

`PieSplitBy` Свойство управляет разделением круговой диаграммы. Вы можете установить его либо`PieSplitType.ByPercentage` или`PieSplitType.ByValue` чтобы разделить диаграмму по процентам или по определенному значению соответственно.

### Как установить положение разделения на круговой диаграмме?

 Вы можете установить положение разделения на круговой диаграмме, используя`setPieSplitPosition` метод. Отрегулируйте значение, чтобы указать желаемое положение.