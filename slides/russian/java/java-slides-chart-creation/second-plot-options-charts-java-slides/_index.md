---
"description": "Узнайте, как настраивать диаграммы в Java Slides с помощью Aspose.Slides для Java. Изучите параметры второго графика и улучшите свои презентации."
"linktitle": "Параметры второго графика для диаграмм в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Параметры второго графика для диаграмм в слайдах Java"
"url": "/ru/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Параметры второго графика для диаграмм в слайдах Java


## Введение в параметры второго графика для диаграмм в слайдах Java

В этом уроке мы рассмотрим, как добавлять параметры второго графика к диаграммам с помощью Aspose.Slides для Java. Параметры второго графика позволяют настраивать внешний вид и поведение диаграмм, особенно в таких сценариях, как круговые диаграммы. Мы предоставим пошаговые инструкции и примеры исходного кода для достижения этой цели. 

## Предпосылки
Прежде чем начать, убедитесь, что в вашем проекте Java установлен и настроен Aspose.Slides для Java.

## Шаг 1: Создайте презентацию
Начнем с создания новой презентации:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2: Добавьте диаграмму на слайд
Далее мы добавим диаграмму на слайд. В этом примере мы создадим круговую диаграмму:

```java
// Добавить диаграмму на слайд
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Шаг 3: Настройте свойства диаграммы
Теперь давайте зададим различные свойства диаграммы, включая параметры второго построения:

```java
// Показать метки данных для первой серии
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Установите размер второй части круга (в процентах)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Разделить пирог по процентному соотношению
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Установите положение разделения
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Шаг 4: Сохраните презентацию
Наконец, сохраните презентацию с параметрами диаграммы и второго графика:

```java
// Записать презентацию на диск
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для второго варианта сюжета

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
// Добавить диаграмму на слайд
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Установить различные свойства
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Записать презентацию на диск
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы узнали, как добавлять параметры второго графика к диаграммам в Java Slides с помощью Aspose.Slides для Java. Вы можете настраивать различные свойства, чтобы улучшить внешний вид и функциональность ваших диаграмм, делая ваши презентации более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как изменить размер второй части круговой диаграммы?

Чтобы изменить размер второго круга в круговой диаграмме, используйте `setSecondPieSize` метод, как показано в примере кода выше. Отрегулируйте значение, чтобы указать размер в процентах.

### Что делает `PieSplitBy` контроль в круговой диаграмме?

The `PieSplitBy` свойство управляет тем, как разделена круговая диаграмма. Вы можете установить его на `PieSplitType.ByPercentage` или `PieSplitType.ByValue` для разделения диаграммы по проценту или по определенному значению соответственно.

### Как задать положение разделения в круговой диаграмме?

Вы можете задать положение разделения в круговой диаграмме с помощью `setPieSplitPosition` Метод. Отрегулируйте значение, чтобы указать желаемую позицию.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}