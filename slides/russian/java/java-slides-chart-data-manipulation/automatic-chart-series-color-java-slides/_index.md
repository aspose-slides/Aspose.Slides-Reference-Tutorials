---
"description": "Узнайте, как создавать динамические диаграммы с автоматическим цветом серий в презентациях PowerPoint с помощью Aspose.Slides для Java. Улучшайте визуализацию данных без усилий."
"linktitle": "Автоматический цвет серии диаграмм в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Автоматический цвет серии диаграмм в слайдах Java"
"url": "/ru/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Автоматический цвет серии диаграмм в слайдах Java


## Введение в автоматическую раскраску серии диаграмм в Aspose.Slides для Java

В этом уроке мы рассмотрим, как создать презентацию PowerPoint с диаграммой с помощью Aspose.Slides для Java и установить автоматические цвета заливки для серий диаграмм. Автоматические цвета заливки могут сделать ваши диаграммы более визуально привлекательными и сэкономить вам время, позволяя библиотеке выбирать цвета за вас.

## Предпосылки

Прежде чем начать, убедитесь, что в вашем проекте установлена библиотека Aspose.Slides for Java. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Создайте новую презентацию

Сначала мы создадим новую презентацию PowerPoint и добавим в нее слайд.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2: Добавьте диаграмму на слайд

Далее мы добавим на слайд кластеризованную столбчатую диаграмму. Также мы настроим первую серию для отображения значений.

```java
// Доступ к первому слайду
ISlide slide = presentation.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Установить первую серию для показа значений
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Шаг 3: Заполнение диаграммы данными

Теперь заполним диаграмму данными. Начнем с удаления сгенерированных по умолчанию серий и категорий, а затем добавим новые серии и категории.

```java
// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавление новых серий
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Шаг 4: Заполнение рядов данных

Мы заполним данные как для серии 1, так и для серии 2.

```java
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Шаг 5: Установите автоматический цвет заливки для серии

Теперь давайте установим автоматические цвета заливки для серии диаграмм. Это заставит библиотеку выбирать цвета для нас.

```java
// Установка автоматического цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Шаг 6: Сохраните презентацию

Наконец, сохраним презентацию с диаграммой в файл PowerPoint.

```java
// Сохранить презентацию с диаграммой
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для автоматического цвета серии диаграмм в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
try
{
	// Доступ к первому слайду
	ISlide slide = presentation.getSlides().get_Item(0);
	// Добавить диаграмму с данными по умолчанию
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Установить первую серию для показа значений
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Установка индекса листа данных диаграммы
	int defaultWorksheetIndex = 0;
	// Получение рабочего листа данных диаграммы
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Удалить созданные по умолчанию серии и категории
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Добавление новых серий
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Добавление новых категорий
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Возьмите первую серию диаграмм
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Сейчас заполняем данные серий
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Установка автоматического цвета заливки для серии
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Возьмите вторую серию диаграмм
	series = chart.getChartData().getSeries().get_Item(1);
	// Сейчас заполняем данные серий
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

В этом уроке мы узнали, как создать презентацию PowerPoint с диаграммой с помощью Aspose.Slides для Java и задать автоматические цвета заливки для серий диаграмм. Автоматические цвета могут улучшить визуальную привлекательность ваших диаграмм и сделать ваши презентации более интересными. Вы можете дополнительно настроить диаграмму по мере необходимости в соответствии с вашими конкретными требованиями.

## Часто задаваемые вопросы

### Как установить автоматические цвета заливки для рядов диаграмм в Aspose.Slides для Java?

Чтобы задать автоматические цвета заливки для рядов диаграмм в Aspose.Slides для Java, используйте следующий код:

```java
// Установка автоматического цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Этот код позволит библиотеке автоматически выбирать цвета для серии диаграмм.

### Могу ли я при необходимости настроить цвета диаграммы?

Да, вы можете настроить цвета диаграммы по мере необходимости. В приведенном примере мы использовали автоматические цвета заливки, но вы можете задать определенные цвета, изменив `FillType` и `SolidFillColor` свойства формата серии.

### Как добавить в диаграмму дополнительные серии или категории?

Чтобы добавить дополнительные серии или категории в диаграмму, используйте `getSeries()` и `getCategories()` методы диаграммы `ChartData` объект. Вы можете добавлять новые серии и категории, указав их данные и метки.

### Возможно ли дополнительно отформатировать диаграмму и метки?

Да, вы можете дополнительно отформатировать диаграмму, ряды и метки по мере необходимости. Aspose.Slides для Java предоставляет обширные возможности форматирования диаграмм, включая шрифты, цвета, стили и многое другое. Вы можете изучить документацию для получения более подробной информации о параметрах форматирования.

### Где я могу найти более подробную информацию о работе с Aspose.Slides для Java?

Для получения дополнительной информации и подробной документации по Aspose.Slides для Java вы можете посетить справочную документацию. [здесь](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}