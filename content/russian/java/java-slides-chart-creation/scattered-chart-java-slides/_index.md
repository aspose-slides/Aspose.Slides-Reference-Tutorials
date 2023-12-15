---
title: Рассеянная диаграмма в слайдах Java
linktitle: Рассеянная диаграмма в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать точечные диаграммы на Java с помощью Aspose.Slides. Пошаговое руководство с исходным кодом Java для визуализации данных в презентациях.
type: docs
weight: 11
url: /ru/java/chart-creation/scattered-chart-java-slides/
---

## Введение в точечную диаграмму в Aspose.Slides для Java

В этом уроке мы проведем вас через процесс создания точечной диаграммы с помощью Aspose.Slides для Java. Точечные диаграммы полезны для визуализации точек данных на двухмерной плоскости. Для вашего удобства мы предоставим пошаговые инструкции и приложим исходный код Java.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. [Aspose.Слайды для Java](https://products.aspose.com/slides/java) установлен.
2. Настроена среда разработки Java.

## Шаг 1. Инициализируйте презентацию

Сначала импортируйте необходимые библиотеки и создайте новую презентацию.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создайте каталог, если он еще не существует.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Создать новую презентацию
Presentation pres = new Presentation();
```

## Шаг 2. Добавьте слайд и создайте точечную диаграмму

 Затем добавьте слайд и создайте на нем точечную диаграмму. Мы будем использовать`ScatterWithSmoothLines` тип диаграммы в этом примере.

```java
// Получить первый слайд
ISlide slide = pres.getSlides().get_Item(0);

// Создание точечной диаграммы
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Шаг 3. Подготовьте данные диаграммы

Теперь давайте подготовим данные для нашей точечной диаграммы. Мы добавим две серии, каждая из которых будет содержать несколько точек данных.

```java
// Получение индекса таблицы данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;

//Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Удалить демонстрационную серию
chart.getChartData().getSeries().clear();

// Добавьте первую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Добавьте точки данных в первую серию
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Изменить тип серии
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Изменить размер маркера
series.getMarker().setSymbol(MarkerStyleType.Star); // Изменить символ маркера

// Возьмите вторую серию диаграмм.
series = chart.getChartData().getSeries().get_Item(1);

// Добавьте точки данных во вторую серию
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Измените стиль маркера для второй серии.
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Шаг 4. Сохраните презентацию

Наконец, сохраните презентацию с точечной диаграммой в файл PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали точечную диаграмму с помощью Aspose.Slides для Java. Теперь вы можете дополнительно настроить этот пример в соответствии с вашими конкретными данными и требованиями к проектированию.

## Полный исходный код для рассеянной диаграммы в слайдах Java
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если он еще не существует.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Создание диаграммы по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Получение индекса таблицы данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;
//Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить демонстрационную серию
chart.getChartData().getSeries().clear();
// Добавить новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Добавьте туда новую точку (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Добавить новую точку (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Изменить тип серии
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Изменение маркера серии диаграммы
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Добавьте туда новую точку (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Добавить новый балл (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
//Добавить новую точку (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Добавить новую точку (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Изменение маркера серии диаграммы
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы познакомили вас с процессом создания точечной диаграммы с помощью Aspose.Slides для Java. Точечные диаграммы — это мощные инструменты для визуализации точек данных в двумерном пространстве, которые упрощают анализ и понимание сложных взаимосвязей данных.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

 Чтобы изменить тип диаграммы, используйте`setType` метод для серии диаграмм и укажите желаемый тип диаграммы. Например,`series.setType(ChartType.Line)` изменит ряд на линейный график.

### Как настроить размер и стиль маркера?

 Вы можете изменить размер и стиль маркера, используя`getMarker` метод для серии, а затем установите свойства размера и символа. Например:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Не стесняйтесь изучить дополнительные параметры настройки в документации Aspose.Slides for Java.

 Не забудьте заменить`"Your Document Directory"` с фактическим путем, по которому вы хотите сохранить презентацию.