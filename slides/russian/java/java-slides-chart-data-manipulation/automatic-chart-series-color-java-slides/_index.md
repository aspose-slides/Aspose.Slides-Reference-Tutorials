---
title: Автоматический цвет серии диаграмм в слайдах Java
linktitle: Автоматический цвет серии диаграмм в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать динамические диаграммы с автоматическим цветом рядов в презентациях PowerPoint с помощью Aspose.Slides для Java. Улучшите визуализацию данных без особых усилий.
type: docs
weight: 14
url: /ru/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Введение в автоматический цвет серии диаграмм в Aspose.Slides для Java

В этом уроке мы рассмотрим, как создать презентацию PowerPoint с диаграммой с помощью Aspose.Slides для Java и установить автоматические цвета заливки для серий диаграмм. Автоматические цвета заливки могут сделать ваши диаграммы более привлекательными и сэкономить ваше время, позволяя библиотеке выбирать цвета за вас.

## Предварительные условия

 Прежде чем начать, убедитесь, что в вашем проекте установлена библиотека Aspose.Slides for Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).

## Шаг 1. Создайте новую презентацию

Сначала мы создадим новую презентацию PowerPoint и добавим в нее слайд.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2. Добавьте диаграмму на слайд

Далее мы добавим на слайд кластеризованную столбчатую диаграмму. Мы также настроим первую серию для отображения значений.

```java
// Доступ к первому слайду
ISlide slide = presentation.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Установите для первой серии значение «Показать значения».
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Шаг 3. Заполнение данных диаграммы

Теперь мы заполним диаграмму данными. Мы начнем с удаления серий и категорий, созданных по умолчанию, а затем добавим новые серии и категории.

```java
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;
// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавляем новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Шаг 4. Заполнение данных серии

Мы заполним данные серии как для серии 1, так и для серии 2.

```java
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Шаг 5. Установите автоматический цвет заливки для серии

Теперь давайте установим автоматические цвета заливки для серии диаграмм. Это заставит библиотеку выбирать цвета за нас.

```java
// Установка цвета автоматической заливки для серий
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Шаг 6. Сохраните презентацию

Наконец, мы сохраним презентацию с диаграммой в файл PowerPoint.

```java
// Сохранить презентацию с диаграммой
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для автоматического цвета серии диаграмм в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
try
{
	// Доступ к первому слайду
	ISlide slide = presentation.getSlides().get_Item(0);
	// Добавить диаграмму с данными по умолчанию
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Установите для первой серии значение «Показать значения».
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Установка индекса таблицы данных диаграммы
	int defaultWorksheetIndex = 0;
	// Получение листа данных диаграммы
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Удалить созданные по умолчанию серии и категории
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Добавляем новую серию
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Добавление новых категорий
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Возьмите первую серию диаграмм
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Теперь заполняем данные серии
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Установка цвета автоматической заливки для серий
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Возьмите вторую серию диаграмм
	series = chart.getChartData().getSeries().get_Item(1);
	// Теперь заполняем данные серии
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Установка цвета заливки для серии
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Сохранить презентацию с диаграммой
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

В этом уроке мы узнали, как создать презентацию PowerPoint с диаграммой с помощью Aspose.Slides для Java и установить автоматические цвета заливки для серий диаграмм. Автоматические цвета могут повысить визуальную привлекательность диаграмм и сделать презентации более привлекательными. Вы можете дополнительно настроить диаграмму в соответствии с вашими конкретными требованиями.

## Часто задаваемые вопросы

### Как установить автоматические цвета заливки для серий диаграмм в Aspose.Slides для Java?

Чтобы установить автоматические цвета заливки для серии диаграмм в Aspose.Slides для Java, используйте следующий код:

```java
// Установка цвета автоматической заливки для серий
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Этот код позволит библиотеке автоматически выбирать цвета для серии диаграмм.

### Могу ли я при необходимости настроить цвета диаграммы?

 Да, вы можете настроить цвета диаграммы по своему усмотрению. В приведенном примере мы использовали автоматические цвета заливки, но вы можете установить определенные цвета, изменив параметр`FillType` и`SolidFillColor` свойства формата серии.

### Как добавить на диаграмму дополнительные серии или категории?

 Чтобы добавить на диаграмму дополнительные серии или категории, используйте кнопку`getSeries()` и`getCategories()` методы построения диаграммы`ChartData` объект. Вы можете добавлять новые серии и категории, указав их данные и метки.

### Возможно ли дальнейшее форматирование диаграммы и меток?

Да, вы можете дополнительно отформатировать диаграмму, ряды и метки по мере необходимости. Aspose.Slides для Java предоставляет широкие возможности форматирования диаграмм, включая шрифты, цвета, стили и многое другое. Вы можете изучить документацию для получения более подробной информации о параметрах форматирования.

### Где я могу найти дополнительную информацию о работе с Aspose.Slides для Java?

 Для получения дополнительной информации и подробной документации по Aspose.Slides для Java вы можете посетить справочную документацию.[здесь](https://reference.aspose.com/slides/java/).