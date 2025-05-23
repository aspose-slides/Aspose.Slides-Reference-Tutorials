---
"description": "Узнайте, как создавать точечные диаграммы в Java с помощью Aspose.Slides. Пошаговое руководство с исходным кодом Java для визуализации данных в презентациях."
"linktitle": "Диаграмма разброса в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Диаграмма разброса в слайдах Java"
"url": "/ru/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Диаграмма разброса в слайдах Java


## Введение в точечную диаграмму в Aspose.Slides для Java

В этом уроке мы проведем вас через процесс создания диаграммы рассеяния с помощью Aspose.Slides для Java. Диаграммы рассеяния полезны для визуализации точек данных на двумерной плоскости. Мы предоставим пошаговые инструкции и включим исходный код Java для вашего удобства.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. [Aspose.Slides для Java](https://products.aspose.com/slides/java) установлен.
2. Настроена среда разработки Java.

## Шаг 1: Инициализация презентации

Сначала импортируйте необходимые библиотеки и создайте новую презентацию.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создайте каталог, если его еще нет.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Создать новую презентацию
Presentation pres = new Presentation();
```

## Шаг 2: Добавьте слайд и создайте точечную диаграмму

Далее добавляем слайд и создаем на нем точечную диаграмму. Мы будем использовать `ScatterWithSmoothLines` тип диаграммы в этом примере.

```java
// Получить первый слайд
ISlide slide = pres.getSlides().get_Item(0);

// Создание диаграммы рассеяния
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Шаг 3: Подготовка данных диаграммы

Теперь давайте подготовим данные для нашей точечной диаграммы. Добавим две серии, каждая с несколькими точками данных.

```java
// Получение индекса рабочего листа данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;

// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Удалить демо-серию
chart.getChartData().getSeries().clear();

// Добавить первую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Возьмем первую серию диаграмм.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Добавить точки данных в первую серию
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Изменить тип серии
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Изменить размер маркера
series.getMarker().setSymbol(MarkerStyleType.Star); // Изменить символ маркера

// Возьмем вторую серию диаграмм.
series = chart.getChartData().getSeries().get_Item(1);

// Добавить точки данных во вторую серию
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Изменить стиль маркера для второй серии
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Шаг 4: Сохраните презентацию

Наконец, сохраните презентацию с диаграммой рассеяния в файл PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали точечную диаграмму с помощью Aspose.Slides для Java. Теперь вы можете настроить этот пример в соответствии с вашими конкретными данными и требованиями к дизайну.

## Полный исходный код для разбросанной диаграммы в Java Slides
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если его еще нет.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Создание диаграммы по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Получение индекса рабочего листа данных диаграммы по умолчанию
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить демо-серию
chart.getChartData().getSeries().clear();
// Добавить новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Добавьте туда новую точку (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Добавить новый пункт (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Изменить тип серии
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Изменение маркера серии диаграммы
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Добавьте туда новый пункт (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Добавить новую точку (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Добавить новую точку (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Добавить новую точку (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Изменение маркера серии диаграммы
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы провели вас через процесс создания диаграммы рассеяния с помощью Aspose.Slides для Java. Диаграммы рассеяния — это мощные инструменты для визуализации точек данных в двумерном пространстве, что упрощает анализ и понимание сложных взаимосвязей данных.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

Чтобы изменить тип диаграммы, используйте `setType` метод на серии диаграмм и предоставить желаемый тип диаграммы. Например, `series.setType(ChartType.Line)` изменит ряд на линейный график.

### Как настроить размер и стиль маркера?

Вы можете изменить размер и стиль маркера с помощью `getMarker` метод на серии, а затем задать размер и свойства символа. Например:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Дополнительные возможности настройки можно найти в документации Aspose.Slides для Java.

Не забудьте заменить `"Your Document Directory"` на фактический путь, по которому вы хотите сохранить презентацию.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}